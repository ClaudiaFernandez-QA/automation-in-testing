# 🧾 User Story: Acceder al Panel de Administración

**ID**: US004  
**Nombre**: Login al Admin Panel

> **Como** administrador del sitio Shady Meadows B&B  
> **Quiero** poder acceder al panel de administración ingresando usuario y contraseña válidos  
> **Para** gestionar las habitaciones, mensajes, reportes y configuraciones del sitio

---

## ✅ Criterios de Aceptación

```gherkin
Feature: Acceso al panel de administración

  Scenario: Acceso exitoso con credenciales válidas
    Given El usuario se encuentra en la página de login de Admin
    When Ingresa un usuario y contraseña válidos
    And Hace clic en "Log in"
    Then El sistema debe permitir el acceso al panel de administración y mostrar la pantalla principal

  Scenario: Acceso fallido con credenciales inválidas
    Given El usuario se encuentra en la página de login de Admin
    When Ingresa un usuario o contraseña inválidos
    And Hace clic en "Log in"
    Then El sistema debe mostrar un mensaje de error indicando que las credenciales son incorrectas

  Scenario: Campos obligatorios vacíos en el login
    Given El usuario se encuentra en la página de login de Admin
    When Intenta iniciar sesión dejando vacío el campo de usuario o contraseña
    Then El sistema debe mostrar un mensaje de error indicando que ambos campos son obligatorios
```

---

## 🧪 Casos de Prueba 

### 🔹 TC001 - Login exitoso con credenciales válidas
- **Precondición**: El usuario se encuentra en la página de login de Admin
- **Pasos**:
  1. Ingresar usuario válido en el campo de username (admin)
  2. Ingresar contraseña válida en el campo de password (password)
  3. Hacer clic en "Log in"
- **Resultado esperado**: El sistema permite el acceso al panel de administración y muestra la pantalla principal

---

### 🔹 TC002 - Login fallido con credenciales inválidas
- **Precondición**: El usuario se encuentra en la página de login de Admin
- **Pasos**:
  1. Ingresar usuario inválido o contraseña inválida
  2. Hacer clic en "Log in"
- **Resultado esperado**: El sistema muestra un mensaje de error indicando que las credenciales son incorrectas

---

### 🔹 TC003 - Login con campo de usuario vacío
- **Precondición**: El usuario se encuentra en la página de login de Admin
- **Pasos**:
  1. Dejar vacío el campo de usuario
  2. Ingresar una contraseña válida
  3. Hacer clic en "Log in"
- **Resultado esperado**: El sistema muestra un mensaje de error indicando que el campo de usuario es obligatorio

---

### 🔹 TC004 - Login con campo de contraseña vacío
- **Precondición**: El usuario se encuentra en la página de login de Admin
- **Pasos**:
  1. Ingresar un usuario válido
  2. Dejar vacío el campo de contraseña
  3. Hacer clic en "Log in"
- **Resultado esperado**: El sistema muestra un mensaje de error indicando que el campo de contraseña es obligatorio

---

