# 🧾 User Story: Enviar un mensaje desde el formulario de contacto

**ID**: US003  
**Nombre**: Contactar al hotel a través del formulario de contacto

> **Como** visitante del sitio Shady Meadows B&B  
> **Quiero** poder enviar un mensaje desde el formulario de contacto  
> **Para** comunicarme fácilmente con el equipo responsable del sitio ante dudas, consultas o problemas

---

## ✅ Criterios de Aceptación

```gherkin
Feature: Enviar mensaje desde el formulario de contacto

  Scenario: El usuario envía un mensaje con todos los campos completados correctamente
    Given El usuario se encuentra en la sección "Contact"
    When Completa los campos de Name, Email, Phone, Subject y Message correctamente
    And Hace clic en "Submit"
    Then El sistema debe mostrar un mensaje de confirmación indicando que el mensaje fue enviado correctamente

  Scenario: El sistema valida que todos los campos del formulario son obligatorios
    Given El usuario se encuentra en la sección "Contact"
    When Intenta enviar el formulario sin completar ningún campo
    Then El sistema debe mostrar un mensaje de error indicando que Name, Email, Phone, Subject y Message son campos obligatorios


  Scenario: El usuario intenta enviar el formulario sin completar uno o más campos obligatorios
    Given El usuario se encuentra en la sección "Contact"
    When Omite uno o más campos requeridos y hace clic en "Submit"
    Then El sistema debe mostrar mensajes de error indicando los campos faltantes

  Scenario: El sistema valida el contenido del campo nombre
    Given El usuario completa el campo "Name"
    When Intenta ingresar números o símbolos
    Then El sistema no lo permite ya que es un input del tipo texto

  Scenario: El usuario ingresa un correo electrónico con formato inválido
    Given El usuario está completando el campo de email
    When Ingresa un texto sin formato de correo válido
    Then El sistema debe mostrar un mensaje de error 

  Scenario: El sistema valida la longitud del mensaje
    Given El usuario completa el campo "Message"
    When Ingresa un texto de menos de 20 caracteres o más de 2000
    Then El sistema debe mostrar un mensaje de error indicando la longitud permitida

  Scenario: El sistema valida la longitud del asunto
    Given El usuario completa el campo "Subject"
    When Ingresa un texto de menos de 5 caracteres o más de 100
    Then El sistema debe mostrar un mensaje de error indicando la longitud permitida

  Scenario: El sistema valida la longitud del teléfono
    Given El usuario completa el campo "Phone"
    When Ingresa un número con menos de 11 o más de 21 caracteres numéricos
    Then El sistema debe mostrar un mensaje de error indicando la longitud permitida

```
---

## 🧪 Casos de Prueba 

### 🔹 TC001 - Envío exitoso del formulario de contacto
- **Precondición**: El usuario se encuentra en la sección "Contact"
- **Pasos**:
  1. Completar los campos de Name, Email, Phone, Subject y Message con datos válidos
  2. Hacer clic en "Submit"
- **Resultado esperado**: El sistema muestra un mensaje de confirmación indicando que el mensaje fue enviado correctamente

---

### 🔹 TC002 - Envío del formulario con campos vacíos
- **Precondición**: El usuario se encuentra en la sección "Contact"
- **Pasos**:
  1. Dejar vacío al menos un campo obligatorio
  2. Hacer clic en "Submit"
- **Resultado esperado**: El sistema muestra mensajes de error indicando que debe completar los campos vacíos

---

### 🔹 TC003 - Validación de todos los campos como obligatorios
- **Precondición**: El usuario se encuentra en la sección "Contact"
- **Pasos**:
  1. Dejar vacío todos los campos
  2. Hacer clic en "Submit" tras cada prueba
- **Resultado esperado**: El sistema muestra un mensaje de error indicando que los campos son obligatorios y la longitud que deben tener (cuando corresponde)

---

### 🔹 TC004 - Validación de formato de email inválido
- **Precondición**: El usuario se encuentra en la sección "Contact"
- **Pasos**:
  1. Completar el campo email con un texto sin formato válido (ejemplo: "correo@prueba")
  2. Completar los demás campos con datos válidos
  3. Hacer clic en "Submit"
- **Resultado esperado**: El sistema muestra un mensaje de error para el campo email

---

### 🔹 TC005 - Validación de longitud del mensaje
- **Precondición**: El usuario se encuentra en la sección "Contact"
- **Pasos**:
  1. Completar el campo mensaje con un texto de menos de 20 caracteres o mas de 2000 caracteres
  2. Completar los demás campos con datos válidos
  3. Hacer clic en "Submit"
- **Resultado esperado**: El sistema muestra un mensaje de error indicando la longitud mínima y máxima permitida

---

### 🔹 TC006 - Validación de longitud del asunto
- **Precondición**: El usuario se encuentra en la sección "Contact"
- **Pasos**:
  1. Completar el campo asunto con un texto de menos de 5 caracteres y mas de 100 caracteres
  2. Completar los demás campos con datos válidos
  3. Hacer clic en "Submit"
- **Resultado esperado**: El sistema muestra un mensaje de error indicando la longitud mínima y máxima permitida

---

### 🔹 TC007 - Validación de longitud del teléfono
- **Precondición**: El usuario se encuentra en la sección "Contact"
- **Pasos**:
  1. Completar el campo teléfono con menos de 11 caracteres numéricos
  2. Completar los demás campos con datos válidos
  3. Hacer clic en "Submit"
- **Resultado esperado**: El sistema muestra un mensaje de error indicando que el teléfono debe tener entre 11 y 21 caracteres

---

### 🔹 TC008 - Validación del contenido del campo nombre
- **Precondición**: El usuario se encuentra en la sección "Contact"
- **Pasos**:
  1. Completar el campo nombre con números o símbolos (ejemplo: "1234##")
  2. Completar los demás campos con datos válidos
  3. Hacer clic en "Submit"
- **Resultado esperado**: El sistema no permite el ingreso de caracteres distintos a letras

---
