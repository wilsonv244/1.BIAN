# API Payment Execution Service Fees - Documentación

## Descripción General
**Función:** Exponer la api de cálculo de comisiones para transferencias internas para cuenta digital


| **API SPECIFICATION** |                                                                           |
|-----------------------|---------------------------------------------------------------------------|
| **API Name**          | payment-to-information-association-b                                      |
| **Version**           | v1                                                                        |
| **Method**            | POST                                                                      |
| **Base Path**         | /payment-to-information-association-b/v1                                  |
| **Path**              | /internal-transfers/execute                                               |
| **URI**               | POST /payment-to-information-association-b/v1/internal-transfers/execute  |


| **BACKEND SERVICE**|                                         |
|--------------------|-----------------------------------------|
| **Protocol**       | JSON                                    |
| **URL**            | http://url-backend.com/basepath/path    |
| **Description**    | Breve descripción del backend           |



| **BIAN DEFINITIONS**   |                                    |
|------------------------|------------------------------------|
| **Business Area**      | Operations and Execution           |
| **Business Domain**    | Payments                           |
| **Service Domain**     | Payment Execution                  |
| **Behavior Qualifier** | internal-transfers                 |
| **Action Term**        | execute                            |

## API Request

| **Nombre del Campo**                                                 | **Descripción**                                               | **Tipo**    | **Cardinalidad** |
|----------------------------------------------------------------------|---------------------------------------------------------------|:-----------:|:----------------:|
| **Header param**                                                     | Parámetros de la cabecera                                     |             |                  |
| **Path param**                                                       | Parametros de la URL                                          |             |                  |
| **Query param**                                                      | Parámetros de la consulta                                     |             |                  |
| **Body**                                                             | Cuerpo del mensaje de solictud                                | object      | [1..1]           |
| **ExecuteInternalTransfer**                                          | Objeto que almacena el mensaje de solictud                    | object      | [1..1]           |
| **ExecuteInternalTransfer.Account**                                  | Objeto que administra la información de las cuentas           | object      | [1..1]           |
| ExecuteInternalTransfer.Account.Identification                       | Código de la cuenta                                           | integer     | [1..1]           |
| **ExecuteInternalTransfer.Product**                                  | Objeto que almacena la entidad producto                       | object      | [1..1]           |
| ExecuteInternalTransfer.Product.ProductIdentification                | Objeto que almacena la identificación producto                | object      | [1..1]           |
| ExecuteInternalTransfer.Product.ProductIdentification.Identifier     | Código del producto de la operación                           | integer     | [1..1]           |
| **ExecuteInternalTransfer.Transaction**                              | Objeto que contiene la información de la transacción          | object      | [1..1]           |
| ExecuteInternalTransfer.Transaction.TransactionReason                | Concepto de la operación                                      | integer     | [1..1]           |
| **ExecuteInternalTransfer.Transaction.Amount**                       | Objeto que almacena el detalle de los montos                  | object      | [1..1]           |
| ExecuteInternalTransfer.Transaction.Amount.Value                     | Valor de la operación interbancaria                           | number      | [1..1]           |
| **ExecuteInternalTransfer.Location**                                 | Objeto que contiene los datos de locación                     | object      | [1..1]           |
| ExecuteInternalTransfer.Location.LocationCode                        | Código de la agencia de la entidad                            | integer     | [1..1]           |
| **ExecuteInternalTransfer.Channel**                                  | Objeto que contiene los datos del canal                       | object      | [1..1]           |
| ExecuteInternalTransfer.Channel.ChannelReference                     | Código del canal de operacion (CoreBank, App, etc)            | integer     | [1..1]           |


## API Response

| **Nombre del Campo**                                             | **Descripción**                                      | **Tipo**   | **Cardinalidad**  |
|------------------------------------------------------------------|------------------------------------------------------|:----------:|:-----------------:|
| **Header param**                                                 |                                                      |            |                   |
| **HTTP Code**                                                    | Código HTTP de respuesta                             | integer    | [1..1]            |
| **HTTP Status**                                                  | Mensaje HTTP de respuesta                            | string     | [1..1]            |
| **Body Successful**                                              | Cuerpo del mensaje de salida                         | object     | [1..1]            |
| **ExecuteInternalTransferResponse**                              | Objeto que almacena el mensaje de respuesta          | object     | [1..1]            |
| ExecuteInternalTransferResponse.Code                             | Código de respuesta operación                        | integer    | [1..1]            |
| **ExecuteInternalTransferResponse.Commission**                   | Objeto que contiene la información de las comisiones | object     | [1..1]            |
| ExecuteInternalTransferResponse.Commission.Code                  | Código de concepto de la comisión                    | integer    | [1..1]            |
| ExecuteInternalTransferResponse.Commission.AdditionalInformation | Nombre de la comisión                                | string     | [1..1]            |
| **ExecuteInternalTransferResponse.Commission.Amount**            | Objeto que almacena el detalle de los montos         | object     | [1..1]            |
| ExecuteInternalTransferResponse.Commission.Amount.Value          | Monto asignado a la respuesta                        | number     | [1..1]            |

## API Response Error

| **Body Error**               | **Descripción**                                    | **Tipo**    | **Cardinalidad** |
|------------------------------|----------------------------------------------------|:-----------:|:----------------:|
| **error**                    | Objeto que contiene la información del error       | array       | [0..n]           |
| error[*].status_code         | Código de error                                    | string      | [1..1]           |
| error[*].message             | mensaje de error                                   | string      | [1..1]           |
