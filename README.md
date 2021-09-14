# gcp-notes

## gsutil Bucket
Se sugiere ponerle al Bucket que este asociado con el proyecto, para que sea fácil de ubicar. El nombre del Bucket debe ser único.

Crear un Bucket (make Bucket)

`gsutil mb gs://mi-proyecto-bucket-01`

Ver mis Buckets

`gsutil ls`

Ver los objetos en un Bucket

`gsutil ls gs://mi-proyecto-bucket-01`

Copiar objetos a un Bucket

`gsutil cp ./archivo.txt gs://mi-proyecto-bucket-01`

Copiar objetos de un Bucket a otro lado

`gsutil cp gs://mi-proyecto-bucket-01/archivo.txt .`

Activar el versionamiento en los objetos de un Bucket

`gsutil versioning set on gs://mi-proyecto-bucket-01`

Desactivar el versionamiento en los objetos de un Bucket

`gsutil versioning set off gs://mi-proyecto-bucket-01`


En esta clase creamos un Bucket Standar Multi-region en US. Se previo el acceso al público y se eligió el acceso uniforme. Finalmente seleccionamos una retención de 10 años. Esto en gsutil se vería así:

`gsutil mb -c standard -l us --pap enforced -b on --retention 10y gs://gemb-platzi-storage-bucket-01`
Donde:
`-c` es la clase
`-l` es el tipo de locación que deseamos
`--pap` especifica el acceso público
`-b` es activar el acceso uniforme
Avanzado:
`--retention` es el periodo de retención del recurso.


## Google Cloud Bigtable

Cloud Bigtable es el servicio de base de datos de Big Data NoSQL de Google, completamente administrado a escala de patabytes para casos de uso en los que el acceso de datos aleatorios de baja latencia, la escalabilidad y la confiabilidad son fundamentales

### Características

Alto procesamiento
Procesamiento de baja latencia
Cantidades muy grandes de datos
Cambios de tamaño sin tiempo de inactividad
Replicación flexible y automatizada
Google Search, Maps y otros productos de Google
¿Cómo interactuamos con Cloud Big Table?

Api de aplicación: Podemos leer y escribir datos atraves de una capa de servicio llamada rede Hbase, que es un gestor de codigo abierto que nos ayuda exponer el point que nos proveen estas operaciones de escribir leer actualizar y borrar y esto se usa normalmente para enviar datos a las aplicaciones o paneles de control
Streaming / Transmisión: Datflow Streaming, Saprk Streaming y Apache Storm
Batch Processing / Procesamiento por lotes: Los datos se pueden leer y escribir en Big Table en forma de batch (cantidades grandes) esto se puede hacer a través de hadoop, Datflow, Apache Spark.
