# 🐞 BUG004 - El sistema permite seleccionar una fecha de check-in pasada

- **Funcionalidad**: Formulario de reserva
- **Severidad**: Media
- **Prioridad**: Alta
- **Estado**: Abierto
- **Reportado por**: Claudia Fernández
- **Fecha**: 2025-04-30

## 🔍 Descripción
El sistema debería impedir que el usuario seleccione una fecha de check-in anterior al día actual. Actualmente, es posible realizar una reserva con fechas en el pasado (por ejemplo, del mes anterior) y el sistema lo acepta sin mostrar mensajes de error. Esto representa un comportamiento ilógico dentro del proceso de reserva.

## 🔁 Pasos para reproducir
1. Ingresar al sitio Shady Meadows B&B
2. Ir a la sección "Our Rooms" y hacer clic en "Book now"
3. En el formulario de reserva, seleccionar:
   - Fecha de check-in: una fecha del mes anterior
   - Fecha de check-out: una fecha posterior a la de check-in
   - Completar el resto del formulario con datos válidos
4. Hacer clic en "Reserve Now"

## ✅ Resultado Esperado
El sistema debe validar que la fecha de check-in no sea anterior al día actual. Si lo es, debe impedir la reserva y mostrar un mensaje de error indicando que la fecha no es válida.

## ❌ Resultado Obtenido
La reserva se procesa exitosamente, incluso cuando se utilizan fechas pasadas para el check-in. No se muestra ningún mensaje de error ni advertencia.

---

## 🔗 Asociaciones

- **User Story**: [US001 - Realizar una reserva desde el sitio web](../features/US001_reserva_habitacion.md)
- **Caso de Prueba**: TC009 - Fecha pasada como check-in

