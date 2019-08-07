# IBM Cloud Functions - Hello world!

1. Crear una *action*:

```ibmcloud fn action create helloWorld .\helloWorld.js```

2. Verificar que se encuentre creada:

```ibmcloud fn action list```

3. Invocar:

```ibmcloud fn action invoke helloWorld --blocking```