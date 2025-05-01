# 🧾 User Story: Consultar disponibilidad de habitaciones desde el buscador de Booking

**ID**: US002  
**Nombre**: Verificar disponibilidad de habitaciones según las fechas ingresadas

> **Como** visitante del sitio Shady Meadows B&B  
> **Quiero** poder consultar las habitaciones disponibles para el rango de fechas ingresado
> **Para** ver qué opciones de alojamiento tengo disponibles

---

## ✅ Criterios de Aceptación

```gherkin
Feature: Verificar disponibilidad de habitaciones desde el buscador de Booking


 Scenario: Las fechas deben estar precargadas por defecto en el día de hoy y el siguiente
    Given El usuario está en la sección "Booking"
    When Visualiza los campos de fecha al cargar la página
    Then El sistema debe mostrar como check-in la fecha actual y como check-out la siguiente

 Scenario: Los campos de fecha deben aceptar únicamente valores de tipo fecha
    Given El usuario está en la sección "Booking"
    When Intenta modificar los campos de fecha con caracteres inválidos o vacíos
    Then El sistema debe impedirlo y restaurar la última fecha válida cargada

 Scenario: La fecha de check-out debe ser posterior a la de check-in
    Given El usuario está en la sección "Booking"
    When Selecciona una fecha de check-out anterior a la de check-in
    Then El sistema debe impedir la acción y mostrar un mensaje de error o evitar realizar la búsqueda

 Scenario: No se deben permitir fechas anteriores a la actual
    Given El usuario está en la sección "Booking"
    When Selecciona una fecha de check-in anterior al día actual
    Then El sistema debe impedir la búsqueda y mostrar un mensaje de error indicando que no se pueden usar fechas pasadas

 Scenario: El usuario consulta disponibilidad para fechas válidas
    Given El usuario se encuentra en la sección "Booking"
    When Selecciona fechas de check-in y check-out válidas y hace clic en "Check Availability"
    Then El sistema debe mostrar las habitaciones disponibles para ese rango de fechas

 Scenario: No hay habitaciones disponibles para las fechas seleccionadas
    Given El usuario selecciona fechas para las cuales no hay disponibilidad
    When Hace clic en "Check Availability"
    Then El sistema debe mostrar un mensaje claro indicando que no hay habitaciones disponibles

```
---

## 🧪 Casos de Prueba 

### 🔹 TC001 - Validación de fechas precargadas por defecto
- **Precondición**: El usuario se encuentra en la sección "Booking"
- **Pasos**:
  1. Ingresar a la sección "Booking"
  2. Verificar que los campos de fecha estén completos al cargar la página
- **Resultado esperado**: El campo de check-in muestra la fecha actual, y el campo de check-out muestra la fecha siguiente

---

### 🔹 TC002 - Impedir modificación con caracteres inválidos en fechas
- **Precondición**: El usuario se encuentra en la sección "Booking"
- **Pasos**:
  1. Intentar escribir letras o símbolos en los campos de fecha
- **Resultado esperado**: El sistema impide el cambio y restaura la última fecha válida

---

### 🔹 TC003 - Impedir ingresar una fecha check-out anterior a la de check-in
- **Precondición**: El usuario se encuentra en la sección "Booking"
- **Pasos**:
  1. Ingresar una fecha de check-in válida
  2. Intentar ingresar una fecha de check-out anterior a la de check-in
- **Resultado esperado**: El sistema debe impedir seleccionar una fecha de check-out anterior a la de check-in, dejando esas fechas deshabilitadas en el calendario.

---

### 🔹 TC004 - Impedir fechas pasadas como check-in
- **Precondición**: El usuario se encuentra en la sección "Booking"
- **Pasos**:
  1. Abrir el calendario del campo de check-in
  2. Verificar que las fechas anteriores al día actual están deshabilitadas
  3. Intentar seleccionar una fecha pasada
- **Resultado esperado**: El sistema debe impedir seleccionar fechas anteriores al día actual como check-in, manteniéndolas deshabilitadas en el calendario.
---

### 🔹 TC005 - Consulta de disponibilidad con fechas válidas
- **Precondición**: El usuario se encuentra en la sección "Booking"
- **Pasos**:
  1. Ingresar fechas de check-in y check-out válidas
  2. Hacer clic en "Check Availability"
- **Resultado esperado**: El sistema muestra las habitaciones disponibles

---

### 🔹 TC006 - Sin disponibilidad para fechas seleccionadas
- **Precondición**: No hay habitaciones disponibles en el rango de fechas ingresado
- **Pasos**:
  1. Ingresar fechas para las cuales se sabe que no hay disponibilidad
  2. Hacer clic en "Check Availability"
- **Resultado esperado**: El sistema muestra un mensaje indicando que no hay habitaciones disponibles

---
