# Api Consulta de Existencias 
Los cedis proporcionan una Api de tipo REST con el que por medio del envio de productos
se podran consultar las existencias de productos y precios de los que se hallan tratado
consultar en el momento.

# Credeciales necesarias
Para consumir la API es necesario contar con un usuario y contraseña unico que por medio
de este se identificara su ID de cliente  para poder proporcionarle su informacion propia


# Obtener credenciales
Comunicarse con su provedor  para que le sean proporcionadas las credenciales en caso de 
no tenerlas aun en debido caso que las credenciales propocionadas no funcionen o tengan 
algun problema de la misma manera compunicarse con su provedor para propocionar unas 
credenciales nuevas o ya sea tambien revisar las anteriores.

# URL:
http://url:9085/sexistencia

# Método:
Post

# HEADERS:
user:usuario
pass:contraseña

# Body(form_data)
* ### k_clave:
 Se tiene que mandar del 1 al 4 una clave ya se 1,2,3 o 4 para consultar los 4 paquetes de informacion que se estaran brindando

```
$response = $curl->get("cedistabasco.ddns.net:9085/sexistencia?{$params}", ['headers' => $headerdatosproducto]);

$params= ?k_clave=1;


$headerdatosproducto;

$headerdatosproducto= array(
            'Accept' => 'application/json',
            'user' =>'Usuario'
            'pass' =>'Contraseña');
//se recibe con
$response = collect(json_decode($response->getBody()))
```
Si la solicitud es correcta recibiremos la siguiente respuesta:
```

    "Items": [
        {
            "part_number": "0081249007",
            "brand": "TRACKONE",
            "price": "0",
            "stock": "0"
        },
```
Los valores son los siguientes
* ### Items:Ejemplo del Items siendo un Array conteniendo su informacion adentro de este mismo
### Donde aloja dos objetos que son el precio y la existencia y linea.

  * ### part_number:numero o clave del producto.
  * ### brand: Linea a la que pertenece.
  * ### price : Precio Calculado por cliente.
  * ### stock: Existencia de cada producto.

  De llegar a tener algun error el formato mandara un Objeto Vacio
  ```
  {}
  ```
# Usuario y Contraseña Desabilitado o error en ella 
En dado caso de tener un usuario o contraseña con problemas ibtendras el siguiente error
de esta forma podras comunicarte con tu provedor y intentaremos apoyarte con tu problema.
```
{
    "ok": "0",
    "err": "Unauthorized user or incorrect password."
}
```
  
