API - Base de Datos

Rutas disponibles: 

http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/guests
Rutas de la API para Huéspedes
La API de huéspedes permite gestionar la información de los huéspedes mediante diversas rutas. A continuación, se describen las rutas disponibles, sus métodos HTTP y cómo utilizarlas.

1. Obtener todos los huéspedes
Ruta: GET http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/guests
Descripción: Recupera una lista de todos los huéspedes registrados en la base de datos.
Respuesta:
Código 200: Devuelve un array con los objetos de los huéspedes.
Código 500: Error en la recuperación de datos.
2. Obtener un huésped específico
Ruta: GET http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/guests/:id
Descripción: Recupera la información de un huésped específico mediante su ID.
Parámetros:
id: ID del huésped a recuperar.
Respuesta:
Código 200: Devuelve el objeto del huésped.
Código 404: Si no se encuentra el huésped.
3. Crear un nuevo huésped
Ruta: POST http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/guests
Descripción: Crea un nuevo registro de huésped en la base de datos.
Cuerpo de la solicitud:
json
Copiar código
{
  "firstName": "Nombre",
  "lastName": "Apellido",
  "email": "correo@example.com",	
  "phone": "123456789",
  "nationality": "Nacionalidad",
  "documentType": "PASSPORT",
  "documentNumber": "Número de documento",
  "address": {
    "street": "Calle",
    "city": "Ciudad",
    "state": "Estado",
    "country": "País",
    "postalCode": "Código postal"
  },
  "preferences": { "key": "valor" },
  "blacklisted": false,
  "blacklistReason": "Razón"
}
Respuesta:
Código 201: Devuelve el objeto del huésped creado.
Código 400: Si faltan datos requeridos (firstName, lastName, email).
4. Actualizar un huésped existente
Ruta: PUT http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/guests/:id
Descripción: Actualiza la información de un huésped existente mediante su ID.
Parámetros:
id: ID del huésped a actualizar.
Cuerpo de la solicitud:
Se pueden enviar los mismos campos que para crear un nuevo huésped, omitiendo aquellos que no se deseen actualizar.
Respuesta:
Código 200: Devuelve el objeto del huésped actualizado.
Código 404: Si no se encuentra el huésped.
5. Eliminar un huésped
Ruta: DELETE http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/guests/:id
Descripción: Elimina un registro de huésped específico de la base de datos.
Parámetros:
id: ID del huésped a eliminar.
Respuesta:
Código 204: El huésped se ha eliminado correctamente.
Código 404: Si no se encuentra el huésped.



http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/rooms
Rutas de la API para Habitaciones
La API de habitaciones permite gestionar la información de las habitaciones mediante diversas rutas. A continuación, se describen las rutas disponibles, sus métodos HTTP y cómo utilizarlas.

1. Obtener todas las habitaciones
Ruta: GET http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/rooms
Descripción: Recupera una lista de todas las habitaciones registradas en la base de datos.
Respuesta:
Código 200: Devuelve un array con los objetos de las habitaciones.
Código 500: Error en la recuperación de datos.

2. Obtener una habitación específica
Ruta: GET http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/rooms/:id
Descripción: Recupera la información de una habitación específica mediante su ID.
Parámetros:
id: ID de la habitación a recuperar.
Respuesta:
Código 200: Devuelve el objeto de la habitación.
Código 404: Si no se encuentra la habitación.

3. Crear una nueva habitación
Ruta: POST http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/rooms
Descripción: Crea un nuevo registro de habitación en la base de datos.
Cuerpo de la solicitud:
json
Copiar código
{
  "roomNumber": "101",
  "type": "SINGLE",
  "basePrice": 100,
  "capacity": 1,
  "amenities": ["Wi-Fi", "TV"],
  "status": "AVAILABLE",
  "description": "Habitación cómoda con vista al mar.",
  "images": ["url_imagen1", "url_imagen2"]
}
Respuesta:
Código 201: Devuelve el objeto de la habitación creada.
Código 400: Si faltan datos requeridos (roomNumber, type, basePrice, capacity).

