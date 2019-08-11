# IBM Cloud Functions - Bash

**Objetivos:** Crear una *action* utilizando Bash por medio de Docker.

`ibmcloud fn action create skeleton --docker openwhisk/dockerskeleton`


`ibmcloud fn action invoke skeleton --blocking --result`

Crear el archivo **exec** con el siguiente contenido:

```
#!/bin/bash
echo "{ \"hello\": \"ran without a docker pull!\" }"`
```

Modificarle los permisos:

`chmod u+x exec`

Hacer una prueba ejecutando el archivo:

`./exec`

Comprimir el archivo:

`zip exec.zip exec`

Creamos la función a partir de una imagen docker:

`ibmcloud fn action create bash exec.zip --docker`

Invocamos la función creada:

`ibmcloud fn action invoke bash --blocking --result`