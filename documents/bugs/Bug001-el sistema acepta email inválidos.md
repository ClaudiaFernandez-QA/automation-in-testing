# 🐞 BUG002 - El sistema acepta direcciones de email inválidas sin validación

- **Funcionalidad**: Formulario de reserva
- **Severidad**: Media
- **Prioridad**: Alta
- **Estado**: Abierto
- **Reportado por**: Claudia Fernández
- **Fecha**: 2025-04-30

## 🔍 Descripción
El formulario de reserva permite completar el campo `Email` con una dirección inválida (por ejemplo, "test@example") y procesa la reserva sin mostrar ningún mensaje de error. Esto puede derivar en datos inválidos en el sistema y en problemas de comunicación con el cliente.

## 🔁 Pasos para reproducir
1. Ingresar al sitio Shady Meadows B&B
2. Navegar a la sección "Our Rooms" y hacer clic en "Book now"
3. Completar el formulario con:
   - `Firstname`: Juan José
   - `Lastname`: Martín
   - `Email`: test@example
   - `Phone`: 114455667788
   - Fechas válidas de reserva
4. Hacer clic en "Reserve Now"

## ✅ Resultado Esperado
El sistema debería validar el formato del email y rechazar direcciones incompletas (sin dominio correcto), mostrando un mensaje de error junto al campo.

## ❌ Resultado Obtenido
La reserva se procesa exitosamente y no se muestra ninguna validación ni mensaje de error.

---

## 🔗 Asociaciones

- **User Story**: [US001 - Realizar una reserva desde el sitio web](../features/US001_reserva_habitacion.md)
- **Caso de Prueba**: TC005 - Email inválido

