# IBM Cloud Functions - Slack

**Objetivos:** Invocar una *action* por defecto para enviar un mensaje a Slack.

1. Acceder al siguiente enlace e iniciar sesión:

https://api.slack.com/apps

2. Volvemos a acceder a la URL anterior, ya con el usuario logueado.

3. Seleccionar el botón `Create New App`.
   1. Completar el nombre y seleccionar el espacio de trabajo.
   2. Create App.
   3. Debajo de la sección  `Buildings Apps for Slack`, seleccionar la opción **Incoming Webhooks**
   4. Activar la opción **Incoming Webhook**.
   5. Seleccionar el botón al final de la página **Add New Webhook to Workspace**.
   6. En el campo `Post to` seleccionar el canal o la persona a la que queremos aplicar está app.
   7. Seleccionar **Install**.

4. En la sección **Webhook URLs for Your Workspace** vamos a tener, ahora sí, completa la sección con un ejemplo para utilizar desde cURL:

`curl -X POST -H 'Content-type: application/json' --data '{"text":"Hola desde cURL!"}' https://hooks.slack.com/services/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`

5. Ahora estamos en condiciones de crear una **action**, utilizando una de los paquetes disponibles en el namespace `whisk.system` destinado para trabajar con Slack directamente:

`ibmcloud fn action invoke /whisk.system/slack/post --param url https://hooks.slack.com/services/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 --param channel '#vmsilvamolina' --param text "Hola desde IBM Cloud Functions!"`

## Próximo paso

3. [Bash](https://github.com/vmsilvamolina/IBMCodeDay-HandsOn-Functions/blob/master/3_Bash/bash.md)