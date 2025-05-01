# 🐞 BUG005 - Error de aplicación al intentar reservar una habitación ya reservada

- **Funcionalidad**: Validación de disponibilidad y procesamiento de reserva
- **Severidad**: Alta
- **Prioridad**: Alta
- **Estado**: Abierto
- **Reportado por**: Claudia Fernández
- **Fecha**: 2025-04-30

## 🔍 Descripción
Cuando se intenta hacer una reserva para una habitación que ya está ocupada en las mismas fechas, el sistema muestra que la habitación no esta disponible. Sin embargo, permite continuar completando el formulario, y al hacer clic en "Reserve Now", se genera un error de aplicación. La página se rompe y se muestra el siguiente mensaje:

```
Application error: a client-side exception has occurred while loading automationintesting.online (see the browser console for more information).
```

Esto representa una falla crítica tanto en la experiencia del usuario como en el control de errores del sistema.

## 🔁 Pasos para reproducir
1. Ingresar al sitio Shady Meadows B&B
2. Ir a la sección "Our Rooms" y seleccionar una habitación
3. Elegir una fecha de check-in y check-out que ya esté reservada previamente
4. Completar el formulario con datos válidos
5. Hacer clic en "Reserve Now"

## ✅ Resultado Esperado
El sistema debe bloquear la reserva para fechas ya ocupadas desde el principio, y evitar que el usuario complete el formulario. Si se detecta un conflicto, debe mostrarse un mensaje claro sin romper la aplicación.

## ❌ Resultado Obtenido
Se muestra una advertencia de disponibilidad, pero el formulario se puede completar igual. Al hacer clic en "Reserve Now", la página se rompe y lanza un error de aplicación genérico.

---

## 🔗 Asociaciones

- **User Story**: [US001 - Realizar una reserva desde el sitio web](../features/US001_reserva_habitacion.md)
- **Caso de Prueba**: TC012 - Doble reserva para la misma fecha y habitación

