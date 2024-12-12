# Proyecto-DJK

Proyecto de DJK hecho por Moises, Carlos y José Manuel

---

# Selección de Modelo de servicio adecuado

![Image of cloud with service model examples](/images/mainimage.jpeg)

### ¿Qué es un Modelo de Servicio?

Es la forma en que una organización ofrece y gestiona sus servicios a los clientes (SaaS, PaaS, IaaS, FaaS, entre otros)

## Selección: FaaS (Function as a Service)

### ¿De qué se trata FaaS?

Tipo de computación en la nube sin preocuparse por la gestión de servidores. Es ideal para aplicaciones ligeras. Este tipo de tecnología funciona de la siguiente manera: nosotros al contrastar el servicio, damos nuestra confianza a la empresa de computación, la cual nos proporciona sistemas remotos potentes y totalmente capaces de poder realizar las tareas que necesitamos

### ¿Por qué es el modelo ideal para este problema?

- Coste optimizado: Pago por ejecución, sin costos asociados a la propia infraestructura o tiempo de inactividad. Al usar equipos proporcionados por la empresa con la que estamos trabajando, evitamos el tener que adquirir de forma física estos equípos. A su vez, eliminamos la necesidad de ocupar espacio con los mismos.

- Escalabilidad: Responde automáticamente al volumen que queramos adquirir, pudiendo mejorar siempre que se necesite dichos equipos, con el fin de mejorar la producción de la empresa.

- Fácil implementación: Desarrollo rápido, gracias a que la empresa de FaaS con la que trabajamos, la cual se encarga de toda la instalación en los dispositivos de nuestra empresa

- Flexibilidad: Compatible con diversas herramientas, entre ellos muchos de los más famosos lenguajes de programación, tales como: Python, JavaScript, Java o Go. 

- Simplicidad administrativa: Administrada por el proveedor el cual implementa todas las configuraciones necesarias para que podamos usar de forma remota todos los servicios necesarios

---

# Selección de 3 plataformas que ofrecen "Funciones como servicio"

### Existe una gran cantidad de plataformas que proveen dicho modelo de servicio, como por ejemplo:

- AWS Lambda

- Google Cloud Functions

- Azure Functions

- IBM Cloud Functions

- Oracle Functions

- Alibaba Cloud

- OpenFaaS

- Cloudflare Workers

### No obstante, en nuestro caso hemos elegido las siguientes tres plataformas:

| Platform             | Scalability   | Costs                      | Implementation Difficulty                      | URL                                                  |
| -------------------- | ------------- | -------------------------- | ---------------------------------------------- | ---------------------------------------------------- |
| **AWS Lambda**       | **Excelente** | **Bajo (Gratis hasta 1M)** | **Alta, pero requiere experiencia con AWS**    | **https://aws.amazon.com/es/lambda/**                |
| **Google Functions** | Excelente     | Bajo (Gratis hasta 1M)     | Muy alta                                       | https://cloud.google.com/functions                   |
| **Azure Functions**  | Excelente     | Bajo (Gratis hasta 1M)     | Alta, especialmente para usuarios de Microsoft | https://azure.microsoft.com/es-es/products/functions |

---

## AWS Lambda

#### Características

1. Compatible con diferentes leguanjes de programación (Node.js, Python, Go, Java, entre otros)

2. Tiempo muy bajo de ejecución máxima de 15 minutos (Si la tarea a ejecutar tarda más de 15 minutos, nuestra plataforma detendrá idependientemente de si ha terminado o no)

##### Ventajas

1. Escalabilidad automática

2. Pago por uso

3. Integración con el ecosistema AWS

#### Desventajas

1. Tiempo de ejecución limitado

2. Latencia

3. Dependencia del ecosistema AWS

---

## Google Functions

#### Caracterísiticas

1. **Ejecución sin servidor (Serverless)**. Permite ejecutar código sin necesidad de gestionar un servidor. Solo se paga por el tiempo de ejecución real, eliminando la necesidad de mantener servidores constantemente activos.

2. **Integración con el ecosistema de Google Cloud**. Está integrado con otros servicios de Google Cloud, lo que facilita la construcción de aplicaciones escalables.

#### Ventajas

1. Escalabilidad automática

2. Costos basados en uso

3. Desarrollo rápido y simplificado

#### Desventajas

1. Latencia de arranque _en frio_

2. Límites de tiempo y recursos

3. Dependencia de la infraestructura de Google

---

### Análisis Económico

**AWS Lambda**

La propia web de AWS Lambda nos proporciona un **Pricing Calculator** el cual nos permite a placer elegir y configurar los servicios que deseemos. Éste hará los cálculos necesarios teniendo en cuenta sus estándares de precios, en nuestro caso, "solo" es necesario insertar los datos y configuración.

## Servicios Necesarios

Utilizaremos un total de **4 servicios** en la siguiente plataforma:

1. AWS Lambda

2. SNS

3. DynamoDB (NoSQL)

4. SQS (Colas de Mensajes)

---

![AWS Lambda Configuration Image](/images/awsconfig.png)

A modo de resumen, en la siguiente tabla se indican los datos necesarios e insertados en la imágen anterior:

| Arquitectura | Cantidad de solicitudes (U/mes) | Duración Cada Solicitud (ms) | Memoria Asignada (GB) | Almacenamiento Efímero Asignado (MB) |
| ------------ | ------------------------------- | ---------------------------- | --------------------- | ------------------------------------ |
| x86          | 1000                            | 100                          | 6                     | 512                                  |

![AWS Lambda Configuration Image - SNS](/images/snsconfig.png)
