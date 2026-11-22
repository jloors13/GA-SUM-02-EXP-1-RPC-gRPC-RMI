# Preguntas probables — Luis Quintero

**¿Netflix es AP o CP?** No se puede asignar una sola etiqueta a toda Netflix. En EVCache, para datos no críticos y replicación entre regiones, se tolera inconsistencia temporal para no interrumpir las operaciones locales; por eso se describe como una aproximación AP en ese caso.

**¿Qué significa EL en tu comparación PACELC?** En condiciones normales, EVCache prioriza lecturas locales rápidas mientras replica de forma asíncrona. La elección favorece latencia sobre consistencia global inmediata; no implica que todos los servicios de Netflix funcionen así.

**¿gRPC garantiza consistencia de datos?** No. gRPC organiza llamadas remotas entre servicios; la consistencia depende de cómo el sistema almacena, replica y confirma los datos.

**¿Google/YouTube usa gRPC en la arquitectura que comparas?** La publicación sobre aceleradores VCU no identifica el protocolo RPC concreto. No se puede atribuirle gRPC basándose en ese artículo.

**¿Qué significa el resultado de 20 a 33 veces?** Es una mejora de eficiencia reportada por Google respecto de una plataforma de transcodificación previa, no una comparación directa de rendimiento entre Netflix y YouTube.

**¿Dónde encaja Java RMI?** Es otra manera de invocar operaciones remotas, especialmente asociada a aplicaciones Java; no está demostrado por las fuentes citadas que Netflix o YouTube lo utilicen en estos casos.

**Fuentes:** Netflix Technology Blog (EVCache y Netflix Media Database) y Ranganathan et al., ASPLOS 2021, DOI: 10.1145/3445814.3446723.
