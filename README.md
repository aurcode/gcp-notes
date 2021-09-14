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
