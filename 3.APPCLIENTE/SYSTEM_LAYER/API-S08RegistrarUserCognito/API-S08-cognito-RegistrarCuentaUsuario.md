# API Payment Execution Service Fees - Documentación

## Descripción General
**Función:** Registrar Enviar Otp Telefono


| **API SPECIFICATION** |                                                                              |
|-----------------------|------------------------------------------------------------------------------|
| **API Name**          | party-authentication-s                                                     |
| **Version**           | v1                                                                           |
| **Method**            | POST                                                                         |
| **Base Path**         | /party-authentication-s/v1                                                  |
| **Path**              | customer-verification/register                                                    |
| **URI**               | POST /party-authentication-s/v1/customer-verification/register                      |


| **BACKEND SERVICE**|                                         |
|--------------------|-----------------------------------------|
| **Protocol**       | JSON                                    |
| **URL**            | http://url-backend.com/basepath/path    |
| **Description**    | Breve descripción del backend           |



| **BIAN DEFINITIONS**   |                                      |
|------------------------|--------------------------------------|
| **Business Area**      | Sales and Service                    |
| **Business Domain**    | Cross Channel                 |
| **Service Domain**     | Party Authentication                 |
| **Behavior Qualifier** | customer-verification                     |
| **Action Term**        | register                             |


## API Request

| **Nombre del Campo**                                                       | **Descripción**                                                                | **Tipo**  | **Cardinalidad** |
|----------------------------------------------------------------------      |--------------------------------------------------------------------------------|-----------|------------------|
| **Header param**                                                           | Parámetros de la cabecera                                                      |           |                  |
| **Path param**                                                             | Parametros de la URL                                                           |           |                  |
| **Query param**                                                            | Parámetros de la consulta                                                      |           |                  |
| **Body**                                                                   | Cuerpo del mensaje de entrada                                                  | object    | [1..1]           |
| **RegisterCustomerVerification**                                                 | Objeto que contiene los datos de solicitud                                     | object    | [1..1]           |
| **RegisterCustomerVerification.Account**                                         | Objeto que contiene el id cuenta                                               | object    | [1..1]           |
| RegisterCustomerVerification.Account.AccountIdentification                       | id cuenta                                                                      | integer   | [1..1]           |
| **RegisterCustomerVerification.PersonIdentification**                            | Objeto que contiene datos de identificacion                                    | object    | [1..1]           |
| RegisterCustomerVerification.PersonIdentification.CustomerIdentificationNumber   | id cliente                                                                     | integer   | [1..1]           |
| RegisterCustomerVerification.PersonIdentification.TypeOfIdentification           | tipo de identificacion                                                         | integer   | [1..1]           |
| RegisterCustomerVerification.PersonIdentification.IdentityCardNumber             | Número de DNI                                                                  | integer   | [1..1]           |
| **RegisterCustomerVerification.Contact**                           | Objeto que contiene datos de contacto                                          | object    | [1..1]           |
| RegisterCustomerVerification.Contact.Name                          | nombre del contacto                                                            | string    | [1..1]           |
| RegisterCustomerVerification.Contact.EmailAddress                  | correo electronico                                                             | string    | [1..1]           |
| RegisterCustomerVerification.Contact.PhoneNumber                   | Número de teléfono móvil de contacto                                           | integer   | [1..1]           |
| **RegisterCustomerVerification.AuthenticationMethod**                            | Objeto que contiene metodo de autenticacion                                    | object    | [1..1]           |
| RegisterCustomerVerification.AuthenticationMethod.Password                       | contrasena                                                                     | string    | [1..1]           |
| **RegisterCustomerVerification.DeviceIdentification**                            | Objeto que contiene datos de identificacion del dispositivo                    | object    | [1..1]           |
| RegisterCustomerVerification.DeviceIdentification.IMEI                           | código identifica al aparato de forma exclusiva a nivel mundiaL                | integer   | [1..1]           |
| RegisterCustomerVerification.DeviceIdentification.MAC                            | dirección física, y es única para cada dispositivo                             | string    | [1..1]           |
| **RegisterCustomerVerification.Device**                                          | Objeto que contiene datos de la apliccion                                      | object    | [1..1]           |
| RegisterCustomerVerification.Device.ApplicationVersion                           | version de la aplicacion                                                       | string    | [1..1]           |


## API Response

| **Nombre del Campo**                                              | **Descripción**                                                                                  | **Tipo**  | **Cardinalidad** |
|-------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|-----------|------------------|
| **Header param**                                                  |                                                                                                  |           |                  |
| **HTTP Code**                                                     | Codigo HTTP de respuesta                                                                         | integer   | [1..1]           |
| **HTTP Status**                                                   | Mensaje HTTP de respuesta                                                                        | string    | [1..1]           |
| **Body**                                                          |                                                                                                  |           |                  |
| **RegisterCustomerVerificationResponse**                                | Objeto que contiene los datos de respuesta                                                       | object    | [1..1]           |
| **RegisterCustomerVerificationResponse.AuthenticationMethod**       | Objeto que contiene los datos de respuesta                                                       | object    | [1..1]           |
| RegisterCustomerVerificationResponse.AuthenticationMethod.CognitoAuthIdentifier       | Un identificador que permite hacer referencia de forma única a una instancia de una transacción. | string    | [1..1]           |


## API Response Error

| **Body Error**               | **Descripción**                                    | **Tipo**    | **Cardinalidad** |
|------------------------------|----------------------------------------------------|:-----------:|:----------------:|
| **error**                    | Objeto que contiene la información del error       | array       | [0..n]           |
| error[*].status_code         | Código de error                                    | string      | [1..1]           |
| error[*].message             | mensaje de error                                   | string      | [1..1]           |
