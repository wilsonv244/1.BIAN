# API Payment Initiation - Documentación

## Descripción General
**Función:** Consulta Transferencia por recurso, información de cuenta Interbancaria CCI o número de teléfono


| **API SPECIFICATION** |                                                                   |
|-----------------------|-------------------------------------------------------------------|
| **API Name**      	| payment-initiation-s                                              |
| **Version**       	| v1                                                                |
| **Method**        	| GET                                                               |
| **Base Path**     	| /payment-initiation-s/v1                                          |
| **Path**          	| /external-transfers/retrieve                                      |
| **URI**           	| GET /payment-initiation-s/v1/external-transfers/retrieve          |


| **BACKEND SERVICE**|                                         |
|--------------------|-----------------------------------------|
| **Protocol**       | JSON                                    |
| **URL**            | http://url-backend.com/basepath/path    |
| **Description**    | Breve descripción del backend           |


| **BIAN DEFINITIONS**   |                                    |
|------------------------|------------------------------------|
| **Business Area**      | Operations and Execution           |
| **Business Domain**    | Payments                           |
| **Service Domain**     | Payment Initiation                 |
| **Behavior Qualifier** | external-transfers                 |
| **Action Term**        | retrieve                           |

## API Request

| **Nombre del Campo**            | **Descripción**                                                 | **Tipo**   | **Cardinalidad** |
|---------------------------------|-----------------------------------------------------------------|------------|------------------|
| **Header param**                | Parámetros de la cabecera                                       |            |                  |
| **Path param**                  | Parametros de la URL                                            |            |                  |
| **Query param**                 | Parámetros de la consulta                                       |            |                  |
| ChannelReference                | Código del canal solicitante(ventanilla/app cliente)            | integer    | [1..1]           |
| ResourceIdentification          | Código del tipo de recurso CCI o Interoperabilidad Telefónica.  | integer    | [1..1]           |
| ResourceReference               | Número del Teléfono o CCI                                       | string     | [1..1]           |
| OriginAccountIdentification     | Número de cuenta del cliente originante                         | string     | [1..1]           |
| UserReference                   | Código de usuario que ejecuta la transacción                    | integer    | [1..1]           |
| CustomerIdentification          | Código del cliente                                              | integer    | [1..1]           |
| TransactionDate                 | Fecha y hora que realiza la consulta                            | string     | [1..1]           |


## API Response

| **Nombre del Campo**                                                                               | **Descripción**                                                                         | **Tipo**   | **Cardinalidad** |
|----------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|------------|------------------|
| **Header param**                                                                                   |                                                                                         |            |                  |
| **HTTP Code**                                                                                      | Codigo HTTP de respuesta                                                                | integer    | [1..1]           |
| **HTTP Status**                                                                                    | Mensaje HTTP de respuesta                                                               | string     | [1..1]           |
| **MessageIdentification**                                                                          | Numero de identificación de la transación                                               | string     | [1..1]           |
| **Body Successful**                                                                                | Cuerpo del mensaje de entrada                                                           | object     |                  |
| **RetrieveExternalTransfersResponse**                                                              | Objeto que representa a la consulta                                                     | object     | [1..1]           |
| **RetrieveExternalTransfersResponse.Creditor**                                                     | Objeto que representa al creditor quien recibe el dinero                                | object     | [1..1]           |
| **RetrieveExternalTransfersResponse.Creditor.PartyIdentification**                                 | Objeto que almacena información relacionada al creditor                                 | object     | [1..1]           |
| RetrieveExternalTransfersResponse.Creditor.PartyIdentification.IdentificationNumber                | Número de cuenta receptor                                                               | integer    | [1..1]           |
| RetrieveExternalTransfersResponse.Creditor.PartyIdentification.Name                                | Nombre del receptor                                                                     | string     | [1..1]           |
| **RetrieveExternalTransfersResponse.Creditor.Account**                                             | Objeto que almacena información relacionada a las partes de una transacción financiera  | object     | [1..1]           |
| RetrieveExternalTransfersResponse.Creditor.Account.CCI                                             | Número de cuenta Interbancaria                                                          | string     | [1..1]           |
| **RetrieveExternalTransfersResponse.CreditorAgent**                                                | Objeto que representa a la entidad financiera que actúa en nombre del creditor          | object     | [1..1]           |
| **RetrieveExternalTransfersResponse.CreditorAgent.FinancialInstitutionIdentification**             | Objeto que representa a la información de la entidad financiera del creditor            | object     | [1..1]           |
| RetrieveExternalTransfersResponse.CreditorAgent.FinancialInstitutionIdentification.Identification  | Código del banco                                                                        | integer    | [1..1]           |
| RetrieveExternalTransfersResponse.CreditorAgent.FinancialInstitutionIdentification.Name            | Nombre del banco                                                                        | string     | [1..1]           |
| **RetrieveExternalTransfersResponse.Debtor**                                                       | Objeto que representa al deudor quien recibe el dinero                                  | object     | [1..1]           |
| **RetrieveExternalTransfersResponse.Debtor.PartyIdentification**                                   | Objeto que almacena información relacionada al deudor                                   | object     | [1..1]           |
| RetrieveExternalTransfersResponse.Debtor.PartyIdentification.IdentificationNumber                  | Código del cliente                                                                      | integer    | [1..1]           |
| **RetrieveExternalTransfersResponse.Debtor.Account**                                               | Objeto que almacena información de las cuentas a nombre de un deudor                    | object     | [1..1]           |
| RetrieveExternalTransfersResponse.Debtor.Account.Identification                                    | Código de la cuenta                                                                     | integer    | [1..1]           |


## API Response Error

| **Body Error**               | **Descripción**                                    | **Tipo**    | **Cardinalidad** |
|------------------------------|----------------------------------------------------|:-----------:|:----------------:|
| **error**                    | Objeto que contiene la información del error       | array       | [0..n]           |
| error[*].status_code         | Código de error                                    | string      | [1..1]           |
| error[*].message             | mensaje de error                                   | string      | [1..1]           |
