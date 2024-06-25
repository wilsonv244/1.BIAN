# API Payment Execution Service Fees - Documentación

## Descripción General
**Función:** Actualizar Estado registro Telefono OTP



| **API SPECIFICATION** |                                                                               |
|-----------------------|------------------------------------------------------------------------------ |
| **API Name**          | party-authentication-s                                                        |
| **Version**           | v1                                                                            |
| **Method**            | PATCH                                                                         |
| **Base Path**         | /party-authentication-s/v1                                                    |
| **Path**              | /authentication-devices/update                                                |
| **URI**               | PATCH /party-authentication-s/v1/authentication-devices/update                |


| **BACKEND SERVICE**|                                         |
|--------------------|-----------------------------------------|
| **Protocol**       | JSON                                    |
| **URL**            | http://url-backend.com/basepath/path    |
| **Description**    | Breve descripción del backend           |



| **BIAN DEFINITIONS**   |                                      |
|------------------------|--------------------------------------|
| **Business Area**      | Sales and Service                    |
| **Business Domain**    | Cross Channel                        |
| **Service Domain**     | Party-Authentication                 |
| **Behavior Qualifier** | authentication-devices               |
| **Action Term**        | update                               |


## API Request

| **Nombre del Campo**                                                 | **Descripción**                                                                | **Tipo**  | **Cardinalidad** |
|----------------------------------------------------------------------|--------------------------------------------------------------------------------|-----------|------------------|
| **Header param**                                                     | Parámetros de la cabecera                                                      |           |                  |
| **Path param**                                                       | Parametros de la URL                                                           |           |                  |
| **Query param**                                                      | Parámetros de la consulta                                                      |           |                  |
| MobilePhoneNumber                                                    | El número de teléfono de destino para verificar.                               | intenger  | [1..1]           |


## API Response

| **Nombre del Campo**                                           | **Descripción**                                                                                  | **Tipo**  | **Cardinalidad** |
|----------------------------------------------------------------|--------------------------------------------------------------------------------------------------|-----------|------------------|
| **Header param**                                               |                                                                                                  |           |                  |
| **HTTP Code**                                                  | Codigo HTTP de respuesta                                                                         | integer   | [1..1]           |
| **HTTP Status**                                                | Mensaje HTTP de respuesta                                                                        | string    | [1..1]           |
| **Body**                                                       |                                                                                                  |           |                  |
| **UpdateAuthenticationDevicesResponse**                        | Objeto que contiene los datos de respuesta                                                       | object    | [1..1]           |
| UpdateAuthenticationDevicesResponse.TransactionIdentification  | Un identificador que permite hacer referencia de forma única a una instancia de una transacción. | intenger  | [1..1]           |


## API Response Error

| **Body Error**               | **Descripción**                                    | **Tipo**    | **Cardinalidad** |
|------------------------------|----------------------------------------------------|:-----------:|:----------------:|
| **error**                    | Objeto que contiene la información del error       | array       | [0..n]           |
| error[*].status_code         | Código de error                                    | string      | [1..1]           |
| error[*].message             | mensaje de error                                   | string      | [1..1]           |
