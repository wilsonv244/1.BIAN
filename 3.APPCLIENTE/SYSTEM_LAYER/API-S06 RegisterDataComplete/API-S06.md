# API Party Reference Data Directory - Documentación

## Descripción General
**Función:** Registrar datos de la cuenta del cliente, detalles del dispositivo y acuerdos.


| **API SPECIFICATION** |                                                                           |
|-----------------------|---------------------------------------------------------------------------|
| **API Name**          | party-reference-data-directory-s                                          |
| **Version**           | v1                                                                        |
| **Method**            | PATCH                                                                       |
| **Base Path**         | /party-reference-data-directory-s/v1                                      |
| **Path**              | /customer-and-device-info/capture                                        |
| **URI**               | PATCH /party-reference-data-directory-s/v1/customer-and-device-info/capture|


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
| **Action Term**        | capture                          |

## API Request

| **Nombre del Campo  *         | ** Descripción **                                                          | **Tipo**    | **Cardinalidad** |
|-------------------------------|----------------------------------------------------------------------------|-------------|------------------|
| **Header param**              |                                                                            |             |                  |
| **Path param**                |                                                                            |             |                  |
| **Query param**               |                                                                            |             |                  |
| accountIdentification      | Número de cuenta del cliente.       | integer     | [1..1]            |
| **Body**                                                             | Cuerpo del mensaje de solicitud                                            | object      | [1..1]           |
| **CaptureCustomerAndDeviceInfo**                                                      | Objeto que almacena el mensaje se solicitud                                                    | object     | 1..1            |
| **CaptureCustomerAndDeviceInfo.Account**                                              | Objeto que administra la información de las cuentas.                                            | object     | 1..1            |
| CaptureCustomerAndDeviceInfo.Account.AccountIdentification                            | Número de cuenta del cliente.                                                                   | integer    | 1..1            |
| **CaptureCustomerAndDeviceInfo.AuthenticationMethod**                                         | Objeto que contiene metodo de autenticación.                              | object     | 1..1            |
| CaptureCustomerAndDeviceInfo.AuthenticationMethod.CognitoAuthIdentifier                          | Identificador del proveedor de autenticación.                                                   | string     | 1..1            |
| **CaptureCustomerAndDeviceInfo.PersonIdentification**                                  | Objeto que almacena información relacionada con la identificación del cliente.                  | object     | 1..1            |
| CaptureCustomerAndDeviceInfo.PersonIdentification.CustomerIdentificationNumber         | Número único asignado por el banco para identificar al cliente.                                  | integer    | 1..1            |
| CaptureCustomerAndDeviceInfo.PersonIdentification.TypeOfIdentification                 | Determina el ID del tipo de documento.                                                          | integer    | 1..1            |
| CaptureCustomerAndDeviceInfo.PersonIdentification.IdentityCardNumber                   | Número asignado por una autoridad nacional a una tarjeta de identidad.                          | string     | 1..1            |
| **CaptureCustomerAndDeviceInfo.PersonName**                                           | Objeto que almacena información relacionada al cliente.                                         | object     | 1..1            |
| CaptureCustomerAndDeviceInfo.PersonName.LastName                                      | Determina el apellido paterno de la persona.                                                    | string     | 1..1            |
| CaptureCustomerAndDeviceInfo.PersonName.MothersLastName                               | Determina el apellido materno de la persona.                                                    | string     | 1..1            |
| CaptureCustomerAndDeviceInfo.PersonName.GivenName                                     | Determina el primer nombre o nombres dados de la persona.                                       | string     | 1..1            |
| **CaptureCustomerAndDeviceInfo.Contact**                                              | Objeto que almacena información de contacto relacionada al cliente.                             | object     | 1..1            |
| CaptureCustomerAndDeviceInfo.Contact.EmailAddress                                     | Dirección de correo electrónico.                                                                | string     | 1..1            |
| CaptureCustomerAndDeviceInfo.Contact.PhoneNumber                                      | Colección de información que identifica un número de teléfono, según lo definido por los servicios de telecomunicaciones. | string     | 1..1            |
| **CaptureCustomerAndDeviceInfo.Device**                                               | Objeto que almacena información del dispositivo del cliente.                                    | object     | 1..1            |
| CaptureCustomerAndDeviceInfo.Device.DeviceModel                                       | Este campo almacena el modelo del dispositivo.                                                  | string     | 1..1            |
| CaptureCustomerAndDeviceInfo.Device.ApplicationVersion                                | Este campo almacena la versión de la aplicación que está siendo utilizada en el dispositivo.    | string     | 1..1            |
| CaptureCustomerAndDeviceInfo.Device.DeviceOperatingSystem                             | El sistema operativo instalado en el dispositivo.                                               | string     | 1..1            |
| CaptureCustomerAndDeviceInfo.Device.DeviceVersion                                     | Versión de sistema operativo.                                                                   | string     | 1..1            |
| CaptureCustomerAndDeviceInfo.Device.CountryCode                                       | Código para identificar un país, basado en los nombres de los países obtenidos de las Naciones Unidas.  | string     | 1..1            |
| CaptureCustomerAndDeviceInfo.Device.LatitudeAddress                                   | La latitud de la ubicación del dispositivo.                                                     | string     | 1..1            |
| CaptureCustomerAndDeviceInfo.Device.LongitudeAddress                                  | La longitud de la ubicación del dispositivo.                                                    | string     | 1..1            |
| CaptureCustomerAndDeviceInfo.Device.DeviceAddress                                     | La dirección asociada con el dispositivo, como la dirección de Protocolo de Internet (IP) o la dirección de correo electrónico. | string     | 1..1            |
| CaptureCustomerAndDeviceInfo.Device.PackageIdentification                             | Identificación de los paquetes de software a los que pertenece el fragmento.                    | string     | 1..1            |
| **CaptureCustomerAndDeviceInfo.Device.DeviceIdentification**                          | Objeto que almacena identificadores únicos del dispositivo.                                     | object     | 1..1            |
| CaptureCustomerAndDeviceInfo.Device.DeviceIdentification.IMEI                         | El IMEI del dispositivo, que es un identificador único de 15 dígitos para dispositivos móviles.  | string     | 1..1            |
| CaptureCustomerAndDeviceInfo.Device.DeviceIdentification.MAC                          | La dirección MAC del dispositivo, que es un identificador único para la interfaz de red.        | string     | 1..1            |
| **CaptureCustomerAndDeviceInfo.MessageIdentification**                                | Identifica un mensaje mediante un identificador único y la fecha y hora en que el remitente creó el mensaje. | string     | 1..1            |
| RegisterCustomerAccount.MessageIdentification.CustomerValidationRetrieve                                  | Traza de la petición validar cliente CLA                                | string   | 1..1         |
| CaptureCustomerAndDeviceInfo.MessageIdentification.KeynuaHashEvaluate                                        | Token ID de resultado satisfactorio Plugin Keynua.                                              | string     | 1..1            |
| CaptureCustomerAndDeviceInfo.MessageIdentification.AuthenticationDeviceRegister                                    | Traza de la petición de OTP.                                                                    | string     | 1..1            |
| CaptureCustomerAndDeviceInfo.MessageIdentification.AuthenticationDeviceUpdate                                   | Traza de la validacion de OTP.                                                                  | string     | 1..1            |
| CaptureCustomerAndDeviceInfo.MessageIdentification.CustomerAccountRegister                               | Traza de la peticion de registro de cliente.                                                               | string     | 1..1            |
| **CaptureCustomerAndDeviceInfo.MailingInstructions**                                  | Objeto que almacena caracteristicas de una direccion.                                           | object     | 1..1            |
| CaptureCustomerAndDeviceInfo.MailingInstructions.MailingIndicator                     | Indica si el correo debe enviarse a una dirección.                                              | integer    | 1..1            |
| **CaptureCustomerAndDeviceInfo.Agreements[n]**                                            | Objeto que almacena un acuerdo común, formal o informal, entre dos o más partes                 | array      | 0..*            |
| CaptureCustomerAndDeviceInfo.Agreements[n].AgreementIdentification                        | El identificador del acuerdo, como el Número de Acuerdo, Número de Contrato, Número de Registro de Contrato, etc. | integer    | 1..1            |
| CaptureCustomerAndDeviceInfo.Agreements[n].AgreementStatus                                | Una característica del acuerdo que se refiere al Estado del Ciclo de Vida del acuerdo.          | string     | 1..1            |


