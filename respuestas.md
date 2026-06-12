Preguntas a responder
1. ¿Por qué necesitamos Loki además de Prometheus si ya tenemos /metrics?
Porque Prometheus solo guarda métricas, no logs.
Los logs (Loki) me ayudan a ver el detalle de lo que pasó dentro de la app (errores, stack traces, eventos).
Las métricas me dicen qué está pasando, pero los logs me dicen por qué pasó.

2. ¿Qué ventaja aporta que las fuentes de datos de Grafana estén aprovisionadas como código y no creadas a mano?
Porque es más ordenado y reproducible.
Puedo versionarlo en Git, automatizarlo y evitar errores manuales.
Además, si despliego en otro entorno, se configura igual sin hacerlo a mano.

3. El panel "CPU contenedor" y el panel "CPU host" pueden mostrar valores muy distintos. ¿Por qué? ¿Cuál usarías para alertar sobre una aplicación concreta?
Son distintos porque el CPU host muestra todo el uso del servidor completo, mientras que el CPU contenedor solo muestra lo que consume ese contenedor.
Para alertar sobre una aplicación concreta usaría el CPU del contenedor, porque es el que realmente refleja su consumo.

4. ¿Qué diferencia hay entre el evaluation interval y el pending period de una alarma?
Evaluation interval: cada cuánto tiempo se revisa la métrica.
Pending period: cuánto tiempo debe mantenerse la condición antes de activar la alerta.
En simple: uno controla cuándo se revisa, el otro cuánto tiempo debe durar el problema antes de alertar.
