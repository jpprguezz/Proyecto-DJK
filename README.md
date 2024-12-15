# Proyecto-DJK

Proyecto de DJK hecho por Moises, Carlos y José Manuel

---

# Selección de Modelo de servicio adecuado

![Image of cloud with service model examples](/images/mainimage.jpeg)

### ¿Qué es un Modelo de Servicio?

Es la forma en que una organización ofrece y gestiona sus servicios a los clientes (SaaS, PaaS, IaaS, FaaS, entre otros)

## Selección: FaaS (Function as a Service)

### ¿De qué se trata FaaS?

Tipo de computación en al nube sin preocuparse por la gestión de servidores. Es ideal para aplicaciones ligeras

### ¿Por qué es el modelo ideal para este problema?

- Coste optimizado: Pago por ejecución, sin costos asociados a la propia infraestructura o tiempo de inactividad.

- Escalabilidad: Responde automáticamente al volumen que queramos adquirir.

- Fácil implementación: Desarrollo rápido.

- Flexibilidad: Compatible con diversas herramientas.

- Simplicidad administrativa: Administrada por el proveedor.

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

Utilizaremos un total de **3 servicios** en la siguiente plataforma:

1. AWS Lambda

2. SNS

3. SQS (Colas de Mensajes)

---

![AWS Lambda Configuration Image](/images/awsconfig.png)

Datos a tener en cuenta para dicho **Pricing Calculator**

1. Arquitectura --> Tipo de procesador utilizado y que sea compatible.

2. Cantidad de solicitudes que recibirá en este caso el restaurante al **mes**

3. Duración de cada solicitud (ms) --> Tiempo de ejecución desde que comienza hasta que termina la función.

4. Cantidad de memoria que tendrá asignada (GB) --> AUmentar la memoria no solo incrementa el costo por ejecución, sino que también puede mejorar el rendimiento.

5. Cantidad de almacenamiento efímero asignado (MB) --> Almacenamiento temporal. Es útil para almacenar datos temporales, como para ciertas aplicaciones, lo cuál, aumentará el costo.


A modo de resumen, en la siguiente tabla se indican los datos necesarios e insertados en la imágen anterior:

| Arquitectura | Cantidad de solicitudes (U/mes) | Duración Cada Solicitud (ms) | Memoria Asignada (GB) | Almacenamiento Efímero Asignado (MB) |
| ------------ | ------------------------------- | ---------------------------- | --------------------- | ------------------------------------ |
| x86          | 1000                            | 100                          | 6                     | 512                                  |

## ¿De dónde han "salido" los anteriores datos?

#### Cantidad de solicitudes

Se ha hecho una aproximación al alza calculando las solicitudes que podría tener una empresa de ese estilo y además sin saber datos genéricos de dicha empresa.

---

#### Duración de cada solicitud

En este caso, no se dispone del código para poder realizar algunas estimaciones, no obstante, se ha investigado y existen diferentes **librerías** las cuales puedes utilizarlas en **Python** y ejecutarlo junto a tu código. Éste ejecutará una serie de líneas que darán lugar al tiempo que tu código tarda en ejecutarse.

---

#### Memoria Asignada

En AWS tenemos la opción de asignarle hasta un máximo de _10GB_, no obstante, nuevamente, hemos calculado al alza para no tener problemas con el rendimiento.

---

#### Almacenamiento Efímero

Debido a que no utilizaremos demasiadas aplicaciones y no queremos que incremente el costo, hemos sido bastante conservados indicando **512 MB**.

---

![AWS Lambda Configuration Image - SNS](/images/snsconfig.png)

1. Solicitudes --> Cantidad de solicitudes que se recibirán.

2. Notificaciones HTTP/HTTPS --> Hay que tener en cuenta la notificación para HTTP y la de EMAIL.

3. Notificaciones por EMAIL o EMAIL-JSON --> Notificación a EMAIL y a la propia empresa.

4. Notificaciones de SQS --> Notificación de entrada y salida, se multiplica al igual que en los anteriores apartados x2 las solicitudes esperadas.

5. Amazon Web Services Lambda --> Solicitudes x2

6. Amazon Kinesis Data Firehose --> Solicitudes x2
