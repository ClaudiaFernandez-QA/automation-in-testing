# 🧾 User Story: Realizar una reserva desde el sitio web

**ID**: US001  
**Nombre**: Crear una reserva desde el sitio web

> **Como** visitante del sitio Shady Meadows B&B  
> **Quiero** poder reservar una habitación de forma online  
> **Para** asegurar mi estadía de manera rápida y segura

---

## ✅ Criterios de Aceptación 

```gherkin
Feature: Reserva de habitación desde el sitio web

  Scenario: El usuario visualiza correctamente las habitaciones disponibles
    Given El usuario se encuentra en la sección 'Our Rooms'
    And Hay habitaciones disponibles
    When El usuario hace clic en 'Book now'
    Then El sistema deberá mostrar el detalle de la habitación elegida

  Scenario: El usuario selecciona fechas válidas de check-in y check-out
    Given El usuario está en el formulario de reserva
    When Selecciona una fecha de check-in igual o posterior al día actual
    And Selecciona una fecha de check-out posterior a la de check-in
    Then El sistema debe aceptar la selección y permitir continuar

  Scenario: El usuario completa correctamente el formulario de reserva
    Given El usuario se encuentra en el formulario de reserva
    When El usuario completa todos los campos requeridos con datos válidos
    And Hace clic en "Reserve Now"
    Then El sistema debe mostrar un mensaje de confirmación exitoso
    And La reserva debe guardarse en el sistema

  Scenario: El usuario deja campos obligatorios vacíos
    Given El usuario se encuentra en el formulario de reserva
    When El usuario no completa uno o más campos obligatorios
    Then El sistema debe mostrar mensajes de error indicando los campos faltantes

  Scenario: El usuario ingresa un correo electrónico con formato inválido
    Given El usuario está completando el campo de email
    When Ingresa un texto que no tiene formato de correo válido
    Then El sistema debe mostrar un mensaje de error junto al campo

  Scenario: El usuario ingresa caracteres inválidos en los campos firstName y lastName
   Given El usuario está completando los campos firstName y lastName
   When Ingresa números o símbolos en dichos campos
   Then El sistema debe mostrar un mensaje de error 

  Scenario: El usuario ingresa una longitud inválida para el campo teléfono
   Given El usuario está completando el campo teléfono
   When Ingresa menos de once números o mas de veintiuno
   Then El sistema debe mostrar un mensaje de error 

  Scenario: El usuario selecciona una fecha anterior al día actual
    Given El usuario completa el campo "Check in" con una fecha pasada
    When Intenta confirmar la reserva
    Then El sistema debe impedir la acción y mostrar un mensaje de validación

  Scenario: La reserva se visualiza correctamente en el panel de administrador
    Given Una reserva fue creada desde el sitio web del hotel
    When El administrador accede al panel de gestión
    Then La reserva debe figurar en el listado con los datos ingresados

  Scenario: El usuario debe visualizar la disponibilidad de la habitación
   Given El usuario accede al formulario de reserva desde una habitación específica
   When Selecciona el campo de fecha en el calendario
   Then El sistema debe mostrar las fechas en las que la habitación ya está reservada y no permitir seleccionarlas


```

---

## 🧪 Casos de Prueba 

### 🔹 TC001 - Visualización de habitaciones disponibles
- **Precondición**: Hay habitaciones cargadas en el sistema
- **Pasos**:
  1. Navegar a la página Shady Meadows B&B
  2. Ir a la sección "Our Rooms"
  3. Verificar que se muestran las habitaciones disponibles
  4. Hacer clic en "Book now" de alguna habitación
- **Resultado esperado**: Se visualiza el detalle de la habitación seleccionada

---

### 🔹 TC002 - Selección de fechas válidas
- **Precondición**: El usuario se encuentra en el formulario de reserva, tras haber seleccionado una habitación desde la sección “Our Rooms”
- **Pasos**:
  1. Seleccionar una fecha de check-in igual o posterior a hoy
  2. Seleccionar una fecha de check-out posterior a la de check-in
- **Resultado esperado**: Las fechas son aceptadas y se puede continuar con la reserva

---

### 🔹 TC003 - Reserva exitosa con datos válidos
- **Precondición**: Hay al menos una habitación disponible.
- **Pasos**:
  1. Navegar a la página pública del hotel
  2. Completar todos los campos del formulario con datos válidos
  3. Hacer clic en "Reserve Now"
