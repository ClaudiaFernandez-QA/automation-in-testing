# 🐞 BUG006 - El sistema permite seleccionar una fecha de check-out anterior a la de check-in

- **Funcionalidad**: Booking 
- **Severidad**: Baja
- **Prioridad**: Media
- **Estado**: Abierto
- **Reportado por**: Claudia Fernández
- **Fecha**: 2025-04-30

## 🔍 Descripción
El sistema debería impedir seleccionar una fecha de check-out que sea anterior a la de check-in. Sin embargo, actualmente es posible realizar esta acción sin recibir ninguna advertencia o bloqueo. Esto puede llevar a la confusión del usuario.

## 🔁 Pasos para reproducir
1. Ingresar al sitio Shady Meadows B&B
2. Ir a la sección "Booking"
3. Seleccionar una fecha de check-in válida
4. Seleccionar una fecha de check-out anterior a la de check-in 
5. Hacer clic en "Check Availability"

## ✅ Resultado Esperado
El sistema debe impedir seleccionar fechas de check-out anteriores a la de check-in, ya sea deshabilitándolas en el calendario o mostrando un mensaje de validación.

## ❌ Resultado Obtenido
El sistema permite realizar la búsqueda sin ningún mensaje de error ni validación, a pesar de que la lógica de fechas es incorrecta.

---

## 🔗 Asociaciones

- **User Story**: [US002 - Consultar disponibilidad desde el buscador de Booking](../features/US002_booking_check_availability.md)
- **Caso de Prueba**: TC003 - Impedir ingresar una fecha check-out anterior a la de check-in

