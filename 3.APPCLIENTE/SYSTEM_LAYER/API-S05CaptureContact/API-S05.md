# API Party Reference Data irectory - Documentación

## Descripción General
**Función:** Registrar los datos de contacto del cliente proporcionados a través de la APP,  utilizados para el envío de OTP.


| **API SPECIFICATION** |                                                                           |
|-----------------------|---------------------------------------------------------------------------|
| **API Name**          | party-reference-data-directory-s                                          |
| **Version**           | v1                                                                        |
| **Method**            | PATCH                                                                     |
| **Base Path**         | /party-reference-data-directory-s/v1                                      |
| **Path**              | /customer-basic-data/contact/capture                                            |
| **URI**               | PATCH /party-reference-data-directory-s/v1/customer-basic-data/contact/capture  |


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
| **Behavior Qualifier** | customer-basic-data/contact        |
| **Action Term**        | capture                            |

## API Request

| **Nombre del Campo  *         | ** Descripción **                                                          | **Tipo**    | **Cardinalidad** |
|-------------------------------|----------------------------------------------------------------------------|-------------|------------------|
| **Header param**              |                                                                            |             |                  |
| **Path param**                |                                                                            |             |                  |
| **Query param**               |                                                                            |             |                  |
| accountIdentification     | Número de cuenta del cliente.       | integer     | [1..1]            |
| **Body**                                                             | Cuerpo del mensaje de solicitud                                            | object      | [1..1]           |
| **CaptureCustomerBasicData**                                             | Objeto con los detalles de contacto del cliente.                       | object    | [1..1]           |
| **CaptureCustomerBasicData.Contact**                                     | Objeto que almacena información de contacto relacionada al cliente.                  | object    | [1..1]           |
| CaptureCustomerBasicData.Contact.EmailAddress | Dirección de correo electrónico.                                  | string   | [1..1]           |
| CaptureCustomerBasicData.Contact.PhoneNumber | Colección de información que identifica un número de teléfono, según lo definido por los servicios de telecomunicaciones.                               | string   | [1..1]           |

## API Response

| **Nombre del Campo**                                                     | **Descripción**                                                                  | **Tipo**   | **Cardinalidad**  |
|--------------------------------------------------------------------------|----------------------------------------------------------------------------------|:----------:|:-----------------:|
| **Header param**                                                         |                                                                                  |            |                   |
| **HTTP Code**                                                            | Código HTTP de respuesta                                                         | integer    | [1..1]            |
| **HTTP Status**                                                          | Mensaje HTTP de respuesta                                                        | string     | [1..1]            |
| **Body Successful**                                                      | Objeto que almacena el mensaje se solicitud                                                    | object     | [1..1]            |
| **CaptureCustomerBasicDataResponse**                                             | Objeto con los detalles de contacto del cliente.                       | object    | [1..1]           |
| **CaptureCustomerBasicDataResponse.Account**                                     | Objeto que administra la información de las cuentas.                  | object    | [1..1]           |
| CaptureCustomerBasicDataResponse.Account.AccountIdentification | Número de cuenta del cliente. | string   | [1..1]           |

## API Response Error

| **Body Error**               | **Descripción**                                    | **Tipo**    | **Cardinalidad** |
|------------------------------|----------------------------------------------------|:-----------:|:----------------:|
| **error**                    | Objeto que contiene la información del error       | array       | [0..n]           |
| error[*].status_code         | Código de error                                    | string      | [1..1]           |
| error[*].message             | mensaje de error                                   | string      | [1..1]           |
