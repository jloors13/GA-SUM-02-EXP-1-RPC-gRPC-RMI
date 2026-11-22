# Glosario técnico: RPC, gRPC y RMI

**Actividad:** GA-SUM-02 / EXP-1  
**Asignatura:** Aplicaciones Distribuidas  
**Integrante:** LOOR SUAREZ JORDAN JOSUE

## 1. Conceptos principales

| Concepto | ¿Qué significa? |
|---|---|
| RPC (Remote Procedure Call) | Es una forma de ejecutar un procedimiento que se encuentra en otro equipo mediante una solicitud por la red. |
| gRPC | Es una tecnología que permite que diferentes aplicaciones se comuniquen mediante llamadas remotas. Utiliza HTTP/2 y, de forma predeterminada, Protocol Buffers. |
| RMI (Remote Method Invocation) | Es una tecnología de Java que permite llamar métodos de objetos que se encuentran en otra máquina virtual Java. |
| Cliente | Es el programa que realiza una petición para utilizar un servicio. |
| Servidor | Es el programa que recibe la petición, realiza el trabajo solicitado y devuelve una respuesta. |
| Stub | Es un representante local del servicio remoto que facilita la comunicación entre el cliente y el servidor. |
| Serialización | Es el proceso de convertir información en un formato que pueda enviarse por la red. |
| Deserialización | Es recuperar la información a partir de los datos que fueron enviados. |
| Protocolo | Son las reglas que deben seguir los equipos o programas para poder comunicarse. |
| Middleware | Es un software que facilita la comunicación entre diferentes aplicaciones o componentes de un sistema distribuido. |

## 2. Diferencias entre RPC, gRPC y RMI

Las tres alternativas permiten realizar operaciones entre programas que se ejecutan en diferentes procesos o equipos, pero tienen características distintas.

- **RPC:** es el mecanismo que permite solicitar la ejecución de un procedimiento en otro equipo. No depende de una tecnología específica.
- **gRPC:** es una tecnología basada en RPC que utiliza HTTP/2 y Protocol Buffers de forma predeterminada. Permite comunicar aplicaciones desarrolladas en diferentes lenguajes.
- **RMI:** es una tecnología de Java que permite invocar métodos de objetos ubicados en otra máquina virtual Java.

La diferencia principal está en la forma en que se implementa la comunicación. gRPC utiliza contratos de servicios y mensajes, mientras que RMI trabaja con interfaces y objetos remotos (gRPC Authors, s. f.; Oracle, 2026).

## 3. Funcionamiento de una llamada RPC

Una llamada RPC permite que un programa solicite la ejecución de un procedimiento que se encuentra en otro equipo. Aunque para el programador puede parecer una llamada normal, los datos deben enviarse a través de la red.

El proceso funciona de la siguiente manera:

1. El cliente solicita la ejecución de un procedimiento remoto.
2. El stub del cliente prepara los datos de la solicitud.
3. La petición se envía al servidor mediante la red.
4. El servidor recibe los datos y ejecuta el procedimiento solicitado.
5. El servidor prepara el resultado y lo envía al cliente.
6. El cliente recibe la respuesta y continúa con la operación.

En una llamada síncrona, el cliente espera la respuesta antes de continuar con esa operación. En gRPC también existen llamadas asíncronas, que permiten realizar otras tareas mientras se procesa la solicitud (gRPC Authors, s. f.).

## 4. Protocol Buffers y HTTP/2 en gRPC

gRPC utiliza Protocol Buffers para definir y serializar los mensajes que intercambian los servicios. Estas definiciones se escriben en archivos `.proto` y permiten generar código para diferentes lenguajes de programación (Google, s. f.).

Por otro lado, HTTP/2 se encarga de transportar los mensajes. Permite mantener varios flujos de comunicación en una misma conexión mediante la multiplexación (Thomson y Benfield, 2022).

gRPC admite cuatro tipos de llamadas:

- **Unaria:** una solicitud y una respuesta.
- **Streaming del servidor:** una solicitud y varias respuestas.
- **Streaming del cliente:** varias solicitudes y una respuesta.
- **Streaming bidireccional:** varios mensajes en ambas direcciones (gRPC Authors, s. f.).

## 5. Funcionamiento de Java RMI

Java RMI permite que un programa invoque métodos de un objeto que se encuentra en otra máquina virtual Java.

Para establecer la comunicación:

1. El servidor crea e implementa un objeto remoto.
2. Registra el objeto en el RMI Registry mediante un nombre.
3. El cliente busca el objeto utilizando ese nombre.
4. El registro devuelve una referencia al objeto remoto, normalmente un stub, que permite al cliente invocar sus métodos.

Este mecanismo facilita la comunicación entre aplicaciones Java, aunque depende de la conexión de red y puede presentar errores durante las llamadas remotas (Oracle, 2026).

## 6. Comparación técnica

| Criterio | RPC | gRPC | Java RMI |
|---|---|---|---|
| Tipo | Mecanismo de comunicación | Framework de RPC | Tecnología de Java |
| Lenguajes | Depende de la implementación | Multilenguaje | Java |
| Transporte | Depende de la implementación | HTTP/2 | Protocolo RMI |
| Datos | Depende de la implementación | Protocol Buffers por defecto | Objetos Java serializados |
| Comunicación | Depende de la implementación | Unaria y streaming | Métodos remotos |

La elección depende de las necesidades del sistema. gRPC resulta útil cuando se necesita comunicar aplicaciones desarrolladas en diferentes lenguajes, mientras que RMI puede utilizarse cuando los componentes trabajan en Java.

## 7. Referencias

- gRPC Authors. (s. f.). *Core concepts, architecture and lifecycle*. gRPC Documentation. https://grpc.io/docs/what-is-grpc/core-concepts/

- Google. (s. f.). *Protocol Buffers Overview*. https://protobuf.dev/overview/

- Thomson, M., & Benfield, C. (2022). *HTTP/2 (RFC 9113)*. Internet Engineering Task Force. https://www.rfc-editor.org/rfc/rfc9113

- Oracle. (2026). *Java Remote Method Invocation Specification*. https://docs.oracle.com/en/java/javase/26/docs/specs/rmi/index.html