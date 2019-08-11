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


## Extra: Utilities

* IBM Cloud Functions ofrece por defecto algunas utilidades empaquetadas, como por ejemplo, utilizar **echo** para imprimir un mensaje. Para invocar esta acción, simplemente será necesario ejecutar la siguiente línea de código:

`ibmcloud fn action invoke whisk.system/utils/echo -p message "Hola!" --result`


* Adicional a lo anterior, también es posible combinar acciones dentro de una secuencia. La secuencia se tiene que definir en un orden lógico según el requerimiento.Por ejemplo, se puede utilizar **split** y **sort** para convertir una línea de texto en un array ordenado.

`ibmcloud fn action create sequenceAction --sequence /whisk.system/utils/split,/whisk.system/utils/sort`

`ibmcloud fn action invoke --result sequenceAction --param payload "Esto va al medio\nÚltima parte\nAl principio"`

En la salida, debería verse algo como ésto:

```
{
    "length": 3,
    "lines": [
        "Al principio",
        "Esto va al medio",
        "Última parte"
    ]
}
```

* Para listar todas las utilidades:

`ibmcloud fn package get --summary /whisk.system/utils`

Donde también se despliega el o los parámetros disponibles.