# IBM Cloud Functions - Bash

**Objetivos:** Crear una *action* utilizando Bash por medio de Docker.

1. Creamos una action a partir de una imagen base de Docker:

`ibmcloud fn action create skeleton --docker openwhisk/dockerskeleton`

2. Invocamos la función para ver la salida:

`ibmcloud fn action invoke skeleton --blocking --result`

3. Crear el archivo **exec** con el siguiente contenido:

```
#!/bin/bash
echo "{ \"hola\": \"Hola desde Bash con Docker!\" }"
```

Donde ese string será la salida de la ejecución de la función.

4. Modificarle los permisos:

`chmod u+x exec`

5. Hacer una prueba ejecutando el archivo:

`./exec`

6. Comprimir el archivo:

`zip exec.zip exec`

7. Creamos la función a partir de una imagen docker, utilizando el "script" de bash:

`ibmcloud fn action create bash exec.zip --docker openwhisk/dockerskeleton`

8. Invocamos la función creada:

`ibmcloud fn action invoke bash --blocking --result`

9. Para modificar la action, primero modificamos el archivo exec y volvemos a ejecutar el *paso 6*.


10. Lo siguiente es cargar el cambio en la action, ejecutando el comando **update**:

`ibmcloud fn action update bash exec.zip --docker openwhisk/dockerskeleton`

11. Volvemos a invocar:

`ibmcloud fn action invoke bash --blocking --result`