# API Payment Execution Service Fees - Documentación

## Descripción General
**Función:**  Enviar Mensaje Correo


| **API SPECIFICATION** |                                                                              |
|-----------------------|------------------------------------------------------------------------------|
| **API Name**          | document-services-s                                                          |
| **Version**           | v1                                                                           |
| **Method**            | POST                                                                         |
| **Base Path**         | /document-services-s/v1                                                      |
| **Path**              | /customer-correspondence/Provide                                              |
| **URI**               | POST /document-services-s/v1/customer-correspondence/provide                  |


| **BACKEND SERVICE**|                                         |
|--------------------|-----------------------------------------|
| **Protocol**       | JSON                                    |
| **URL**            | http://url-backend.com/basepath/path    |
| **Description**    | Breve descripción del backend           |



| **BIAN DEFINITIONS**   |                                      |
|------------------------|--------------------------------------|
| **Business Area**      | Business Support                     |
| **Business Domain**    | Document Management and Archive      |
| **Service Domain**     | Document Services                    |
| **Behavior Qualifier** | customer-correspondence               |
| **Action Term**        | provide                              |


## API Request

| **Nombre del Campo**                                                       | **Descripción**                                                                | **Tipo**  | **Cardinalidad** |
|----------------------------------------------------------------------------|--------------------------------------------------------------------------------|-----------|------------------|
| **Header param**                                                           | Parámetros de la cabecera                                                      |           |                  |
| **Path param**                                                             | Parametros de la URL                                                           |           |                  |
| **Query param**                                                            | Parámetros de la consulta                                                      |           |                  |
| **Body**                                                                   | Cuerpo del mensaje de entrada                                                  | object    | [1..1]           |
| **ProvideCustomerCorrespondence**                                           | Objeto que contiene los datos de solicitud                                     | object    | [1..1]           |
| **ProvideCustomerCorrespondence.Correspondence**                            | Objeto que representa el servicio de correspondencia utilizado para la renderización y transmisión de documentos a través de diferentes canales de comunicación. | object | [1..1] |
| ProvideCustomerCorrespondence.Correspondence.EmailAddresses             | Lista de correos electrónicos de los destinatarios a los que se enviará la correspondencia. | array | [1..n] |
| **ProvideCustomerCorrespondence.Correspondence.Document**                   | Objeto que contiene datos del documento                                        | object    | [1..1]           |
| ProvideCustomerCorrespondence.Correspondence.Document.DocumentSubject   | Asunto del documento                                                           | string    | [1..1]           |
| ProvideCustomerCorrespondence.Correspondence.Document.DocumentDescription | Contenido del documento                                                        | string    | [1..1]           |
| ProvideCustomerCorrespondence.Correspondence.Document.DocumentIdentification | Identificador de plantilla                                                     | integer   | [1..1]           |
| **ProvideCustomerCorrespondence.Correspondence.Attachments[n]**                | Lista de archivos adjuntos                                                     | array     | [0..n]           |
| ProvideCustomerCorrespondence.Correspondence.Attachments[n].FileName    | Título del adjunto                                                             | string    | [1..1]           |
| ProvideCustomerCorrespondence.Correspondence.Attachments[n].Format      | Tipo de documento (PDF, XML, XSLT)                                             | string    | [1..1]           |
| ProvideCustomerCorrespondence.Correspondence.Attachments[n].FileURL        | URL del archivo adjunto                                                        | string    | [1..1]           |

## API Response

| **Nombre del Campo**                                                                                  | **Descripción**                                                                                  | **Tipo**  | **Cardinalidad** |
|-------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|-----------|------------------|
| **Header param**                                                                                      |                                                                                                  |           |                  |
| **HTTP Code**                                                                                         | Codigo HTTP de respuesta                                                                         | integer   | [1..1]           |
| **HTTP Status**                                                                                       | Mensaje HTTP de respuesta                                                                        | string    | [1..1]           |
| **Body**                                                                                              |                                                                                                  |           |                  |
| **ProvideCustomerCorrespondenceResponse**                                                              | Objeto que contiene los datos de respuesta                                                       | object    | [1..1]           |
| **ProvideCustomerCorrespondenceResponse.Transaction**                         | Objeto que contiene los datos de respuesta                                                       | object    | [1..1]           |
| ProvideCustomerCorrespondenceResponse.Transaction.TransactionIdentification   | Un identificador que permite hacer referencia de forma única a una instancia de una transacción. | string    | [1..1]           |


## API Response Error

| **Body Error**               | **Descripción**                                    | **Tipo**    | **Cardinalidad** |
|------------------------------|----------------------------------------------------|:-----------:|:----------------:|
| **error**                    | Objeto que contiene la información del error       | array       | [0..n]           |
| error[*].status_code         | Código de error                                    | string      | [1..1]           |
| error[*].message             | mensaje de error                                   | string      | [1..1]           |
