# 🐞 BUG008 - El sistema no muestra mensaje cuando no hay disponibilidad para las fechas seleccionadas

- **Funcionalidad**: Booking 
- **Severidad**: Media
- **Prioridad**: Media
- **Estado**: Abierto
- **Reportado por**: Claudia Fernández
- **Fecha**: 2025-04-30

## 🔍 Descripción
Cuando el usuario ingresa un rango de fechas en el que no hay habitaciones disponibles, el sistema no muestra ningún mensaje que indique esta situación. Simplemente no se renderiza ningún resultado, lo que puede llevar al usuario a pensar que hubo un error en la búsqueda o que el sistema no respondió.

## 🔁 Pasos para reproducir
1. Ingresar al sitio Shady Meadows B&B
2. Ir a la sección "Booking"
3. Seleccionar un rango de fechas donde se sepa que no hay habitaciones disponibles
4. Hacer clic en "Check Availability"

## ✅ Resultado Esperado
El sistema debe mostrar un mensaje claro indicando que no hay habitaciones disponibles para las fechas seleccionadas.

## ❌ Resultado Obtenido
No se muestra ningún mensaje ni advertencia. La sección de resultados queda vacía, sin retroalimentación para el usuario.

---

## 🔗 Asociaciones

- **User Story**: [US002 - Consultar disponibilidad desde el buscador de Booking](../features/US002_booking_check_availability.md)
- **Caso de Prueba**: TC006 - Sin disponibilidad para fechas seleccionadas

