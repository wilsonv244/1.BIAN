# API Party Reference Data Directory - Documentación

## Descripción General
**Función:** Obtener catálogo de campos que abarca diferentes tipos de datos.


| **API SPECIFICATION** |                                                                           |
|-----------------------|---------------------------------------------------------------------------|
| **API Name**          | party-reference-data-directory-s                                          |
| **Version**           | v1                                                                        |
| **Method**            | GET                                                                       |
| **Base Path**         | /party-reference-data-directory-s/v1                                      |
| **Path**              | /field-management/retrieve                                     |
| **URI**               | GET /party-reference-data-directory-s/v1/field-management/retrieve|


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
| **Behavior Qualifier** | field-management          |
| **Action Term**        | retrieve                         |

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
| **RetrieveFieldManagementResponse**                                                        | Objeto que almacena el mensaje de solicitud.                                | object   | 1..1         |
| **RetrieveFieldManagementResponse.PersonIdentification[n]**                                | Objeto que almacena información relacionada con la identificación del cliente. | array    | 0..*         |
| RetrieveFieldManagementResponse.PersonIdentification[n].TypeOfIdentification               | Determina el ID del tipo de documento.                                       | integer  | 1..1         |
| RetrieveFieldManagementResponse.PersonIdentification[n].IdentificationShortName            | Nombre corto del tipo de identificación, como "DNI".                         | string   | 1..1         |
| RetrieveFieldManagementResponse.PersonIdentification[n].IdentificationType                 | El tipo de identificación, como "Documento Nacional de Identidad".           | string   | 1..1         |
| **RetrieveFieldManagementResponse.PersonIdentification[n].ValidationRules[n]**             | Reglas de validación para el documento de identificación.                    | object   | 1..1         |
| RetrieveFieldManagementResponse.PersonIdentification[n].ValidationRules[n].Pattern         | Patrón de validación del documento, por ejemplo, una expresión regular.      | string   | 1..1         |
| RetrieveFieldManagementResponse.PersonIdentification[n].ValidationRules[n].Description     | Descripción de las reglas de validación.                                     | string   | 1..1         |
| **RetrieveFieldManagementResponse.Agreements[n]**                                          | Objeto que almacena un acuerdo común, formal o informal, entre dos o más partes. | array    | 0..*         |
| RetrieveFieldManagementResponse.Agreements[n].AgreementIdentification                      | El identificador del acuerdo, como el Número de Acuerdo, Número de Contrato, Número de Registro de Contrato, etc. | integer  | 1..1         |
| RetrieveFieldManagementResponse.Agreements[n].AgreementSubjectMatter                       | El asunto del acuerdo, como "Términos y condiciones".                        | string   | 1..1         |
| RetrieveFieldManagementResponse.Agreements[n].AgreementDescription                         | Una descripción del acuerdo, como un texto plano de términos y condiciones.  | string   | 1..1         |
| RetrieveFieldManagementResponse.Agreements[n].AgreementURLAddress                          | La URL donde se puede encontrar el acuerdo.                                  | string   | 1..1         |
| **RetrieveFieldManagementResponse.ContactPoints[n]**                                       | Objeto que almacena información de contacto relacionada al cliente.          | array    | 0..*         |
| RetrieveFieldManagementResponse.ContactPoints[n].ContactIdentification                     | Identificador único para el contacto.                                        | integer  | 1..1         |
| RetrieveFieldManagementResponse.ContactPoints[n].ContactType                               | Tipo de contacto, como "WhatsApp", "Teléfono", "Email", etc.                 | string   | 1..1         |
| RetrieveFieldManagementResponse.ContactPoints[n].ContactValue                              | Valor del contacto, como el número de teléfono o dirección de correo electrónico. | string   | 1..1         |
| **RetrieveFieldManagementResponse.Branches[n]**                                            | Objeto que almacena información sobre la ubicación de las sucursales.        | object   | 0..*         |
| RetrieveFieldManagementResponse.Branches[n].BranchIdentification                           | Identificador único de la sucursal.                                          | integer  | 1..1         |
| RetrieveFieldManagementResponse.Branches[n].BranchName                                     | Nombre de la sucursal.                                                      | string   | 1..1         |
| RetrieveFieldManagementResponse.Branches[n].BranchAddress                                  | Dirección de la sucursal.                                                   | string   | 1..1         |
| RetrieveFieldManagementResponse.Branches[n].LatitudeAddress                                | Latitud de la ubicación de la sucursal.                                      | string   | 1..1         |
| RetrieveFieldManagementResponse.Branches[n].LongitudeAddress                               | Longitud de la ubicación de la sucursal.                                     | string   | 1..1         |

## API Response Error

| **Body Error**               | **Descripción**                                    | **Tipo**    | **Cardinalidad** |
|------------------------------|----------------------------------------------------|:-----------:|:----------------:|
| **error**                    | Objeto que contiene la información del error       | array       | [0..n]           |
| error[*].status_code         | Código de error                                    | string      | [1..1]           |
| error[*].message             | mensaje de error                                   | string      | [1..1]           |
