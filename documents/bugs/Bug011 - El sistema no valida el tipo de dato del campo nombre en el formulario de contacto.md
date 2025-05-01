# 🐞 BUG011 - El sistema permite ingresar números o símbolos en el campo nombre del formulario de contacto

- **Funcionalidad**: Contact - Formulario de contacto
- **Severidad**: Baja
- **Prioridad**: Media
- **Estado**: Abierto
- **Reportado por**: Claudia Fernández
- **Fecha**: 2025-05-01

## 🔍 Descripción
El sistema no valida que el campo nombre contenga únicamente letras. Actualmente es posible completar el campo nombre con números o símbolos (ejemplo: "1234##") y enviar el formulario sin que se muestre ningún mensaje de error, lo que permite almacenar un dato inválido.

## 🔁 Pasos para reproducir
1. Ingresar al sitio Shady Meadows B&B
2. Ir a la sección "Contact"
3. Completar el campo nombre con "1234##"
4. Completar los demás campos con datos válidos
5. Hacer clic en "Submit"

## ✅ Resultado Esperado
El sistema debe validar que el campo nombre contenga solo letras. Si se ingresan números o símbolos, debe mostrar un mensaje de error e impedir el envío del formulario.

## ❌ Resultado Obtenido
El sistema permite enviar el formulario aceptando valores no alfabéticos en el campo nombre sin mostrar errores.

---

## 🔗 Asociaciones

- **User Story**: [US003 - Enviar un mensaje desde el formulario de contacto](../features/US003_contacto_enviar_mensaje.md)
- **Caso de Prueba**: TC008 - Validación del contenido del campo nombre

