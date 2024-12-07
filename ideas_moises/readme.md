# En este documento se podrán visualizar diferentes ideas del componente del grupo: Moisés.

## Serán ideas a poner en común las cuales no están aún implementadas.

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

| Platform             | Scalability | Costs                  | Implementation Difficulty                      |
| -------------------- | ----------- | ---------------------- | ---------------------------------------------- |
| **AWS Lambda**       | Excelente   | Baja (Gratis hasta 1M) | Alta, pero requiere experiencia con AWS        |
| **Google Functions** | Excelente   | Bajo (Gratis hasta 1M) | Muy alta                                       |
| **Azure Functions**  | Excelente   | Bajo (Gratis hasta 1M) | Alta, especialmente para usuarios de Microsoft |
