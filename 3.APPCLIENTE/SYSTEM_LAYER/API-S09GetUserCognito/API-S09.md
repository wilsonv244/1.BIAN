# API Party Authentication- Documentación

## Descripción General
**Función:** Obtener cuenta de usuario de AWS cognito.


| **API SPECIFICATION** |                                                                           |
|-----------------------|---------------------------------------------------------------------------|
| **API Name**          | party-authentication-s                                                    |
| **Version**           | v1                                                                        |
| **Method**            | GET                                                                       |
| **Base Path**         | /party-authentication-s/v1                                                 |
| **Path**              | /customer-verification/retrieve                                      |
| **URI**               | GET /party-authentication-s/v1/customer-verification/retrieve         |


| **BACKEND SERVICE**|                                         |
|--------------------|-----------------------------------------|
| **Protocol**       | JSON                                    |
| **URL**            | http://url-backend.com/basepath/path    |
| **Description**    | Breve descripción del backend           |



| **BIAN DEFINITIONS**   |                                    |
|------------------------|------------------------------------|
| **Business Area**      | Sales and Service                  |
| **Business Domain**    | Cross Channel               |
| **Service Domain**     | Party Authentication    |
| **Behavior Qualifier** | customer-verification           |
| **Action Term**        | retrieve                           |

## API Request

| **Nombre del Campo  *         | ** Descripción **                                                          | **Tipo**    | **Cardinalidad** |
|-------------------------------|----------------------------------------------------------------------------|-------------|------------------|
| **Header param**              |                                                                            |             |                  |
| **Path param**                |                                                                            |             |                  |
| **Query param**               |                                                                            |             |                  |
| cognitoAuthIdentifier      | Identificador del proveedor de autenticación.       | string     | [1..1]            |
| **Body**                                                             | Cuerpo del mensaje de solicitud                                            | object      | [1..1]           |

## API Response

| **Nombre del Campo**                                                     | **Descripción**                                                                  | **Tipo**   | **Cardinalidad**  |
|--------------------------------------------------------------------------|----------------------------------------------------------------------------------|:----------:|:-----------------:|
| **Header param**                                                         |                                                                                  |            |                   |
| **HTTP Code**                                                            | Código HTTP de respuesta                                                         | integer    | [1..1]            |
| **HTTP Status**                                                          | Mensaje HTTP de respuesta                                                        | string     | [1..1]            |
| **Body Successful**                                                      | Objeto que almacena el mensaje se solicitud                                                    | object     | [1..1]            |
| **RetrieveCustomerVerificationResponse**                                     | Objeto que almacena el mensaje de solicitud.                                                                  | object     | 1..1              |
| **RetrieveCustomerVerificationResponse.Account**                             | Objeto que administra la información de las cuentas.                                                          | object     | 1..1              |
| RetrieveCustomerVerificationResponse.Account.AccountIdentification           | Número de cuenta del cliente.                                                                                 | integer    | 1..1              |
| **RetrieveCustomerVerificationResponse.AuthenticationMethod**                | Objeto que contiene método de autenticación.                                                                  | object     | 1..1              |
| RetrieveCustomerVerificationResponse.AuthenticationMethod.CognitoAuthIdentifier | Identificador del proveedor de autenticación.                                                             | string     | 1..1              |
| RetrieveCustomerVerificationResponse.AuthenticationMethod.Password           | Autenticación mediante una contraseña.                                                                        | string     | 1..1              |
| **RetrieveCustomerVerificationResponse.PersonIdentification**                | Objeto que almacena información relacionada con la identificación del cliente.                                | object     | 1..1              |
| RetrieveCustomerVerificationResponse.PersonIdentification.CustomerIdentificationNumber | Número único asignado por el banco para identificar al cliente.                                          | integer    | 1..1              |
| RetrieveCustomerVerificationResponse.PersonIdentification.TypeOfIdentification | Determina el ID del tipo de documento.                                                                   | integer    | 1..1              |
| RetrieveCustomerVerificationResponse.PersonIdentification.IdentityCardNumber | Número asignado por una autoridad nacional a una tarjeta de identidad.                                    | string     | 1..1              |
| **RetrieveCustomerVerificationResponse.PersonName**                          | Objeto que almacena información relacionada al cliente.                                                       | object     | 1..1              |
| RetrieveCustomerVerificationResponse.PersonName.LastName                     | Determina el apellido paterno de la persona.                                                                  | string     | 1..1              |
| RetrieveCustomerVerificationResponse.PersonName.MothersLastName              | Determina el apellido materno de la persona.                                                                  | string     | 1..1              |
| RetrieveCustomerVerificationResponse.PersonName.GivenName                    | Determina el primer nombre o nombres dados de la persona.                                                     | string     | 1..1              |
| **RetrieveCustomerVerificationResponse.Contact**                             | Objeto que almacena información de contacto relacionada al cliente.                                           | object     | 1..1              |
| RetrieveCustomerVerificationResponse.Contact.EmailAddress                    | Dirección de correo electrónico.                                                                              | string     | 1..1              |
| RetrieveCustomerVerificationResponse.Contact.PhoneNumber                     | Colección de información que identifica un número de teléfono, según lo definido por los servicios de telecomunicaciones. | string     | 1..1              |
| **RetrieveCustomerVerificationResponse.Device**                              | Objeto que almacena información del dispositivo del cliente.                                                  | object     | 1..1              |
| RetrieveCustomerVerificationResponse.Device.ApplicationVersion               | Este campo almacena la versión de la aplicación que está siendo utilizada en el dispositivo.                   | string     | 1..1              |
| **RetrieveCustomerVerificationResponse.Device.DeviceIdentification**         | Objeto que almacena identificadores únicos del dispositivo.                                                   | object     | 1..1              |
| RetrieveCustomerVerificationResponse.Device.DeviceIdentification.IMEI        | El IMEI del dispositivo, que es un identificador único de 15 dígitos para dispositivos móviles.                | string     | 1..1              |
| RetrieveCustomerVerificationResponse.Device.DeviceIdentification.MAC         | La dirección MAC del dispositivo, que es un identificador único para la interfaz de red.                       | string     | 1..1              |


## API Response Error

| **Body Error**               | **Descripción**                                    | **Tipo**    | **Cardinalidad** |
|------------------------------|----------------------------------------------------|:-----------:|:----------------:|
| **error**                    | Objeto que contiene la información del error       | array       | [0..n]           |
| error[*].status_code         | Código de error                                    | string      | [1..1]           |
| error[*].message             | mensaje de error                                   | string      | [1..1]           |
