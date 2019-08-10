# IBM Cloud Functions - Hello world!

**Objetivos:** Crear una *action*, invocarla, analizar la respuesta y ver cómo se administra (edita/elimina) una función.

## Hello world desde una función

1. Crear una *action*:

`ibmcloud fn action create helloWorld .\helloWorld.js`

2. Verificar que se encuentre creada:

`ibmcloud fn action list`

3. Invocar:

`ibmcloud fn action invoke helloWorld --blocking`

>Nota: El parámetro **--blocking**...

4. Invocar filtrando el mensaje (con una *regular expression*):

`(ibmcloud fn action invoke helloWorld --blocking | Select-String -Pattern '(?:"message": ")(.*)("$)').Matches.Groups[1].Value`



`curl -X POST -H 'Content-type: application/json' --data '{"text":"Hola desde cURL!"}' https://hoo.slack.com/services/TBK11E5UM/BM9NCTQ5D/MQnMXPiPvb5XPpmZhS5pr8Mp`

`ibmcloud fn action invoke /whisk.system/slack/post --param url https://hooks.slack.com/services/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 --param channel '#vmsilvamolina' --param text "Hola desde IBM Cloud Functions!"`


## Extra: Utilities

* IBM Cloud Functions ofrece por defecto algunas utilidades empaquetadas, como por ejemplo, utilizar **echo** para imprimir un mensaje. Para invocar esta acción, simplemente será necesario ejecutar la siguiente línea de código:

`ibmcloud fn action invoke whisk.system/utils/echo -p message "Hola!" --result`


* Secuencia?

* Para listar todas las utilidades:

`ibmcloud fn package get --summary /whisk.system/utils`


