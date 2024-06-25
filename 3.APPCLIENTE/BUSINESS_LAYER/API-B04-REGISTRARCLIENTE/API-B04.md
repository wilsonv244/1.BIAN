# API Customer Management Onboarding- Documentación

## Descripción General
**Función:** Registrar información básica del cliente, dispositivo y acuerdos.


| **API SPECIFICATION** |                                                                           |
|-----------------------|---------------------------------------------------------------------------|
| **API Name**          | customer-management-onboarding-b                                                  |
| **Version**           | v1                                                                        |
| **Method**            | POST                                                                       |
| **Base Path**         | /customer-management-onboarding-b/v1                                                 |
| **Path**              | /customer-account/register                                     |
| **URI**               | POST /customer-management-onboarding-b/v1/customer-account/register         |


| **BACKEND SERVICE**|                                         |
|--------------------|-----------------------------------------|
| **Protocol**       | JSON                                    |
| **URL**            | http://url-backend.com/basepath/path    |
| **Description**    | Breve descripción del backend           |



| **BIAN DEFINITIONS**   |                                    |
|------------------------|------------------------------------|
| **Business Area**      |                 |
| **Business Domain**    |             |
| **Service Domain**     |    |
| **Behavior Qualifier** | customer-account           |
| **Action Term**        | register                           |

## API Request

| **Nombre del Campo  *         | ** Descripción **                                                          | **Tipo**    | **Cardinalidad** |
|-------------------------------|----------------------------------------------------------------------------|-------------|------------------|
| **Header param**              |                                                                            |             |                  |
| **Path param**                |                                                                            |             |                  |
| **Query param**               |                                                                            |             |                  |
| securityToken               | Llave secreta para consumir los servicios sin JWT.               | string     | 1..1         |
| messageIdentification       | Traza de la petición de registro de cliente.                     | string     | 1..1         |
| accountIdentification       | Número de cuenta del cliente.                                    | string     | 1..1         |
| **Body**                                                             | Cuerpo del mensaje de solicitud                                            | object      | [1..1]           |

## API Response