4. Actualizar una habitación existente
Ruta: PUT http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/rooms/:id
Descripción: Actualiza la información de una habitación existente mediante su ID.
Parámetros:
id: ID de la habitación a actualizar.
Cuerpo de la solicitud:
Se pueden enviar los mismos campos que para crear una nueva habitación, omitiendo aquellos que no se deseen actualizar.
Respuesta:
Código 200: Devuelve el objeto de la habitación actualizada.
Código 404: Si no se encuentra la habitación.
5. Eliminar una habitación
Ruta: DELETE http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/rooms/:id
Descripción: Elimina un registro de habitación específico de la base de datos.
Parámetros:
id: ID de la habitación a eliminar.
Respuesta:
Código 204: La habitación se ha eliminado correctamente.
Código 404: Si no se encuentra la habitación.

http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/reservations
Rutas de la API para Reservas
La API de reservas permite gestionar la información de las reservas mediante diversas rutas. A continuación, se describen las rutas disponibles, sus métodos HTTP y cómo utilizarlas.

1. Obtener todas las reservas
Ruta: GET http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/reservations
Descripción: Recupera una lista de todas las reservas registradas en la base de datos, incluyendo información del huésped y la habitación.
Respuesta:
Código 200: Devuelve un array con los objetos de las reservas.
Código 500: Error en la recuperación de datos.
2. Obtener una reserva específica
Ruta: GET http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/reservations/:id
Descripción: Recupera la información de una reserva específica mediante su ID, incluyendo información del huésped y la habitación.
Parámetros:
id: ID de la reserva a recuperar.
Respuesta:
Código 200: Devuelve el objeto de la reserva.
Código 404: Si no se encuentra la reserva.
3. Crear una nueva reserva
Ruta: POST http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/reservations
Descripción: Crea un nuevo registro de reserva en la base de datos.
Cuerpo de la solicitud:
json
Copiar código
{
  "bookingReference": "REF12345",
  "guest": "ID_GUEST",
  "room": "ID_ROOM",
  "checkIn": "2024-10-01T14:00:00Z",
  "checkOut": "2024-10-05T12:00:00Z",
  "totalPrice": 500,
  "channel": "DIRECT",
  "channelReference": "CHANNEL_REF",
  "specialRequests": "Cama extra"
}
Respuesta:
Código 201: Devuelve el objeto de la reserva creada.
Código 400: Si faltan datos requeridos (bookingReference, guest, room, checkIn, checkOut, totalPrice, channel).
4. Actualizar una reserva existente
Ruta: PUT http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/reservations/:id
Descripción: Actualiza la información de una reserva existente mediante su ID.
Parámetros:
id: ID de la reserva a actualizar.
Cuerpo de la solicitud:
Se pueden enviar los mismos campos que para crear una nueva reserva, omitiendo aquellos que no se deseen actualizar.
Respuesta:
Código 200: Devuelve el objeto de la reserva actualizada.
Código 404: Si no se encuentra la reserva.
5. Eliminar una reserva
Ruta: DELETE http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/reservations/:id
Descripción: Elimina un registro de reserva específico de la base de datos.
Parámetros:
id: ID de la reserva a eliminar.
Respuesta:
Código 204: La reserva se ha eliminado correctamente.
Código 404: Si no se encuentra la reserva.


http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/rate-modifications
Rutas de la API para Modificaciones de Tarifa
La API de modificaciones de tarifa permite gestionar la información relacionada con cambios en las tarifas de las habitaciones. A continuación, se describen las rutas disponibles, sus métodos HTTP y cómo utilizarlas.

