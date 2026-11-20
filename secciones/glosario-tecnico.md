# Glosario técnico: RPC, gRPC y RMI

**Actividad:** GA-SUM-02 / EXP-1  
**Asignatura:** Aplicaciones Distribuidas  
**Integrante:** LOOR SUAREZ JORDAN JOSUE

## 1. Conceptos principales

| Concepto | ¿Qué significa? |
|---|---|
| RPC (Remote Procedure Call) | Es una forma de ejecutar una función que se encuentra en otro equipo, sin tener que escribir directamente todo el proceso de comunicación. |
| gRPC | Es una tecnología que permite que diferentes aplicaciones se comuniquen mediante llamadas remotas. Utiliza HTTP/2 y Protocol Buffers para intercambiar información. |
| RMI (Remote Method Invocation) | Es una tecnología de Java que permite llamar métodos de objetos que se encuentran en otra computadora. |
| Cliente | Es el programa que realiza una petición para utilizar un servicio. |
| Servidor | Es el programa que recibe la petición, realiza el trabajo solicitado y devuelve una respuesta. |
| Stub | Es un representante local del servicio remoto. Se encarga de facilitar la comunicación entre el cliente y el servidor. |
| Serialización | Es el proceso de convertir información u objetos en un formato que se pueda enviar por la red. |
| Deserialización | Es recuperar la información original a partir de los datos que fueron enviados. |
| Protocolo | Son las reglas que deben seguir los equipos o programas para poder comunicarse. |
| Middleware | Es un software que facilita la comunicación entre diferentes aplicaciones o componentes de un sistema distribuido. |

## 2. Diferencias entre RPC, gRPC y RMI

Aunque las tres alternativas permiten realizar operaciones entre procesos, no funcionan exactamente de la misma manera.

- **RPC:** es el mecanismo general que permite solicitar la ejecución de procedimientos en otro equipo.
- **gRPC:** utiliza ese mecanismo y ofrece herramientas para definir servicios y transmitir información entre aplicaciones.
- **RMI:** permite realizar llamadas a métodos de objetos remotos, pero está orientado principalmente a aplicaciones desarrolladas en Java.

## 3. Temas que falta investigar

- Cómo se realiza una llamada RPC desde que el cliente envía la petición hasta que recibe la respuesta.
- Para qué sirven Protocol Buffers en gRPC.
- Qué ventajas ofrece HTTP/2 en la comunicación.
- Cómo funciona el registro de objetos remotos en Java RMI.
- Qué diferencias existen en rendimiento, compatibilidad y facilidad de implementación.

## 4. Referencias

Las fuentes utilizadas para completar este glosario se incorporarán después de consultar la documentación oficial y los artículos académicos correspondientes.
