# API Party Reference Data Directory - Documentación

## Descripción General
**Función:** Obtiene datos del cliente registrado en el corebank.


| **API SPECIFICATION** |                                                                           |
|-----------------------|---------------------------------------------------------------------------|
| **API Name**          | party-reference-data-directory-x                                      |
| **Version**           | v1                                                                            |
| **Method**            | GET                                                                          |
| **Base Path**         | /party-reference-data-directory-x/v1                                     |
| **Path**              | /customer-basic-data/retrieve                                                |
| **URI**               | GET /party-reference-data-directory-x/v1/customer-basic-data/retrieve        |


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
| **Behavior Qualifier** | customer-basic-data                |
| **Action Term**        | retrieve                          |

## API Request

| **Nombre del Campo  *         | ** Descripción **                                                          | **Tipo**    | **Cardinalidad** |
|-------------------------------|----------------------------------------------------------------------------|-------------|------------------|
| **Header param**              |                                                                            |             |                  |
| **Path param**                |                                                                            |             |                  |
| **Query param**               |                                                                            |             |                  |
| typeOfIdentification          | Determina el ID del tipo de documento.                               | integer      | [1..1]           |
| identityCardNumber         | Número asignado por una autoridad nacional a una tarjeta de identidad.   | string      | [1..1]           |




## API Response

| **Nombre del Campo**                                                     | **Descripción**                                                                  | **Tipo**   | **Cardinalidad**  |
|--------------------------------------------------------------------------|----------------------------------------------------------------------------------|:----------:|:-----------------:|
| **Header param**                                                         |                                                                                  |            |                   |
| **HTTP Code**                                                            | Código HTTP de respuesta                                                         | integer    | [1..1]            |
| **HTTP Status**                                                          | Mensaje HTTP de respuesta                                                        | string     | [1..1]            |
| **Body**                                                             | Cuerpo del mensaje de solicitud                                            | object      | [1..1]           |
| **RetrieveCustomerBasicDataResponse**                                             | Objeto con los detalles de contacto del cliente.                       | object    | [1..1]           |
| **RetrieveCustomerBasicDataResponse.PersonIdentification**                                     | Objeto que almacena información relacionada al cliente.                      | object    | [1..1]           |
| RetrieveCustomerBasicDataResponse.PersonIdentification.CustomerIdentificationNumber | Número único asignado por el banco para identificar al cliente.                                              | integer   | [1..1]           |
| RetrieveCustomerBasicDataResponse.PersonIdentification.TypeOfIdentification           | Determina el ID del tipo de documento.                      | integer      | [1..1]           |
| RetrieveCustomerBasicDataResponse.PersonIdentification.IdentityCardNumber         | Número asignado por una autoridad nacional a una tarjeta de identidad.   | string      | [1..1]           |
| **RetrieveCustomerBasicDataResponse.Person**                                     | Objeto que almacena información relacionada al cliente.                      | object    | [1..1]           |
| RetrieveCustomerBasicDataResponse.Person.Gender | Especifica el género de la persona.                                 | integer   | [1..1]           |
| RetrieveCustomerBasicDataResponse.Person.BirthDate | Fecha en la que nace una persona.                    | string   | [1..1]           |
| **RetrieveCustomerBasicDataResponse.PersonName**                                     | Objeto que almacena información relacionada al cliente.                      | object    | [1..1]           |
| RetrieveCustomerBasicDataResponse.PersonName.LastName | Determina el apellido paterno de la persona.                                    | string   | [1..1]           |
| RetrieveCustomerBasicDataResponse.PersonName.MothersLastName | Determina el apellido materno de la persona.                                  | string   | [1..1]           |
| RetrieveCustomerBasicDataResponse.PersonName.GivenName | Determina el primer nombre o nombres dados de la persona.                                | string   | [1..1]           |
| **RetrieveCustomerBasicDataResponse.Contact**                                     | Objeto que almacena información de contacto relacionada al cliente.                  | object    | [1..1]           |
| RetrieveCustomerBasicDataResponse.Contact.EmailAddress | Dirección de correo electrónico.                                  | string   | [1..1]           |
| RetrieveCustomerBasicDataResponse.Contact.PhoneNumber | Colección de información que identifica un número de teléfono, según lo definido por los servicios de telecomunicaciones.                               | string   | [1..1]           |


## API Response Error

| **Body Error**       | **Descripción**                              | **Tipo** | **Cardinalidad** |
|----------------------|----------------------------------------------|:--------:|:----------------:|
| **status_code**      | Código de error                              | string   | [1..1]           |
| **status**           | Estado de la respuesta                       | string   | [1..1]           |
| **message**          | Mensaje de error                             | string   | [1..1]           |