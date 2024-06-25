# API Party Reference Data Directory - Documentación

## Descripción General
**Función:** Maneja la gestión de datos básicos para perfiles de clientes, incluyendo nombre, dirección e información de contacto.


| **API SPECIFICATION** |                                                                           |
|-----------------------|---------------------------------------------------------------------------|
| **API Name**          | party-reference-data-directory-s                            |
| **Version**           | v1                                                                        |
| **Method**            | POST                                                                       |
| **Base Path**         | /party-reference-data-directory-s/v1                                      |
| **Path**              | /customer-basic-data/register                                             |
| **URI**               | POST /party-reference-data-directory-s/v1/customer-basic-data/register     |


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
| **Behavior Qualifier** | customer-basic-data                      |
| **Action Term**        | register                           |

## API Request

| **Nombre del Campo  *         | ** Descripción **                                                          | **Tipo**    | **Cardinalidad** |
|-------------------------------|----------------------------------------------------------------------------|-------------|------------------|
| **Header param**              |                                                                            |             |                  |
| **Path param**                |                                                                            |             |                  |
| **Query param**               |                                                                            |             |                  |
| **Body**                                                             | Cuerpo del mensaje de solicitud                                            | object      | [1..1]           |
| **RegisterCustomerBasicData**                                             | Objeto con los detalles de contacto del cliente.                       | object    | [1..1]           |
| **RegisterCustomerBasicData.PersonIdentification**                                     | Objeto que almacena información relacionada al cliente.                      | object    | [1..1]           |
| RegisterCustomerBasicData.PersonIdentification.CustomerIdentificationNumber | Número único asignado por el banco para identificar al cliente.                                              | integer   | [1..1]           |
| **RegisterCustomerBasicData.Person**                                     | Objeto que almacena información adicional relacionada al cliente.                      | object    | [1..1]           |
| RegisterCustomerBasicData.PersonName.Gender | Especifica el género de la persona.                               | integer   | [1..1]           |
| RegisterCustomerBasicData.PersonName.BirthDate | Fecha en la que nace una persona. | string   | [1..1]           |
| **RegisterCustomerBasicData.PersonName**                                     | Objeto que almacena información relacionada al cliente.                      | object    | [1..1]           |
| RegisterCustomerBasicData.PersonName.LastName | Determina el apellido paterno de la persona.                                    | string   | [1..1]           |
| RegisterCustomerBasicData.PersonName.MothersLastName | Determina el apellido materno de la persona.                                  | string   | [1..1]           |
| RegisterCustomerBasicData.PersonName.GivenName | Determina el primer nombre o nombres dados de la persona.                                | string   | [1..1]           |
| **RegisterCustomerBasicData.Contact**                                     | Objeto que almacena información de contacto relacionada al cliente.                  | object    | [1..1]           |
| RegisterCustomerBasicData.Contact.EmailAddress | Dirección de correo electrónico.                                  | string   | [1..1]           |
| RegisterCustomerBasicData.Contact.PhoneNumber | Colección de información que identifica un número de teléfono, según lo definido por los servicios de telecomunicaciones.                               | string   | [1..1]           |

## API Response

| **Nombre del Campo**                                                     | **Descripción**                                                                  | **Tipo**   | **Cardinalidad**  |
|--------------------------------------------------------------------------|----------------------------------------------------------------------------------|:----------:|:-----------------:|
| **Header param**                                                         |                                                                                  |            |                   |
| **HTTP Code**                                                            | Código HTTP de respuesta                                                         | integer    | [1..1]            |
| **HTTP Status**                                                          | Mensaje HTTP de respuesta                                                        | string     | [1..1]            |
| **Body Successful**                                                      | Cuerpo del mensaje de salida                                                     | object     | [1..1]            |
| **RetrieveCustomerBasicDataResponse**   | Objeto que almacena el mensaje se solicitud. | object     | [1..1]            |
| **RetrieveCustomerBasicDataResponse.Account** | Objeto que administra la información de las cuentas.                          | object     | [1..1]            |
| RetrieveCustomerBasicDataResponse.Account.AccountIdentification      | Número de cuenta del cliente.       | integer     | [1..1]            |

## API Response Error

| **Body Error**               | **Descripción**                                    | **Tipo**    | **Cardinalidad** |
|------------------------------|----------------------------------------------------|:-----------:|:----------------:|
| **error**                    | Objeto que contiene la información del error       | array       | [0..n]           |
| error[*].status_code         | Código de error                                    | string      | [1..1]           |
| error[*].message             | mensaje de error                                   | string      | [1..1]           |
