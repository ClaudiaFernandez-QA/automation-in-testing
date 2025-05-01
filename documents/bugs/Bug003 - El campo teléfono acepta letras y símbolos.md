# 🐞 BUG003 - El campo teléfono acepta letras y símbolos

- **Funcionalidad**: Formulario de reserva
- **Severidad**: Media
- **Prioridad**: Alta
- **Estado**: Abierto
- **Reportado por**: Claudia Fernández
- **Fecha**: 2025-04-30

## 🔍 Descripción
El campo `Phone` del formulario de reserva debería aceptar únicamente números. Actualmente, si se ingresan letras o símbolos (por ejemplo, "abc%%123456"), el sistema permite continuar con la reserva siempre que la longitud esté dentro del rango válido (entre 11 y 21 caracteres). Esto genera datos inválidos y puede afectar procesos posteriores.

## 🔁 Pasos para reproducir
1. Ingresar al sitio Shady Meadows B&B
2. Ir a la sección "Our Rooms" y seleccionar una habitación
3. Completar el formulario con:
   - `Firstname`: Marcela
   - `Lastname`: Francia
   - `Email`: marcela28@mail.com
   - `Phone`: abc%%1234566
   - Fechas válidas
4. Hacer clic en "Reserve Now"

## ✅ Resultado Esperado
El sistema debe validar que el campo `Phone` contenga únicamente caracteres numéricos. Si se ingresan letras o símbolos, debe mostrarse un mensaje de error y no debe permitirse completar la reserva.

## ❌ Resultado Obtenido
La reserva se procesa con éxito, incluso con un número de teléfono compuesto por letras y símbolos. No se muestra ninguna advertencia ni validación.

---

## 🔗 Asociaciones

- **User Story**: [US001 - Realizar una reserva desde el sitio web](../features/US001_reserva_habitacion.md)
- **Caso de Prueba**: TC008 - Validación de campo teléfono

