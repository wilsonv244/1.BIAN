# API Payment Execution Service Fees - Documentación

## Descripción General
**Función:**  Validar Otp Comprobar Telefono: Servicio para validar el OTP x SMS con el fin de comprobar el número de teléfono del cliente



| **API SPECIFICATION** |                                                                               |
|-----------------------|------------------------------------------------------------------------------ |
| **API Name**          | /customer-management-onboarding-b                                             |
| **Version**           | v1                                                                            |
| **Method**            | POST                                                                          |
| **Base Path**         | /customer-management-onboarding-b/v1                                          |
| **Path**              | /authentication-device/evaluate                                               |
| **URI**               | POST /customer-management-onboarding-b/v1/authentication-device/evaluate      |


| **BACKEND SERVICE**|                                         |
|--------------------|-----------------------------------------|
| **Protocol**       | JSON                                    |
| **URL**            | http://url-backend.com/basepath/path    |
| **Description**    | Breve descripción del backend           |



| **BIAN DEFINITIONS**   |                                      |
|------------------------|--------------------------------------|
| **Business Area**      | Sales and Service                    |
| **Business Domain**    | Cross Channel                        |
| **Service Domain**     | Party Authentication                 |
| **Behavior Qualifier** | authentication-device                |
| **Action Term**        | evaluate                             |


## API Request

| **Nombre del Campo**                                                                     | **Descripción**                                                                           | **Tipo**  | **Cardinalidad** |
|-------------------------------------------------------------------------------           |-----------------------------------------------------------------------------------------  |-----------|------------------|
| **Header param**                                                                         | Parámetros de la cabecera                                                                 |           |                  |
| securityToken                                                                            | Una cadena que representa la llave pública utilizada para la autenticación o autorización |string     | [1..1]           |
| messageIdentification                                                                  | Una cadena que representa la traza de la petición de validación del cliente               |string     | [1..1]           |
| accountIdentification                                                                    | Número de cuenta del cliente                                                              |integer    | [1..1]           |
| **Path param**                                                                           | Parametros de la URL                                                                      |           |                  |
| **Query param**                                                                          | Parámetros de la consulta                                                                 |           |                  |
| PhoneNumber                                                                              | El número de teléfono de destino para verificar.                                          | integer   | [1..1]           |
| **Body**                                                                                 | Cuerpo del mensaje de entrada                                                             | object    | [1..1]           |
| **EvaluateAuthenticationDevice**                                                         | Objeto que contiene los datos de solicitud                                                | object    | [1..1]           |
| **EvaluateAuthenticationDevice.MessageIdentification**                                   | Reglas de validación                                                                      | object    | [1..1]           |
| EvaluateAuthenticationDevice.MessageIdentification.CustomerValidationRetrieve                | Traza de la petición validar cliente CLA                                                  | integer   | [1..1]           |
| EvaluateAuthenticationDevice.MessageIdentification.KeynuaHashEvaluate                                | Traza de la petición con Keynua                                                           | string    | [1..1]           |
| EvaluateAuthenticationDevice.MessageIdentification.AuthenticationDevicesRegister                                | Traza de la petición de OTP.                                                 | string    | [1..1]           |
| **EvaluateAuthenticationDevice.AuthenticationMethod**              | Reglas de validación                                                                      | object   | [1..1]           |
| EvaluateAuthenticationDevice.AuthenticationMethod.OneTimePassword  | Verificación de una contraseña de un solo uso proporcionada por el emisor. | string    | [1..1]           |

## API Response

| **Nombre del Campo**                                           | **Descripción**                                                                                  | **Tipo**  | **Cardinalidad** |
|----------------------------------------------------------------|--------------------------------------------------------------------------------------------------|-----------|------------------|
| **Header param**                                               |                                                                                                  |           |                  |
| **HTTP Code**                                                  | Codigo HTTP de respuesta                                                                         | integer   | [1..1]           |
| **HTTP Status**                                                | Mensaje HTTP de respuesta                                                                        | string    | [1..1]           |
| **Body**                                                       |                                                                                                  |           |                  |
| **EvaluateAuthenticationDeviceResponse**                       | Objeto que contiene los datos de respuesta                                                       | object    | [1..1]           |
| EvaluateAuthenticationDeviceResponse.AccountIdentification     | Un identificador que permite hacer referencia de forma única a una instancia de una transacción. | intenger  | [1..1]           |

## API Response Error

| **Body Error**               | **Descripción**                                    | **Tipo**    | **Cardinalidad** |
|------------------------------|----------------------------------------------------|:-----------:|:----------------:|
| **error**                    | Objeto que contiene la información del error       | array       | [0..n]           |
| error[*].status_code         | Código de error                                    | string      | [1..1]           |
| error[*].message             | mensaje de error                                   | string      | [1..1]           |
