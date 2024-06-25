# API Customer Management Onboarding - Documentación

## Descripción General
**Función:** Valida por número de DNI si el cliente está registrado en el corebank.


| **API SPECIFICATION** |                                                                           |
|-----------------------|---------------------------------------------------------------------------|
| **API Name**          | customer-management-onboarding-b                                       |
| **Version**           | v1                                                                            |
| **Method**            | GET                                                                          |
| **Base Path**         | /customer-management-onboarding-b/v1                                     |
| **Path**              | /customer-validation/retrieve                                                |
| **URI**               | GET /customer-management-onboarding-b/v1/customer-validation/retrieve  |


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
| **Behavior Qualifier** | customer-validation                |
| **Action Term**        | retrieve                          |

## API Request

| **Nombre del Campo  *         | ** Descripción **                                                          | **Tipo**    | **Cardinalidad** |
|-------------------------------|----------------------------------------------------------------------------|-------------|------------------|
| **Header param**              |                                                                            |             |                  |
| messageIdentificationCustomerValidationRetrieve         | Una cadena que representa la traza de la petición de validación del cliente.   | string      | [1..1]           |
| securityToken         | LLave secreta para consumir los servicios sin JWT.  | string      | [1..1]           |
| **Path param**                |                                                                            |             |                  |
| **Query param**               |                                                                            |             |                  |
| typeOfIdentification           | Determina el ID del tipo de documento.                        | integer      | [1..1]           |
| identityCardNumber         | Número asignado por una autoridad nacional a una tarjeta de identidad.   | string      | [1..1]           |
| IMEI        | El IMEI del dispositivo, que es un identificador único de 15 dígitos para dispositivos móviles.   | string      | [1..1]           |




## API Response

| **Nombre del Campo**                                                     | **Descripción**                                                                  | **Tipo**   | **Cardinalidad**  |
|--------------------------------------------------------------------------|----------------------------------------------------------------------------------|:----------:|:-----------------:|
| **Header param**                                                         |                                                                                  |            |                   |
| **HTTP Code**                                                            | Código HTTP de respuesta                                                         | integer    | [1..1]            |
| **HTTP Status**                                                          | Mensaje HTTP de respuesta                                                        | string     | [1..1]            |
| **Body**               |                                                                  |             |                  |
| **EvaluateCustomerValidationResponse**          | Objeto que contiene los datos de respuesta de la validación del cliente registrado en el corebank.                       | object      | [1..1]           |
| **EvaluateCustomerValidationResponse.Account**          | Objeto que almacena información relacionada a la cuenta del cliente.                  | object      | [1..1]           |
| EvaluateCustomerValidationResponse.Account.AccountIdentification          | Número de cuenta del cliente.                    | integer      | [1..1]           |


## API Response Error

| **Body Error**       | **Descripción**                              | **Tipo** | **Cardinalidad** |
|----------------------|----------------------------------------------|:--------:|:----------------:|
| **status_code**      | Código de error                              | string   | [1..1]           |
| **status**           | Estado de la respuesta                       | string   | [1..1]           |
| **message**          | Mensaje de error                             | string   | [1..1]           |

