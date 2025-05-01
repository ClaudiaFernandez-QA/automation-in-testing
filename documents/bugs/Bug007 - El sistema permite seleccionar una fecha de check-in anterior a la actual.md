# 🐞 BUG007 - El sistema permite seleccionar una fecha de check-in anterior a la actual

- **Funcionalidad**: Booking 
- **Severidad**: Baja
- **Prioridad**: Media
- **Estado**: Abierto
- **Reportado por**: Claudia Fernández
- **Fecha**: 2025-04-30

## 🔍 Descripción
El sistema debería restringir al usuario de seleccionar una fecha de check-in anterior al día actual. Sin embargo, actualmente es posible ingresar fechas pasadas y realizar la búsqueda de disponibilidad sin restricciones, lo que contradice las reglas de negocio y puede generar confusión.

## 🔁 Pasos para reproducir
1. Ingresar al sitio Shady Meadows B&B
2. Ir a la sección "Booking"
3. Seleccionar una fecha de check-in anterior a la actual
4. Seleccionar una fecha de check-out posterior
5. Hacer clic en "Check Availability"

## ✅ Resultado Esperado
El sistema debe deshabilitar en el calendario todas las fechas anteriores a la actual para el campo de check-in, impidiendo su selección.

## ❌ Resultado Obtenido
El sistema permite seleccionar fechas pasadas y realiza la búsqueda como si fueran válidas, sin mostrar advertencias ni errores.

---

## 🔗 Asociaciones

- **User Story**: [US002 - Consultar disponibilidad desde el buscador de Booking](../features/US002_booking_check_availability.md)
- **Caso de Prueba**: TC004 - Impedir fechas pasadas como check-in

