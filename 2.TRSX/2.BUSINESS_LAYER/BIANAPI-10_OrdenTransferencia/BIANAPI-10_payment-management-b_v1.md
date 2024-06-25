# API Payment Management - Documentación

## Descripción General
**Función:** Exponer la generación de orden de transferencia interbancaria


| **API SPECIFICATION**   |                                                                   |
|-------------------------|-------------------------------------------------------------------|
| **API Name**            | payment-management-b                                              |
| **Version**             | v1                                                                |
| **Method**              | POST                                                              |
| **Base Path**           | /payment-management-b/v1									      |
| **Path**                | /external-transfers/create                                        |
| **Full URI**            | POST /payment-management-b/v1/external-transfers/create           |


| **BACKEND SERVICE**|                                         |
|--------------------|-----------------------------------------|
| **Protocol**       | JSON                                    |
| **URL**            | http://url-backend.com/basepath/path    |
| **Description**    | Breve descripción del backend           |


| **BIAN DEFINITIONS **      |                                  |
|----------------------------|----------------------------------|
| **Business Area**          | Operations and Execution         |
| **Business Domain**        | Payments                         |
| **Service Domain**         | Payment Order                    |
| **Behavior Qualifier**     | external-transfers               |
| **Behavior Sub-Qualifier** |                                  |
| **Action Term**            | create                           |


## API Request

| **Nombre del Campo**                                                    | **Descripción**                                                      | **Tipo**  | **Cardinalidad** |
|-------------------------------------------------------------------------|----------------------------------------------------------------------|-----------|------------------|
| **Header param**                                                        | Parámetros de la cabecera                                            |           |                  |
| channelIdentification                                                   | Identificador del canal 	                                         | string    | [1..1]           |
| messageIdentification											          | Identificador del mensaje                                            | string    | [1..1]           |
| **Path param**                                                          | Parametros de la URL                                                 |           |                  |
| **Query param**                                                         | Parámetros de la consulta                                            |           |                  |
| **Body**                                                                | Cuerpo del mensaje de entrada                                        | object    | [1..1]           |
| **CreateExternalTransfers**                                             | Objeto que representa la información del canal                       | object    | [1..1]           |
| **CreateExternalTransfers.Channel**                                     | Objeto que representa la información del canal                       | object    | [1..1]           |
| CreateExternalTransfers.Channel.ChannelReference                        | Código de canal                                                      | integer   | [1..1]           |
| **CreateExternalTransfers.Location**                                    | Objeto que representa la información de la locación                  | object    | [1..1]           |
| CreateExternalTransfers.Location.LocationCode                           | Código de agencia                                                    | integer   | [1..1]           |
| **CreateExternalTransfers.Transaction**                                 | Objeto que representa a la información de la transacción             | object    | [1..1]           |
| CreateExternalTransfers.Transaction.TransactionDate                     | Fecha Operación                                                      | string    | [1..1]           |
| CreateExternalTransfers.Transaction.UserId                              | Código del usuario                                                   | integer   | [1..1]           |
| CreateExternalTransfers.Transaction.MessageIdentification               | Número aleatorio perteneciente a la consulta                         | integer   | [1..1]           |
| CreateExternalTransfers.Transaction.TransactionReason                   | Código de motivo de operación por tipo de operación                  | integer   | [1..1]           |
| **CreateExternalTransfers.Document**                                    | Objeto que representa al documento de la operación                   | object    | [1..1]           |
| CreateExternalTransfers.Document.Type                                   | Tipo de documento                                                    | string    | [1..1]           |
| CreateExternalTransfers.Document.Identification                         | Número del documento                                                 | string    | [1..1]           |
| **CreateExternalTransfers.Amount**                                      | Objeto que representa a los montos de la operación                   | object    | [1..1]           |
| CreateExternalTransfers.Amount.Value                                    | Monto base de la operación                                           | number    | [1..1]           |
| CreateExternalTransfers.Amount.CurrencyCode                             | Código moneda                                                        | integer   | [1..1]           |
| CreateExternalTransfers.Amount.TotalValue                               | Monto final considerando todos los conceptos                         | number    | [1..1]           |
| **CreateExternalTransfers.Product**                                     | Objeto que representa al producto                                    | object    | [1..1]           |
| **CreateExternalTransfers.Product.ProductIdentification**               | Objeto que representa a la identificación del producto               | object    | [1..1]           |
| CreateExternalTransfers.Product.ProductIdentification.Identifier        | Código de producto                                                   | integer   | [1..1]           |
| **CreateExternalTransfers.Payment**                                     | Objeto que representa a los montos de la operación                   | object    | [1..1]           |
| CreateExternalTransfers.Payment.Type                                    | Código de la lista de los Tipos de Pago                              | integer   | [1..1]           |
| **CreateExternalTransfers.Commissions[n]**                              | Información de las comisiones                                        | array     | [1..n]           |
| **CreateExternalTransfers.Commissions[n].Commission**                   | Objeto que identifica la información de la comisión                  | object    | [1..1]           |
| CreateExternalTransfers.Commissions[n].Commission.AdditionalInformation | Nombre del concepto de la comisión                                   | string    | [1..1]           |
| CreateExternalTransfers.Commissions[n].Commission.Code                  | Codigo del concepto de la comisión                                   | integer   | [1..1]           |
| CreateExternalTransfers.Commissions[n].Commission.Amount.Value          | Monto de la comisión                                                 | number    | [1..1]           |
| **CreateExternalTransfers.Creditor**                                    | Objeto que representa al creditor quien recibe el dinero             | object    | [1..1]           |
| CreateExternalTransfers.Creditor.Account.Identification                 | Número de cuenta receptor                                            | string    | [1..1]           |
| CreateExternalTransfers.Creditor.PhoneAddress.PhoneNumber               | Número de telefono                                                   | string    | [1..1]           |
| **CreateExternalTransfers.Debtor**                                      | Objeto que representa al debtor quien envia el dinero                | object    | [1..1]           |
| CreateExternalTransfers.Debtor.Account.Identification                   | Número de cuenta del cliente originante                              | string    | [1..1]           |


