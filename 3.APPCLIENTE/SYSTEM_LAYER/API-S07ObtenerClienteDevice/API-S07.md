# API Party Reference Data Directory - Documentación

## Descripción General
**Función:** Obtener datos de la cuenta del cliente y detalles del dispositivo.


| **API SPECIFICATION** |                                                                           |
|-----------------------|---------------------------------------------------------------------------|
| **API Name**          | party-reference-data-directory-s                                          |
| **Version**           | v1                                                                        |
| **Method**            | GET                                                                       |
| **Base Path**         | /party-reference-data-directory-s/v1                                      |
| **Path**              | /customer-and-device-info/retrieve                                        |
| **URI**               | GET /party-reference-data-directory-s/v1/customer-and-device-info/retrieve|


| **BACKEND SERVICE**|                                         |
|--------------------|-----------------------------------------|
| **Protocol**       | JSON                                    |
| **URL**            | http://url-backend.com/basepath/path    |
| **Description**    | Breve descripción del backend           |



| **BIAN DEFINITIONS**   |                                    |
|------------------------|------------------------------------|
| **Business Area**      | Sales and Service                  |
| **Business Domain**    | Customer Management                |
| **Service Domain**     | Party Reference Data Directory     |
| **Behavior Qualifier** | customer-and-device-info           |
| **Action Term**        | retrieve                           |

## API Request

| **Nombre del Campo  *         | ** Descripción **                                                          | **Tipo**    | **Cardinalidad** |
|-------------------------------|----------------------------------------------------------------------------|-------------|------------------|
| **Header param**              |                                                                            |             |                  |
| **Path param**                |                                                                            |             |                  |
| **Query param**               |                                                                            |             |                  |
| accountIdentification      | Número de cuenta del cliente.       | integer     | [1..1]            |
| **Body**                                                             | Cuerpo del mensaje de solicitud                                            | object      | [1..1]           |

## API Response

| **Nombre del Campo**                                                     | **Descripción**                                                                  | **Tipo**   | **Cardinalidad**  |
|--------------------------------------------------------------------------|----------------------------------------------------------------------------------|:----------:|:-----------------:|
| **Header param**                                                         |                                                                                  |            |                   |
| **HTTP Code**                                                            | Código HTTP de respuesta                                                         | integer    | [1..1]            |
| **HTTP Status**                                                          | Mensaje HTTP de respuesta                                                        | string     | [1..1]            |
| **Body Successful**                                                      | Objeto que almacena el mensaje se solicitud                                                    | object     | [1..1]            |
| **RetrieveCustomerAndDeviceInfoResponse**                                                 | Objeto que almacena el mensaje de solicitud.                                                                   | object     | 1..1              |
| **RetrieveCustomerAndDeviceInfoResponse.Account**                                         | Objeto que administra la información de las cuentas.                                                           | object     | 1..1              |
| RetrieveCustomerAndDeviceInfoResponse.Account.AccountIdentification                              | Número de cuenta del cliente.                                                                                  | integer    | 1..1              |
| **RetrieveCustomerAndDeviceInfoResponse.AuthenticationMethod**                                    | Objeto que contiene metodo de autenticación.                                              | object     | 1..1              |
| RetrieveCustomerAndDeviceInfoResponse.AuthenticationMethod.CognitoAuthIdentifier                     | Identificador del proveedor de autenticación.                                                                  | string     | 1..1              |
| **RetrieveCustomerAndDeviceInfoResponse.PersonIdentification**                             | Objeto que almacena información relacionada con la identificación del cliente.                                 | object     | 1..1              |
| RetrieveCustomerAndDeviceInfoResponse.PersonIdentification.CustomerIdentificationNumber    | Número único asignado por el banco para identificar al cliente.                                                | integer    | 1..1              |
| RetrieveCustomerAndDeviceInfoResponse.PersonIdentification.TypeOfIdentification            | Determina el ID del tipo de documento.                                                                         | integer    | 1..1              |
| RetrieveCustomerAndDeviceInfoResponse.PersonIdentification.IdentityCardNumber              | Número asignado por una autoridad nacional a una tarjeta de identidad.                                          | string     | 1..1              |
| **RetrieveCustomerAndDeviceInfoResponse.PersonName**                                      | Objeto que almacena información relacionada al cliente.                                                        | object     | 1..1              |
| RetrieveCustomerAndDeviceInfoResponse.PersonName.LastName                                 | Determina el apellido paterno de la persona.                                                                   | string     | 1..1              |
| RetrieveCustomerAndDeviceInfoResponse.PersonName.MothersLastName                          | Determina el apellido materno de la persona.                                                                   | string     | 1..1              |
| RetrieveCustomerAndDeviceInfoResponse.PersonName.GivenName                                | Determina el primer nombre o nombres dados de la persona.                                                      | string     | 1..1              |
| **RetrieveCustomerAndDeviceInfoResponse.Contact**                                         | Objeto que almacena información de contacto relacionada al cliente.                                            | object     | 1..1              |
| RetrieveCustomerAndDeviceInfoResponse.Contact.EmailAddress                                | Dirección de correo electrónico.                                                                               | string     | 1..1              |
| RetrieveCustomerAndDeviceInfoResponse.Contact.PhoneNumber                                 | Colección de información que identifica un número de teléfono, según lo definido por los servicios de telecomunicaciones. | string     | 1..1              |
| **RetrieveCustomerAndDeviceInfoResponse.Device**                                          | Objeto que almacena información del dispositivo del cliente.                                                   | object     | 1..1              |
| RetrieveCustomerAndDeviceInfoResponse.Device.DeviceModel                                  | Este campo almacena el modelo del dispositivo.                                                                 | string     | 1..1              |
| RetrieveCustomerAndDeviceInfoResponse.Device.ApplicationVersion                           | Este campo almacena la versión de la aplicación que está siendo utilizada en el dispositivo.                   | string     | 1..1              |
| RetrieveCustomerAndDeviceInfoResponse.Device.DeviceIdentification                         | Objeto que almacena identificadores únicos del dispositivo.                                                    | object     | 1..1              |
| RetrieveCustomerAndDeviceInfoResponse.Device.DeviceIdentification.IMEI                    | El IMEI del dispositivo, que es un identificador único de 15 dígitos para dispositivos móviles.                | string     | 1..1              |
| RetrieveCustomerAndDeviceInfoResponse.Device.DeviceIdentification.MAC      | La dirección MAC del dispositivo, que es un identificador único para la interfaz de red.                       | string     | 1..1              |

## API Response Error

| **Body Error**               | **Descripción**                                    | **Tipo**    | **Cardinalidad** |
|------------------------------|----------------------------------------------------|:-----------:|:----------------:|
| **error**                    | Objeto que contiene la información del error       | array       | [0..n]           |
| error[*].status_code         | Código de error                                    | string      | [1..1]           |
| error[*].message             | mensaje de error                                   | string      | [1..1]           |
