# endpoint SPARQL

Es un endpoint de SPARQL con un RDF (ttl) que puedes montar siguiendo las instrucciones a continuacion

## Empecemos.

### Prerequisitos.

Que necesitas para que funcione el endpoint:

```
Docker
```

### Como iniciamos 

a continuacion veremos el paso a paso para correr correctamente el contenedor


```
docker run -p 3030:3030 -e ADMIN_PASSWORD=pw123 stain/jena-fuseki
```

ten en cuenta la contraseña pw123 y el usuario por defecto admin.

El apache jena fuseki estara corriendo en el puerto 3030 y podremos acceder mediante el explorador por http://localhost:3030/



Para finalizar debemos crear una nueva base de datos y aqui agregar el archivo *.ttl, en nuestro caso es el archivo "oficial.ttl" el que contiene al rededor de 2000 articulos organizados de acuerdo a su ontologia.

* [Video_Guia](https://drive.google.com/file/d/1_PiqGZM3J25BJ3_3eJ8h1c-WaIY_3RI0/view?usp=sharing) - Como correr entorno SPARQL

## Prueba la siguiente consulta

Antes de realizar una consulta debes ingresar los prefijos que posiblemente vas a utilizar

```
prefix bb: <http://www.snik.eu/ontology/bb/>
prefix rdf:   <http://www.w3.org/1999/02/22-rdf-syntax-ns#> 
prefix xsd:   <http://www.w3.org/2001/XMLSchema#> 
prefix fo:    <http://www.w3.org/1999/XSL/Format#> 
prefix rdfs:  <http://www.w3.org/2000/01/rdf-schema#> 
prefix dc:    <http://purl.org/dc/elements/1.1/> 
prefix bbr: <http://purl.org/dc/terms/> 
```
Consulta los articulos que fueron creados en el año 2018
```
SELECT (COUNT(*)AS ?totalarticles)
WHERE
{
    ?class dc:created 2018 .
}
```
Solicita un conteo de todos los autores

```
SELECT (COUNT(*)AS ?totalauthors)
WHERE
{
    ?class dc:creator .
}
```