## API Response

| **Nombre del Campo**                                                               | **Descripción**                                                                | **Tipo**  | **Cardinalidad** |
|------------------------------------------------------------------------------------|--------------------------------------------------------------------------------|-----------|------------------|
| **Header param**                                                                   |                                                                                |           |                  |
| **HTTP Code**                                                                      | Codigo HTTP de respuesta                                                       | integer   | [1..1]           |
| **HTTP Status**                                                                    | Mensaje HTTP de respuesta                                                      | string    | [1..1]           |
| **Body Successful**                                                                |Objeto que almacena el mensaje de solictud                                      | object    | [1..1]           |
| **CreateExternalTransfersResponse**                                                | Objeto que representa la información del canal                                 | object    | [1..1]           |
| **CreateExternalTransfersResponse.Channel**                                        | Objeto que representa la información del canal                                 | object    | [1..1]           |
| CreateExternalTransfersResponse.Channel.ChannelReference                           | Identificación del canal                                                       | integer   | [1..1]           |
| **CreateExternalTransfersResponse.Creditor**                                       | Objeto que representa al creditor quien recibe el dinero                       | object    | [1..1]           |
| **CreateExternalTransfersResponse.Creditor.PartyIdentification**                   | Objeto que almacena información relacionada al creditor                        | object    | [1..1]           |
| CreateExternalTransfersResponse.Creditor.PartyIdentification.IdentificationNumber  | Número del documento del receptor                                              | string    | [1..1]           |
| **CreateExternalTransfersResponse.Creditor.Account**                               | Objeto que representa a la entidad financiera que actúa en nombre del creditor | object    | [1..1]           |
| CreateExternalTransfersResponse.Creditor.Account.Identification                    | Número de cuenta receptor                                                      | string    | [1..1]           |


## API Response Error

| **Body Error**               | **Descripción**                                    | **Tipo**    | **Cardinalidad** |
|------------------------------|----------------------------------------------------|:-----------:|:----------------:|
| **error**                    | Objeto que contiene la información del error       | array       | [0..n]           |
| error[*].status_code         | Código de error                                    | string      | [1..1]           |
| error[*].message             | mensaje de error                                   | string      | [1..1]           |
