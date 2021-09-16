# Maquinas virtuales con GCP
## Virtual Private Cloud
Es una forma de establecer conectividad entre los recursos que tengamos en la nube.

Ambiente de red virtual, aislado y privado que se basa en el concepto de red definida por software.

Existe una red global privada (tiene alcance global). Es decir nos permite conectar todos nuestros recursos a la VPC sin importar la región en que estén.

### Subredes
Las VPC se forman de subredes. Una VPC debe tener al menos una subred.

Las subredes tienen alcance regional. Es decir, podemos conectar recursos que están en diferentes zonas de una región usando la subred.

Las subredes tienen asociados rangos de IPs, se usan para asignar IPs privadas a los recursos que están asociados a la subred.

### Tipos de VPC
* Default: Crea una subred en todas las regiones de GCP, crea algunos Firewalls
* Auto Mode: Similar a la anterior pero es expandible a /16.
* Custom Mode: No crea las subredes por defecto, se tiene control total de las IPs. Expandible a cualquier tamaño RFC 1918
