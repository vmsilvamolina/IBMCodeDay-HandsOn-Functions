# IBM Cloud Functions - Workshop

## Prefacio

Antes de comenzar, hay que tener en cuenta que IBM Cloud Functions antes se llamaba IBM Bluemix OpenWhisk. ¿Y qué tiene de especial el nombre anterior? Que básicamente nos dejaba ver que la plataforma sobre la que está construida la solución de Serverlesss de IBM es **Apache OpenWhisk**. Hoy por hoy Apache OpenWhisk  se refiere al proyecto de código abierto disponible en Apache, mientras que **IBM Cloud Functions** se refiere a la plataforma serverless de IBM que se ejecuta sobre la nube pública de IBM. IBM Cloud Functions está completamente basado en Apache OpenWhisk ya que ambos proyectos comparten la misma base *core* de código.

A modo de simplificar, vamos a llamar simplemente **Functions** a la solución IBM Cloud Functions.

## Conceptos sobre Serverless y IBM Cloud Functions

***Serverless computing*** (llamado también ***Functions-as-a-Service*** o ***FaaS***) hace referencia al modelo donde la existencia de servidores es totalmente abstracta, es decir, no tenemos que preocuparnos de ellos, simplemente del código. Los desarrolladores se liberan de la necesidad de preocuparse por los detalles de infraestructura y operación de bajo nivel; como la escalabilidad, la alta disponibilidad, la seguridad de la infraestructura, etc. Por lo tanto, *serverless* se trata esencialmente de reducir los esfuerzos de mantenimiento para permitir a los desarrolladores concentrarse rápidamente en el desarrollo de código de valor agregado.

> Serverless simplifica el desarrollo de aplicaciones nativas en la nube, especialmente soluciones orientadas a microservicios que descomponen aplicaciones complejas en módulos pequeños e independientes que se pueden intercambiar fácilmente.

Así es que *serverless* no se refiere a una tecnología específica; en cambio, si se refiere a los conceptos subyacentes al modelo descrito anteriormente. Sin embargo, recientemente han surgido algunas soluciones prometedoras que facilitan los enfoques de desarrollo que siguen el modelo sin servidor, como IBM Cloud Functions.

Functions es un servicio cloud-first de programación event-based distribuido y representa una plataforma FaaS que le permite ejecutar código en respuesta a un evento.


El mismo proporciona el modelo de operaciones y despliegue mencionado anteriormente, con un esquema de precios granular a cualquier escala brindando exactamente los recursos, ni más ni menos, que se necesita y solo se cobra por el código que realmente se encuentra en ejecución. Ofrece un modelo de programación flexible. incluído soporte para lenguajes como **Java**, **JavaScript**, **PHP**, **Python** y **Swift** e incluso la ejecución de código personalizada a través de contenedores **Docker**. Esto permite que pequeños equipos ágiles reutilicen las habilidades existentes y se desarrollen de manera adecuada. También proporciona herramientas para encadenar declarativamente los bloques de construcción que ha desarrollado.

En resumen, IBM Cloud Functions proporciona:

* Un rico conjunto de bloques de construcción que puedes pegar/unir fácilmente
* La capacidad de centrarse más en la lógica empresarial de valor agregado y menos en los detalles de infraestructura y operaciones de bajo nivel.
* La capacidad de encadenar fácilmente microservicios a través de secuencias.

El modelo (básico) de Functions consta de tres conceptos:

* `Trigger`, una clase de eventos que pueden suceder.
* `Action`, un controlador de eventos: código que se ejecuta en respuesta a un evento y
* `Rule`, una asociación entre un trigger y una action.

Los servicios definen los eventos que se emiten como triggers, y los desarrolladores definen las actions para manejar los eventos.

## Requisitos

1. Tener instalado algún editor de código como VSCode, Atom, Notepad++.
2. Instalar el CLI de IBM Cloud: [instrucciones aquí](https://cloud.ibm.com/docs/cli?topic=cloud-cli-getting-started).
3. Clonar el repositorio:
```git clone https://github.com/vmsilvamolina/IBMCodeDay-HandsOn-Functions.git```
o descargar el código desde el siguiente [enlace](https://github.com/vmsilvamolina/IBMCodeDay-HandsOn-Functions/archive/master.zip).
4. Tener una cuenta en IBM Cloud.