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

## Prueba la siguiente consulta

Solicita un conteo de los articulos creados en el 2018

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


### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

### And coding style tests

Explain what these tests test and why

```
Give an example
```

## Deployment

Add additional notes about how to deploy this on a live system

## Built With

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Authors

* **Billie Thompson** - *Initial work* - [PurpleBooth](https://github.com/PurpleBooth)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone whose code was used
* Inspiration
* etc
