# 🐞 BUG010 - El sistema permite ingresar letras o símbolos en el campo teléfono del formulario de contacto

- **Funcionalidad**: Contact - Formulario de contacto
- **Severidad**: Baja
- **Prioridad**: Media
- **Estado**: Abierto
- **Reportado por**: Claudia Fernández
- **Fecha**: 2025-05-01

## 🔍 Descripción
El sistema valida correctamente la longitud mínima y máxima del campo teléfono (11 a 21 caracteres), pero no valida que los caracteres ingresados sean exclusivamente numéricos. Actualmente es posible completar el campo teléfono con letras o símbolos y enviar el formulario sin mostrar ningún mensaje de error.

## 🔁 Pasos para reproducir
1. Ingresar al sitio Shady Meadows B&B
2. Ir a la sección "Contact"
3. Completar el campo teléfono con "123abcdefghi##"
4. Completar los demás campos con datos válidos
5. Hacer clic en "Submit"

## ✅ Resultado Esperado
El sistema debe validar que el campo teléfono contenga solo caracteres numéricos. Si se ingresan letras o símbolos, debe mostrar un mensaje de error e impedir el envío del formulario.

## ❌ Resultado Obtenido
El sistema permite enviar el formulario aceptando valores alfanuméricos o con símbolos en el campo teléfono sin mostrar errores.

---

## 🔗 Asociaciones

- **User Story**: [US003 - Enviar un mensaje desde el formulario de contacto](../features/US003_contacto_enviar_mensaje.md)
- **Caso de Prueba**: TC007 - Validación del campo teléfono

