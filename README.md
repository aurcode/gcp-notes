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
* `-c` es la clase
* `-l` es el tipo de locación que deseamos
* `--pap` especifica el acceso público
* `-b` es activar el acceso uniforme
Avanzado:
* `--retention` es el periodo de retención del recurso.


## Google Cloud Bigtable

Cloud Bigtable es el servicio de base de datos de Big Data NoSQL de Google, completamente administrado a escala de patabytes para casos de uso en los que el acceso de datos aleatorios de baja latencia, la escalabilidad y la confiabilidad son fundamentales

### Características

* Alto procesamiento
* Procesamiento de baja latencia
* Cantidades muy grandes de datos
* Cambios de tamaño sin tiempo de inactividad
* Replicación flexible y automatizada
* Google Search, Maps y otros productos de Google

¿Cómo interactuamos con Cloud Big Table?

Api de aplicación: Podemos leer y escribir datos atraves de una capa de servicio llamada rede Hbase, que es un gestor de codigo abierto que nos ayuda exponer el point que nos proveen estas operaciones de escribir leer actualizar y borrar y esto se usa normalmente para enviar datos a las aplicaciones o paneles de control
Streaming / Transmisión: Datflow Streaming, Saprk Streaming y Apache Storm
Batch Processing / Procesamiento por lotes: Los datos se pueden leer y escribir en Big Table en forma de batch (cantidades grandes) esto se puede hacer a través de hadoop, Datflow, Apache Spark.

### Google Cloud Bigtable en acción
En esta clase creamos una instancia de Bigtable con el nombre `quick-start-instance`, id `quick-start-instance` y cluster id `quickstart-instance-c1`. El tipo de disco fue SSD con un solo nodo. Finalmente la región fue `us-east1` y la zona `us-east1-c`.

Desde la CLI podemos crear nuestra instancia ocupando la herramienta `cbt`, la el comando para crear la instancia de esta clase quedaría así:

* `cbt createinstance quick-start-instance "quick-start-instance" quickstart-instance-c1 us-east1-c 1 SSD`
* `quick-start-instance` es el id
* `"quick-start-instance"` es el nombre
* `quickstart-instance-c1` es el id del cluster
* `us-east1-c` es la región
* `1` es el numero de nodos
* `SSD` es el tipo de disco

## Cloud SQL
Este es el servicio administrado de Bases de Datos Relacionales. Puede ser MySQL, PosgreSQL y SLQ Server.

En caso de necesitar mayor rendimiento se puede escalar de forma vertical (un máquina más potente).
Si se requiere más disponibilidad se puede optar por una arquitectura en dos zonas.

### Características claves
Totalmente administrada
Una solución integrada: Se puede acceder a ellas desde cualquier lado.
Confiable: ES fácil configurar las replicas, copias de seguridad y activar el proceso de Failover (reemplazar una instancia cuando esta falla).
Migraciones sencillas a CloudSQL: Database Migration Service ayuda a migrar las DB on premise a la Nube facilmente.
En este tipo de Bases de datos realizamos transacciones y deben cumplir los principios ACID.

* Atomicity: Asegura que todas las operaciones que una transaccion se realicen, y en caso contrario que sea posible regresar al estado anterior (rollback).
* Consistency: Asegura que todas las transacciones se realicen con exito, los datos deben tener sentido.
* Isolation: Dicta que las operaciones sean aisladas y transparentes, es decir, multiples operaciones ocurren de forma independiente y sin afectarse.
* Durabilty: Nos asegura que el resultado de una operación permanezca incluso cuando hubo un error.


## Firestore

BigTable es una Base de Datos NoSQL de tipo Llave-Valor (key-value), mientras que Cloud Firestore es una Base de Datos NoSQL de documentos

**Documento **= Conjunto de datos asociados a un mismo concepto
Ejemplo: Producto, Nota, Jugador.

Colección: Conjunto de documentos.
Cloud Firestore:

- Serverless
- Tiempo Real
- Soporte Offline

### Características:

- Escalable
- Confiable
- Flexible
- Disponible
- Transaccional

Algunos casos de uso pueden ser:

- Gestión de perfiles de usuario
- Inventarios en tiempo real
- Cambios de estados
- Sincronización de datos

### Firestore en acción
En esta clase creamos una instancia de Firestore en Native Mode, ubicada en us-east4.

Ocupando el siguiente comando podemos crear una base de datos Google Cloud Firestore Native:

gcloud firestore databases create --region=us-east4	
