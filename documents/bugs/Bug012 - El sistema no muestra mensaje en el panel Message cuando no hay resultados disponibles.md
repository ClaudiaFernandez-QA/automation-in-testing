# 🐞 BUG012 - El sistema no muestra mensaje cuando no hay mensajes ni notificaciones en la sección Messages

- **Funcionalidad**: Admin Panel > Messages
- **Severidad**: Baja
- **Prioridad**: Baja
- **Estado**: Abierto
- **Reportado por**: Claudia Fernández
- **Fecha**: 2025-05-01

## 🔍 Descripción
Cuando no existen mensajes ni notificaciones registradas, el sistema simplemente muestra una lista vacía sin ningún mensaje o indicación al administrador. Esto puede generarle confusión al usuario.

## 🔁 Pasos para reproducir
1. Ingresar al Admin Panel con credenciales válidas
2. Hacer clic en la pestaña "Messages"
3. Comprobar que no existan mensajes ni notificaciones registrados

## ✅ Resultado Esperado
El sistema debe mostrar un mensaje claro indicando que no hay mensajes ni notificaciones disponibles.

## ❌ Resultado Obtenido
El sistema solo muestra una lista vacía, sin ningún mensaje o alerta.

---

## 🔗 Asociaciones

- **User Story**: [US005 - Consultar mensajes y notificaciones de reservas en el panel de administración](../features/US005_admin_messages.md)
- **Caso de Prueba**: TC004 - Visualización de mensaje de lista vacía

