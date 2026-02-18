# Redactor Jurídico (Interoperable)

Este proyecto contiene un flujo de trabajo de **n8n** diseñado para asistir en la redacción de documentos jurídicos, específicamente memorándums de hechos, utilizando inteligencia artificial y automatización.

## Descripción del Flujo

El flujo de trabajo automatiza el proceso de recepción de información, análisis legal, generación de documentos y notificación. Los pasos principales son:

1.  **Entrada de Datos (Webhook)**: Recibe información del caso a través de un webhook (configurado para WhatsApp/Telegram).
2.  **Clasificador Legal (OpenAI)**: Un modelo de IA (GPT-4.1-nano) actúa como un asistente profesional legal (conforme a las leyes de El Salvador) para interpretar y clasificar la solicitud.
3.  **Parser**: Procesa la respuesta del clasificador para estructurar los datos.
4.  **Memorandum de Hechos (OpenAI)**: Genera un memorándum de hechos basado en la información clasificada.
5.  **Registro en Google Sheets**: Guarda la información relevante del caso y el memorándum en una hoja de cálculo de Google.
6.  **Notificación por Correo (Gmail)**: Envía un correo electrónico con el resultado o confirmación a una dirección específica.

## Requisitos Previos

Para utilizar este flujo de trabajo en n8n, necesitarás:

-   Una instancia de **n8n** (local o en la nube).
-   Credenciales configuradas en n8n para:
    -   **OpenAI** (API Key).
    -   **Google Sheets** (OAuth2).
    -   **Gmail** (OAuth2).
-   Un Webhook configurado en tu proveedor de mensajería (WhatsApp/Telegram) apuntando al nodo de entrada.

## Instalación

1.  Importa el archivo `Redactor Jurídico (Interoperable).json` en tu instancia de n8n.
2.  Configura las credenciales indicadas (OpenAI, Google, Gmail).
3.  Asegúrate de que el ID de la hoja de cálculo de Google Sheets sea accesible y tenga los encabezados correctos.
4.  Activa el flujo de trabajo.

## Uso

Envía una solicitud POST al webhook de entrada con la información del caso legal. El sistema procesará automáticamente la información y generará el memorándum.