1. Obtener todas las modificaciones de tarifa
Ruta: GET http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/rate-modifications
Descripción: Recupera una lista de todas las modificaciones de tarifa registradas en la base de datos, incluyendo información de la habitación asociada.
Respuesta:
Código 200: Devuelve un array con los objetos de las modificaciones de tarifa.
Código 500: Error en la recuperación de datos.
2. Obtener una modificación de tarifa específica
Ruta: GET http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/rate-modifications/:id
Descripción: Recupera la información de una modificación de tarifa específica mediante su ID, incluyendo información de la habitación asociada.
Parámetros:
id: ID de la modificación de tarifa a recuperar.
Respuesta:
Código 200: Devuelve el objeto de la modificación de tarifa.
Código 404: Si no se encuentra la modificación de tarifa.
3. Crear una nueva modificación de tarifa
Ruta: POST http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/rate-modifications
Descripción: Crea un nuevo registro de modificación de tarifa en la base de datos.
Cuerpo de la solicitud:
json
Copiar código
{
  "room": "ID_ROOM",
  "startDate": "2024-10-01T00:00:00Z",
  "endDate": "2024-10-05T00:00:00Z",
  "modificationType": "PRICE_CHANGE",
  "value": 120,
  "reason": "Aumento de tarifas para temporada alta",
  "channel": "DIRECT"
}
Respuesta:
Código 201: Devuelve el objeto de la modificación de tarifa creada.
Código 400: Si faltan datos requeridos (room, startDate, endDate, modificationType, value, channel).
4. Actualizar una modificación de tarifa existente
Ruta: PUT http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/rate-modifications/:id
Descripción: Actualiza la información de una modificación de tarifa existente mediante su ID.
Parámetros:
id: ID de la modificación de tarifa a actualizar.
Cuerpo de la solicitud:
Se pueden enviar los mismos campos que para crear una nueva modificación de tarifa, omitiendo aquellos que no se deseen actualizar.
Respuesta:
Código 200: Devuelve el objeto de la modificación de tarifa actualizada.
Código 404: Si no se encuentra la modificación de tarifa.
5. Eliminar una modificación de tarifa
Ruta: DELETE http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/rate-modifications/:id
Descripción: Elimina un registro de modificación de tarifa específico de la base de datos.
Parámetros:
id: ID de la modificación de tarifa a eliminar.
Respuesta:
Código 204: La modificación de tarifa se ha eliminado correctamente.
Código 404: Si no se encuentra la modificación de tarifa.

http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/inventory

Rutas de la API para Inventario
La API de inventario permite gestionar la disponibilidad y precios de las habitaciones en diferentes fechas. A continuación se describen las rutas disponibles, sus métodos HTTP y cómo utilizarlas.

1. Obtener todos los registros de inventario
Ruta: GET http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/inventory
Descripción: Recupera una lista de todos los registros de inventario, incluyendo la información de las habitaciones asociadas.
Respuesta:
Código 200: Devuelve un array con los objetos de inventario.
Código 500: Error en la recuperación de datos.
2. Obtener un registro de inventario específico
Ruta: GET http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/inventory/:id
Descripción: Recupera la información de un registro de inventario específico mediante su ID, incluyendo la información de la habitación asociada.
Parámetros:
id: ID del registro de inventario a recuperar.
Respuesta:
Código 200: Devuelve el objeto de inventario.
Código 404: Si no se encuentra el registro de inventario.
3. Crear un nuevo registro de inventario
Ruta: POST http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/inventory
Descripción: Crea un nuevo registro de inventario en la base de datos.
Cuerpo de la solicitud:
json
Copiar código
{
  "room": "ID_ROOM",
  "date": "2024-10-01T00:00:00Z",
  "availableUnits": 5,
  "price": 150,
  "restrictions": {
    "minStay": 2,
    "maxStay": 5,
    "closedToArrival": false,
    "closedToDeparture": false
  },
  "channel": "DIRECT"
}
Respuesta:
Código 201: Devuelve el objeto de inventario creado.
Código 400: Si faltan datos requeridos (room, date, availableUnits, price).
4. Actualizar un registro de inventario existente
Ruta: PUT http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/inventory/:id
Descripción: Actualiza la información de un registro de inventario existente mediante su ID.
Parámetros:
id: ID del registro de inventario a actualizar.
Cuerpo de la solicitud:
Se pueden enviar los mismos campos que para crear un nuevo registro de inventario, omitiendo aquellos que no se deseen actualizar.
Respuesta:
Código 200: Devuelve el objeto de inventario actualizado.
Código 404: Si no se encuentra el registro de inventario.
5. Eliminar un registro de inventario
Ruta: DELETE http://chelenko-data.sa-east-1.elasticbeanstalk.com/api/inventory/:id
Descripción: Elimina un registro de inventario específico de la base de datos.
Parámetros:
id: ID del registro de inventario a eliminar.
Respuesta:
Código 204: El registro de inventario se ha eliminado correctamente.
Código 404: Si no se encuentra el registro de inventario.




