# 🐞 BUG002 - El sistema permite ingresar números en el campo firstname y lastName

- **Funcionalidad**: Formulario de reserva
- **Severidad**: Media
- **Prioridad**: Media
- **Estado**: Abierto
- **Reportado por**: Claudia Fernández
- **Fecha**: 2025-04-30

## 🔍 Descripción
Los campo `Firstname` y `Lastname`del formulario de reserva deberían permitir ingresar únicamente letras, en cambio están permitiendo ingresar números y símbolos (por ejemplo, "123%%") sin realizar ningún tipo de validación. La reserva se completa con éxito y se almacena un dato inválido como nombre y apellido del huésped.

## 🔁 Pasos para reproducir
1. Ingresar al sitio Shady Meadows B&B
2. Ir a la sección "Our Rooms" y seleccionar una habitación
3. Completar el formulario con:
   - `Firstname`: 123$%
   - `Lastname`: Martín122
   - `Email`: juan.martin@gmail.com
   - `Phone`: 12222023548982
   - Fechas válidas
4. Hacer clic en "Reserve Now"

## ✅ Resultado Esperado
El sistema debe validar que los campo `Firstname` y `Lastname` contengan solo letras. Si se ingresan números o símbolos, debe mostrarse un mensaje de error y no debe permitirse completar la reserva.

## ❌ Resultado Obtenido
La reserva se procesa con éxito. No se muestra ninguna advertencia ni validación.

---

## 🔗 Asociaciones

- **User Story**: [US001 - Realizar una reserva desde el sitio web](../features/US001_reserva_habitacion.md)
- **Caso de Prueba**: TC006 - Validación de campo firstName
- **Caso de Prueba**: TC007 - Validación de campo lastName
