# CRUD-serverless
## Diagrama del proyecto
![Diagrama](src/ddb-crud.png)
## Componentes del diagrama:
 -Api Gateway, Lambda y DynamoDB
## Implentación
## Primer paso
 - Crea una tabla en DynamoBD
 - Pon un nombre a la tabla
 - Para la partición de la tabla ingrese id
 - Cree la tabla
## Segundo paso
 - Cree la función Lambda
 - Nombre la función
 - Seleccione crear nuevo rol a partir de las plantillas de politicas de AWS
 - Nombre el nuevo rol 
 - Para Plantillas de políticas , elija "Simple microservice permissions". Esta política otorga permiso a la función Lambda para interactuar con DynamoDB.
 - Cree la función 
 - Abra el index.mjs, copie y pegue todo el contenido del index.js del repostirio al index.mjs (Asegure de cambiar el nombre de la tabla de DynamoDB por la cual nombro)
## Tercer paso
 - Cree una API HTTP
 - Nombre a su API
 - Cree la AIP
## Cuarto paso
 - Crea las rutas de la API
 - Seleccione su API
 - Seleccione routes y crear
 - Debera crear 4 rutas: GET /items, GET /items/{id}, DELETE /items/{id} y PUT /items
## Quinto paso
 - Selecciona tu API
 - Selecciona Manage integrations y seleciona create
 - Para el tipo de integración selecione Lambda function
 - Nombra la función de integración
 - Crealo
## Sexto paso
 - Selecciona tu API
 - Selecciona Integrations y luego routes
 - Seleccione una integración existente, la que nombro en el quinto paso
 - Seleccione Attach integration
 - Repita los pasos con las rutas 4 rutas creada del API
## TEST
 - Pruebe su API
 - Seleccione tu API
 - Copie la URL que sale en invoke URL para realizar sus peticiones
 - Ejemplos de para la probar (No olvide cambiar la ruta por la de su API)
 - Crear o Actualizar
 - curl -X "PUT" -H "Content-Type: application/json" -d "{\"id\": \"123\", \"price\": 12345, \"name\": \"myitem\"}" https://abcdef123.execute-api.us-west-2.amazonaws.com/items
 - Obtener datos de un elemento por su ID
 - curl https://abcdef123.execute-api.us-west-2.amazonaws.com/items/123
 - Eliminar un elemento
 - curl -X "DELETE" https://abcdef123.execute-api.us-west-2.amazonaws.com/items/123
 - Listar todos los elementos
 - curl https://abcdef123.execute-api.us-west-2.amazonaws.com/items


