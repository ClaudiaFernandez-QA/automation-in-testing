# 🧾 User Story: Consultar mensajes y notificaciones de reservas en el panel de administración

**ID**: US005  
**Nombre**: Ver los mensajes y notificaciones de reservas en el panel Admin

> **Como** administrador del sitio Shady Meadows B&B  
> **Quiero** poder consultar los mensajes y notificaciones recibidas en el panel de administración  
> **Para** gestionar las consultas de usuarios y verificar las reservas realizadas

---

## ✅ Criterios de Aceptación

```gherkin
Feature: Consultar mensajes y notificaciones en el panel de administración

  Scenario: El administrador visualiza la lista de mensajes y notificaciones
    Given El administrador accede a la sección "Messages" del panel Admin 
    When Se cargan los mensajes y notificaciones recibidas
    Then El sistema debe mostrar una lista con el nombre y asunto de cada mensaje o notificación

  Scenario: El administrador ve el número de mensajes nuevos en la pestaña "Messages"
    Given El administrador se encuentra en el panel Admin
    When Hay mensajes o notificaciones nuevas
    Then El sistema debe mostrar en la pestaña "Messages" un número que indica la cantidad de mensajes no leídos

  Scenario: El administrador consulta el detalle de un mensaje
    Given El administrador se encuentra en la lista de mensajes
    When Hace clic sobre un mensaje o notificación
    Then El sistema debe abrir un modal con los datos completos (nombre, email, teléfono, asunto, mensaje)

  Scenario: No hay mensajes ni notificaciones para mostrar
    Given El administrador accede a la sección "Messages"
    When No existen mensajes ni notificaciones registrados
    Then El sistema debe mostrar un mensaje indicando que no hay mensajes disponibles
```

---

## 🧪 Casos de Prueba Manuales

### 🔹 TC001 - Visualización de la lista de mensajes y notificaciones
- **Precondición**: El administrador accedió al panel Admin y hay mensajes/notificaciones registradas
- **Pasos**:
  1. Ingresar al Admin Panel con credenciales válidas
  2. Hacer clic en la pestaña "Messages"
- **Resultado esperado**: Se visualiza una lista con el nombre y asunto de cada mensaje o notificación

---

### 🔹 TC002 - Visualización del contador de mensajes nuevos
- **Precondición**: Existen mensajes o notificaciones nuevas sin visualizar
- **Pasos**:
  1. Ingresar al panel Admin  con credenciales válidas
  2. Observar la pestaña "Messages" sin hacer clic
- **Resultado esperado**: Se muestra un número indicando la cantidad de mensajes nuevos

---

### 🔹 TC003 - Consulta del detalle de un mensaje
- **Precondición**: Hay al menos un mensaje o notificación en la lista
- **Pasos**:
  1. Ingresar al panel Admin con credenciales válidas
  2. Hacer clic en la pestaña "Messages"
  3. Hacer clic en uno de los mensajes de la lista
- **Resultado esperado**: Se abre un modal mostrando nombre, email, teléfono, asunto y mensaje completo

---

### 🔹 TC004 - Visualización de mensaje de lista vacía
- **Precondición**: No existen mensajes ni notificaciones registrados
- **Pasos**:
  1. Ingresar al panel Admin con credenciales válidas
  2. Hacer clic en la pestaña "Messages"
- **Resultado esperado**: El sistema muestra un mensaje indicando que no hay mensajes disponibles

---

