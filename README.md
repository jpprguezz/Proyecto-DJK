# Proyecto-DJK

Proyecto de DJK hecho por Moises, Carlos y José Manuel

# Selección de Modelo de servicio adecuado

## Selección: FaaS (Function as a Service)

### ¿De qué se trata?

Tipo de computación en al nube sin preocuparse por la gestión de servidores. Es ideal para aplicaciones ligeras

### ¿Por qué es el modelo ideal para este problema?

- Coste optimizado: Pago por ejecución, sin costos asociados a la propia infraestructura o tiempo de inactividad.

- Escalabilidad: Responde automáticamente al volumen que queramos adquirir.

- Fácil implementación: Desarrollo rápido.

- Flexibilidad: Compatible con diversas herramientas.

- Simplicidad administrativa: Administrada por el proveedor.

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

| Platform             | Scalability | Costs                  | Implementation Difficulty                      | URL                                                  |
| -------------------- | ----------- | ---------------------- | ---------------------------------------------- | ---------------------------------------------------- |
| **AWS Lambda**       | Excelente   | Baja (Gratis hasta 1M) | Alta, pero requiere experiencia con AWS        | https://aws.amazon.com/es/lambda/                    |
| **Google Functions** | Excelente   | Bajo (Gratis hasta 1M) | Muy alta                                       | https://cloud.google.com/functions                   |
| **Azure Functions**  | Excelente   | Bajo (Gratis hasta 1M) | Alta, especialmente para usuarios de Microsoft | https://azure.microsoft.com/es-es/products/functions |

## AWS Lambda

#### Características

- Compatible con diferentes leguanjes de programación (Node.js, Python, Go, Java, entre otros)

- Tiempo muy bajo de ejecución máxima de 15 minutos (Si la tarea a ejecutar tarda más de 15 minutos, nuestra plataforma detendrá idependientemente de si ha terminado o no)

##### Ventajas

1. Escalabilidad automática

2. Pago por uso

3. Integración con el ecosistema AWS

#### Desventajas

1. Tiempo de ejecución limitado

2. Latencia

3. Dependencia del ecosistema AWS
