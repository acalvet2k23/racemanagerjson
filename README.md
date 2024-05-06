# racemanagerjson
## Json doc

Dentro de ```json_doc``` podemos ver las llamadas que hay disponibles.

### getCurses
 * request
Pide todas las cursas que hayan, ordenadas por fecha. Acepta el parámetro opcional ```cursaId``` para recibir solo la información de una cursa.

 * response
Devuelve un array de cursas con todos sus datos, incluido _esport_ y _estat_ con sus respectivos *id* y *nom*
También devuelve un objeto llamado *response* con código de error y descripción del error

### inscriure
 * request
Envía todos los datos de un participante y el id de una cursa, para registrarlo

 * response
Devuelve un objeto llamado *response* con código de error y descripción del error

### participantCheckpoint
 * request
Envía los id del beacon y del checkpoint, además de un timestamp.

 * response
Devuelve un objeto llamado *response* con código de error y descripción del error