## API Response

| **Nombre del Campo**                                                     | **Descripción**                                                                  | **Tipo**   | **Cardinalidad**  |
|--------------------------------------------------------------------------|----------------------------------------------------------------------------------|:----------:|:-----------------:|
| **Header param**                                                         |                                                                                  |            |                   |
| **HTTP Code**                                                            | Código HTTP de respuesta                                                         | integer    | [1..1]            |
| **HTTP Status**                                                          | Mensaje HTTP de respuesta                                                        | string     | [1..1]            |
| **Body Successful**                                                      | Objeto que almacena el mensaje se solicitud                                                    | object     | [1..1]            |
| **CaptureCustomerAndDeviceInfoResponse**                                                 | Objeto que almacena el mensaje de solicitud.                                                                   | object     | 1..1              |
| **CaptureCustomerAndDeviceInfoResponse.Account**                                         | Objeto que administra la información de las cuentas.                                                           | object     | 1..1              |
| CaptureCustomerAndDeviceInfoResponse.Account.AccountIdentification                              | Número de cuenta del cliente.                                                                                  | integer    | 1..1              |

## API Response Error

| **Body Error**               | **Descripción**                                    | **Tipo**    | **Cardinalidad** |
|------------------------------|----------------------------------------------------|:-----------:|:----------------:|
| **error**                    | Objeto que contiene la información del error       | array       | [0..n]           |
| error[*].status_code         | Código de error                                    | string      | [1..1]           |
| error[*].message             | mensaje de error                                   | string      | [1..1]           |
