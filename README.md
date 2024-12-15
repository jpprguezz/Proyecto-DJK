# Proyecto-DJK

Proyecto de DJK hecho por Moises, Carlos y José Manuel

---

# Selección de Modelo de servicio adecuado

![Image of cloud with service model examples](/images/mainimage.jpeg)

### Problema elegido para el proyecto

Problema C: Una cadena de restaurantes necesita implementar una funcionalidad que permita enviar notificaciones automáticas a los clientes cuando su pedido está listo. El sistema debe ser escalable, de bajo coste, y ejecutarse únicamente cuando se realicen pedidos.

### ¿Qué es un Modelo de Servicio?

Es la forma en que una organización ofrece y gestiona sus servicios a los clientes (SaaS, PaaS, IaaS, FaaS, entre otros)

## Selección: FaaS (Function as a Service)

### ¿De qué se trata FaaS?

Tipo de computación en la nube sin preocuparse por la gestión de servidores. Es ideal para aplicaciones ligeras. Este tipo de tecnología funciona de la siguiente manera: nosotros al contrastar el servicio, damos nuestra confianza a la empresa de computación, la cual nos proporciona sistemas remotos potentes y totalmente capaces de poder realizar las tareas que necesitamos

### ¿Por qué es el modelo ideal para este problema?

- Coste optimizado: Pago por ejecución, sin costos asociados a la propia infraestructura o tiempo de inactividad. Al usar equipos proporcionados por la empresa con la que estamos trabajando, evitamos el tener que adquirir de forma física estos equípos. A su vez, eliminamos la necesidad de ocupar espacio con los mismos.

- Escalabilidad: Responde automáticamente al volumen que queramos adquirir, pudiendo mejorar siempre que se necesite dichos equipos, con el fin de mejorar la producción de la empresa.

- Fácil implementación: Desarrollo rápido, gracias a que la empresa de FaaS con la que trabajamos, la cual se encarga de toda la instalación en los dispositivos de nuestra empresa.

- Flexibilidad: Compatible con diversas herramientas, entre ellos muchos de los más famosos lenguajes de programación, tales como: Python, JavaScript, Java o Go. 

- Simplicidad administrativa: Administrada por el proveedor el cual implementa todas las configuraciones necesarias para que podamos usar de forma remota todos los servicios necesarios.

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

| Plataforma            | Escalabilidad   | Costes                     | Dificultad a la hora de ser implementada                      | URL                                                  |
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

3. Integración con el ecosistema AWS (el cuál es el propio conjunto de servicios, herramientas y recursos que son proporcionados por amazon para trabajar con su sistema en la nube)

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

1. Latencia de arranque _en frio_. La latencia en frío es el lapso de espera que hay cuando una función es activada después de haber estado inactiva durante un tiempo.

2. Límites de tiempo y recursos

3. Dependencia de la infraestructura de Google

---
## Azure Functions

### Características
1. Diseña aplicaciones sin servidor en el lenguaje que prefieras mientras te centras en la lógica de negocios.

2. Logra un escalado de un gran rendimiento.

3. Flexibilidad y simplicidad, gracias a que Azure se encarga de ejecutar el código solo cuando sea necesario, escalarlo automáticamente, y liberar recursos en caso de que no se esten usando

## Ventajas

1. Podemos codificar todo el código que necesitemos para el problema / acción que se quiere ejecutar sin preocuparnos de la aplicación o la infraestructura para ejecutarlo.

2. Hace que el desarrollo sea más productivo.

3. Cambio en el modelo de pago frente a los WebJobs. Azure Function dispone de dos modelos de pago y, además, se puede incluir en un modelo de pago ya existente como un App Service. También se puede pagar solo por el tiempo que este en ejecución esa función.

## Desventajas

1. Los costos asociados con el uso de Azure son variables y dependen de los tipos de productos necesarios para el equipo de desarrollo de la empresa. 

2. Azure difiere de los servidores locales y requiere experiencia para garantizar un funcionamiento eficiente de todas las partes móviles. Incluso un error simple cometido por el administrador de TI puede generar problemas significativas.


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


---

## Conclusiones

En base al modelo adoptado, la investigación de las plataformas, los factores evaluados y el análisis económico, se concluye lo siguiente:

#### **Adecuación del Modelo de Servicio FaaS**
El modelo **FaaS** se ajusta perfectamente a los requisitos del problema debido a:

- **Coste optimizado**: Pago únicamente por uso y ejecución de funciones.
- **Escalabilidad automática**: La capacidad de escalar de manera dinámica según el volumen de trabajo asegura que las necesidades de procesamiento puedan ser cubiertas sin intervención manual.
- **Flexibilidad**: Compatible con diversos lenguajes y herramientas, lo que facilita la implementación de soluciones a medida.
- **Simplicidad administrativa**: El proveedor administra la infraestructura, permitiendo a los desarrolladores centrarse exclusivamente en la lógica del negocio.

#### **Soluciones Contrastadas**
De las plataformas seleccionadas, las tres cumplen con los principios del modelo FaaS, pero destacan en diferentes aspectos:

1. **AWS Lambda**:
   - Excelente para aplicaciones que requieren integración profunda con el ecosistema AWS.
   - Es ideal para equipos con experiencia en la plataforma.
   - El costo es competitivo, y ofrece herramientas avanzadas de monitoreo y configuración.

2. **Google Cloud Functions**:
   - Beneficia a las empresas que ya utilizan herramientas de Google.
   - Su integración nativa con el ecosistema de Google facilita el desarrollo de soluciones escalables.

3. **Azure Functions**:
   - Excelente opción para empresas que ya tienen experiencia o infraestructuras basadas en Microsoft.
   - Ofrece una flexibilidad significativa en modelos de pago y escalabilidad avanzada.

#### **Comparativa de Plataformas**
La elección de la plataforma dependerá de los siguientes factores:

| **Plataforma**         | **Casos ideales**                                                                                   |
|-------------------------|---------------------------------------------------------------------------------------------------|
| **AWS Lambda**          | Soluciones complejas y de alta integración con el ecosistema AWS.                                 |
| **Google Cloud Functions** | Aplicaciones ligeras, rápidas de implementar y con dependencia de servicios de Google Cloud.       |
| **Azure Functions**     | Proyectos empresariales con dependencias en herramientas y servicios de Microsoft Azure.          |

---

### **Recomendación Final**

La plataforma seleccionada debe alinearse con las necesidades técnicas y operativas del proyecto. Si el entorno actual está basado en Microsoft, **Azure Functions** ofrece una integración nativa que maximiza el valor del ecosistema Azure. Sin embargo, si ya se utilizan servicios de Google o AWS, estas plataformas podrían ser más convenientes. En cualquier caso, el modelo FaaS satisface los requisitos del problema por su flexibilidad, eficiencia económica y simplicidad administrativa.