| **Nombre del Campo**                                                     | **Descripción**                                                                  | **Tipo**   | **Cardinalidad**  |
|--------------------------------------------------------------------------|----------------------------------------------------------------------------------|:----------:|:-----------------:|
| **Header param**                                                         |                                                                                  |            |                   |
| **HTTP Code**                                                            | Código HTTP de respuesta                                                         | integer    | [1..1]            |
| **HTTP Status**                                                          | Mensaje HTTP de respuesta                                                        | string     | [1..1]            |
| **Body Successful**                                                      | Objeto que almacena el mensaje se solicitud                                                    | object     | [1..1]            |
| **RegisterCustomerAccount**                                                                | Objeto que almacena el mensaje de solicitud.                                | object   | 1..1         |
| **RegisterCustomerAccount.Account**                                                        | Objeto que administra la información de las cuentas.                        | object   | 1..1         |
| RegisterCustomerAccount.Account.AccountIdentification                                      | Número de cuenta del cliente.                                               | string   | 1..1         |
| **RegisterCustomerAccount.AuthenticationMethod**                                           | Objeto que contiene método de autenticación.                                | object   | 1..1         |
| RegisterCustomerAccount.AuthenticationMethod.CognitoAuthIdentifier                         | Identificador del proveedor de autenticación.                               | string   | 1..1         |
| RegisterCustomerAccount.AuthenticationMethod.Password                                      | Autenticación mediante una contraseña.                                      | string   | 1..1         |
| **RegisterCustomerAccount.PersonIdentification**                                           | Objeto que almacena información relacionada con la identificación del cliente. | object   | 1..1         |
| RegisterCustomerAccount.PersonIdentification.CustomerIdentificationNumber                  | Número único asignado por el banco para identificar al cliente.             | integer  | 1..1         |
| RegisterCustomerAccount.PersonIdentification.TypeOfIdentification                          | Determina el ID del tipo de documento.                                      | integer  | 1..1         |
| RegisterCustomerAccount.PersonIdentification.IdentityCardNumber                            | Número asignado por una autoridad nacional a una tarjeta de identidad.      | string   | 1..1         |
| **RegisterCustomerAccount.PersonName**                                                     | Objeto que almacena información relacionada al cliente.                     | object   | 1..1         |
| RegisterCustomerAccount.PersonName.LastName                                                | Determina el apellido paterno de la persona.                                | string   | 1..1         |
| RegisterCustomerAccount.PersonName.MothersLastName                                         | Determina el apellido materno de la persona.                                | string   | 1..1         |
| RegisterCustomerAccount.PersonName.GivenName                                               | Determina el primer nombre o nombres dados de la persona.                   | string   | 1..1         |
| **RegisterCustomerAccount.Contact**                                                        | Objeto que almacena información de contacto relacionada al cliente.         | object   | 1..1         |
| RegisterCustomerAccount.Contact.EmailAddress                                               | Dirección de correo electrónico.                                            | string   | 1..1         |
| RegisterCustomerAccount.Contact.PhoneNumber                                                | Colección de información que identifica un número de teléfono, según lo definido por los servicios de telecomunicaciones. | string   | 1..1         |
| **RegisterCustomerAccount.Device**                                                         | Objeto que almacena información del dispositivo del cliente.                | object   | 1..1         |
| RegisterCustomerAccount.Device.ApplicationVersion                                          | Este campo almacena la versión de la aplicación que está siendo utilizada en el dispositivo. | string   | 1..1         |
| RegisterCustomerAccount.Device.DeviceOperatingSystem                                       | El sistema operativo instalado en el dispositivo.                           | string   | 1..1         |
| RegisterCustomerAccount.Device.DeviceModel                                                 | Este campo almacena el modelo del dispositivo.                              | string   | 1..1         |
| RegisterCustomerAccount.Device.DeviceVersion                                               | Versión de sistema operativo.                                               | string   | 1..1         |
| RegisterCustomerAccount.Device.CountryCode                                                 | Código para identificar un país, basado en los nombres de los países obtenidos de las Naciones Unidas. | string   | 1..1         |
| RegisterCustomerAccount.Device.LatitudeAddress                                             | La latitud de la ubicación del dispositivo.                                 | string   | 1..1         |
| RegisterCustomerAccount.Device.LongitudeAddress                                            | La longitud de la ubicación del dispositivo.                                | string   | 1..1         |
| RegisterCustomerAccount.Device.DeviceAddress                                               | La dirección asociada con el dispositivo, como la dirección de Protocolo de Internet (IP) o la dirección de correo electrónico. | string   | 1..1         |
| RegisterCustomerAccount.Device.PackageIdentification                                       | Identificación de los paquetes de software a los que pertenece el fragmento. | string   | 1..1         |
| **RegisterCustomerAccount.Device.DeviceIdentification**                                    | Objeto que almacena identificadores únicos del dispositivo.                 | object   | 1..1         |
| RegisterCustomerAccount.Device.DeviceIdentification.IMEI                                   | El IMEI del dispositivo, que es un identificador único de 15 dígitos para dispositivos móviles. | string   | 1..1         |
| RegisterCustomerAccount.Device.DeviceIdentification.MAC                                    | La dirección MAC del dispositivo, que es un identificador único para la interfaz de red. | string   | 1..1         |
| **RegisterCustomerAccount.MailingInstructions**                                            | Objeto que almacena características de una dirección.                       | object   | 1..1         |
| RegisterCustomerAccount.MailingInstructions.MailingIndicator                               | Indica si el correo debe enviarse a una dirección.                          | string   | 1..1         |
| **RegisterCustomerAccount.MessageIdentification**                                          | Identifica un mensaje mediante un identificador único y la fecha y hora en que el remitente creó el mensaje. | string   | 1..1         |
| RegisterCustomerAccount.MessageIdentification.CustomerValidationRetrieve                                  | Traza de la petición validar cliente CLA                                | string   | 1..1         |
| RegisterCustomerAccount.MessageIdentification.KeynuaHashEvaluate                                  | Token ID de resultado satisfactorio Plugin Keynua.                          | string   | 1..1         |
| RegisterCustomerAccount.MessageIdentification.AuthenticationDeviceRegister                              | Traza de la petición de OTP.                                                | string   | 1..1         |
| RegisterCustomerAccount.MessageIdentification.AuthenticationDeviceUpdate                             | Traza de la validación de OTP.                                              | string   | 1..1         |
| **CaptureCustomerAndDeviceInfo.Agreements[n]**                                             | Array que almacena un acuerdo común, formal o informal, entre dos o más partes. | array    | 0..*         |
| CaptureCustomerAndDeviceInfo.Agreements[n].AgreementIdentification                         | El identificador del acuerdo, como el Número de Acuerdo, Número de Contrato, Número de Registro de Contrato, etc. | integer  | 1..1         |
| CaptureCustomerAndDeviceInfo.Agreements[n].AgreementStatus                                 | Una característica del acuerdo que se refiere al Estado del Ciclo de Vida del acuerdo. | string   | 1..1         |


## API Response Error

| **Body Error**       | **Descripción**                              | **Tipo** | **Cardinalidad** |
|----------------------|----------------------------------------------|:--------:|:----------------:|
| **status_code**      | Código de error                              | string   | [1..1]           |
| **status**           | Estado de la respuesta                       | string   | [1..1]           |
| **message**          | Mensaje de error                             | string   | [1..1]           |