- **Resultado esperado**: Se muestra mensaje de éxito y la reserva se registra en el sistema

---

### 🔹 TC004 - Campos obligatorios vacíos
- **Precondición**:El usuario se encuentra en el formulario de reserva, tras haber seleccionado una habitación desde la sección “Our Rooms”
- **Pasos**:
  1. Dejar vacíos uno o más campos obligatorios
  2. Hacer clic en "Reserve Now"
- **Resultado esperado**: Se muestran mensajes de error junto a los campos vacíos

---

### 🔹 TC005 - Email inválido
- **Precondición**: El usuario se encuentra en el formulario de reserva, tras haber seleccionado una habitación desde la sección “Our Rooms”
- **Pasos**:
  1. Completar el campo de email con "test@example"
  2. Completar los demás campos con datos válidos
  3. Hacer clic en "Reserve Now"
- **Resultado esperado**: Aparece mensaje de error indicando formato incorrecto

---

### 🔹 TC006 - Validación de campo firstName
- **Precondición**: El usuario se encuentra en el formulario de reserva, tras haber seleccionado una habitación desde la sección “Our Rooms”
- **Pasos**:
  1. Completar el campo firstName con números
  2. Completar los demás campos con datos válidos
  3. Hacer clic en "Reserve Now"
- **Resultado esperado**: El sistema debe mostrar un mensaje de error indicando que el nombre debe contener solo letras

---

### 🔹 TC007 - Validación de campo lastName
- **Precondición**: El usuario se encuentra en el formulario de reserva, tras haber seleccionado una habitación desde la sección “Our Rooms”
- **Pasos**:
  1. Completar el campo lastName con números
  2. Completar los demás campos con datos válidos
  3. Hacer clic en "Reserve Now"
- **Resultado esperado**: El sistema debe mostrar un mensaje de error indicando que el nombre debe contener solo letras

---
### 🔹 TC008 - Validación de campo teléfono 
- **Precondición**: El usuario se encuentra en el formulario de reserva, tras haber seleccionado una habitación desde la sección “Our Rooms”
- **Pasos**:
  1. Completar el campo teléfono con menos de 11 caracteres numéricos
  2. Completar los demás campos con datos válidos
  3. Hacer clic en "Reserve Now"
- **Resultado esperado**: Aparece mensaje de error indicando que el número debe comprender entre los 11 y 21 caracteres, y debe estar compuesto únicamente por números

---

### 🔹 TC009 - Fecha pasada como check-in
- **Precondición**: El usuario se encuentra en el formulario de reserva, tras haber seleccionado una habitación desde la sección “Our Rooms”
- **Pasos**:
  1. Ingresar una fecha de check-in anterior a la actual
  2. Completar el resto del formulario
  3. Hacer clic en "Reserve Now"
- **Resultado esperado**: El sistema muestra error e impide continuar

---

### 🔹 TC010 - Validar reserva en panel admin
- **Precondición**: Reserva exitosa realizada previamente
- **Pasos**:
  1. Ingresar al panel admin (`admin/password`)
  2. Navegar a la sección de reservas
  3. Buscar la reserva creada
- **Resultado esperado**: Se visualiza correctamente con los datos ingresados


---

### 🔹 TC011 - Visualización de disponibilidad de la habitación elegida
- **Precondición**: Una reserva existente para una habitación específica en determinada fecha
- **Pasos**:
  1. Intentar crear una reserva para la misma habitación y comprobar que se visualiza las fechas en la que no esta disponible
- **Resultado esperado**: El sistema debe mostrar que la habitación no esta disponible


---

### 🔹 TC012 - Doble reserva para la misma fecha y habitación
- **Precondición**: Una reserva existente para una habitación específica en determinada fecha
- **Pasos**:
  1. Intentar crear una segunda reserva para la misma habitación y fecha
  2. Hacer clic en "Reserve Now"
- **Resultado esperado**: El sistema debe impedir la reserva y mostrar un mensaje de error

---

### 🔹 TC013 - Doble reserva para la misma fecha y distinta habitación
- **Precondición**: Una reserva existente para una habitación específica en determinada fecha
- **Pasos**:
  1. Intentar crear una segunda reserva para una habitación distinta y misma fecha
  2. Hacer clic en "Reserve Now"
- **Resultado esperado**: Se muestra mensaje de éxito y la reserva se registra en el sistema

---


