# API Payment Execution Service Fees - Documentación

## Descripción General
**Función:** Registrar Enviar Otp Telefono



| **API SPECIFICATION** |                                                                               |
|-----------------------|------------------------------------------------------------------------------ |
| **API Name**          | party-authentication-s                                                        |
| **Version**           | v1                                                                            |
| **Method**            | POST                                                                          |
| **Base Path**         | /party-authentication-s/v1                                                    |
| **Path**              | /authentication-devices/register                                              |
| **URI**               | POST /party-authentication-s/v1/authentication-devices/register               |


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
| **Action Term**        | register                             |


## API Request

| **Nombre del Campo**                                                 | **Descripción**                                                                | **Tipo**  | **Cardinalidad** |
|----------------------------------------------------------------------|--------------------------------------------------------------------------------|-----------|------------------|
| **Header param**                                                     | Parámetros de la cabecera                                                      |           |                  |
| **Path param**                                                       | Parametros de la URL                                                           |           |                  |
| **Query param**                                                      | Parámetros de la consulta                                                      |           |                  |
| **Body**                                                             | Cuerpo del mensaje de entrada                                                  | object    | [1..1]           |
| **RegisterAuthenticationDevices**                                    | Objeto que contiene los datos de solicitud                                     | object    | [1..1]           |
| **RegisterAuthenticationDevices.Contact**                            | Reglas de validación                                                           | object    | [1..1]           |
| RegisterAuthenticationDevicea.Contact.MobilePhoneNumber              | Número de teléfono móvil de contacto                                           | string    | [1..1]           |


## API Response

| **Nombre del Campo**                                              | **Descripción**                                                                                  | **Tipo**  | **Cardinalidad** |
|-------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|-----------|------------------|
| **Header param**                                                  |                                                                                                  |           |                  |
| **HTTP Code**                                                     | Codigo HTTP de respuesta                                                                         | integer   | [1..1]           |
| **HTTP Status**                                                   | Mensaje HTTP de respuesta                                                                        | string    | [1..1]           |
| **Body**                                                          |                                                                                                  |           |                  |
| **RegisterAuthenticationDevicesResponse**                         | Objeto que contiene los datos de respuesta                                                       | object    | [1..1]           |
| RegisterAuthenticationDevicesResponse.TransactionIdentification   | Un identificador que permite hacer referencia de forma única a una instancia de una transacción. | string    | [1..1]           |


## API Response Error

| **Body Error**               | **Descripción**                                    | **Tipo**    | **Cardinalidad** |
|------------------------------|----------------------------------------------------|:-----------:|:----------------:|
| **error**                    | Objeto que contiene la información del error       | array       | [0..n]           |
| error[*].status_code         | Código de error                                    | string      | [1..1]           |
| error[*].message             | mensaje de error                                   | string      | [1..1]           |
