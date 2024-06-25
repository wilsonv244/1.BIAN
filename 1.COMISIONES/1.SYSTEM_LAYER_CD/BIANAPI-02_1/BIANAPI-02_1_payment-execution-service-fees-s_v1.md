# API Payment Execution Service Fees - Documentación

## Descripción General
**Función:** Registrar configuración de las comisiones


| **API SPECIFICATION** |                                                                           |
|-----------------------|---------------------------------------------------------------------------|
| **API Name**          | payment-execution-service-fees-s                                          |
| **Version**           | v1                                                                        |
| **Method**            | POST                                                                      |
| **Base Path**         | /payment-execution-service-fees-s/v1                                      |
| **Path**              | /internal-transfers/register                                              |
| **URI**               | POST /payment-execution-service-fees-s/v1/internal-transfers/register   |


| **BACKEND SERVICE**|                                         |
|--------------------|-----------------------------------------|
| **Protocol**       | JSON                                    |
| **URL**            | http://url-backend.com/basepath/path    |
| **Description**    | Breve descripción del backend           |



| **BIAN DEFINITIONS**       |                                    |
|----------------------------|------------------------------------|
| **Business Area**          | Operations and Execution           |
| **Business Domain**        | Payments                           |
| **Service Domain**         | Payment Execution                  |
| **Behavior Qualifier**     | service-fees                       |
| **Behavior Sub-Qualifier** | internal-transfers                 |
| **Action Term**            | register                           |


## API Request

| **Nombre del Campo**                                                 | **Descripción**                                                                | **Tipo**  | **Cardinalidad** |
|----------------------------------------------------------------------|--------------------------------------------------------------------------------|-----------|------------------|
| **Header param**                                                     | Parámetros de la cabecera                                                      |           |                  |
| **Path param**                                                       | Parametros de la URL                                                           |           |                  |
| **Query param**                                                      | Parámetros de la consulta                                                      |           |                  |
| **Body**                                                             | Cuerpo del mensaje de entrada                                                  | object    | [1..1]           |
| **RegisterInternalTransfers**                                        | Objeto que contiene los datos de solicitud                                     | object    | [1..1]           |
| **RegisterInternalTransfers.Commission**                             | Objeto que contiene la información relacionada a comisiones                    | object    | [1..1]           |
| RegisterInternalTransfers.Commission.Code                            | Código de la comisión                                                          | integer   | [1..1]           |
| RegisterInternalTransfers.Commission.Type                            | LimiteMonto / Operación / Mantenimiento                                        | integer   | [1..1]           |
| RegisterInternalTransfers.Commission.InterplazaTransactionIndicator  | Aplica Inter-Plaza/Plaza                                                       | boolean   | [1..1]           |
| RegisterInternalTransfers.Commission.VariableRateIndicator           | Indicador para determinar si aplica comisionFija / Variable                    | boolean   | [1..1]           |
| RegisterInternalTransfers.Commission.DailyFreeOperationCount         | Cantidad de operacion gratis por día                                           | integer   | [1..1]           |
| RegisterInternalTransfers.Commission.ActiveCommissionIndicator       | Vigencia de la configuración                                                   | boolean   | [1..1]           |
| **RegisterInternalTransfers.Commission.Amount**                      | Objeto que contiene los montos de las comisiones                               | object    | [1..1]           |
| RegisterInternalTransfers.Commission.Amount.Value                    | Monto de la comisión                                                           | number    | [1..1]           |
| RegisterInternalTransfers.Commission.Amount.MaximumValue             | Monto máximo                                                                   | number    | [1..1]           |
| RegisterInternalTransfers.Commission.Amount.MinimumValue             | Monto mínimo                                                                   | number    | [1..1]           |
| **RegisterInternalTransfers.Commission.VariableAmount**              | Objeto que contiene montos variables                                           | object    | [1..1]           |
| RegisterInternalTransfers.Commission.VariableAmount.MaximumValue     | Monto valor máximo                                                             | number    | [1..1]           |
| RegisterInternalTransfers.Commission.VariableAmount.MinimumValue     | Monto valor mínimo                                                             | number    | [1..1]           |
| **RegisterInternalTransfers.Transaction**                            | Objeto que contiene la información de las transacciones                        | object    | [1..1]           |
| RegisterInternalTransfers.Transaction.TransactionReasons             | Array de código de operaciones                                                 | number    | [1..1]           |
| **RegisterInternalTransfers.Transaction.Channel**                    | Objeto que contiene la información del canal                                   | object    | [1..1]           |
| RegisterInternalTransfers.Transaction.Channel.ChannelReference       | Código del canal de operación Ventanilla ó Aplicativo                          | integer   | [1..1]           |
| **RegisterInternalTransfers.Product**                                | Objeto que contiene la información de los productos                            | object    | [1..1]           |
| RegisterInternalTransfers.Product.AdditionalProductCode              | Código del producto de la operación                                            | integer   | [1..1]           |
| **RegisterInternalTransfers.Product.Module**                         | Objeto que contiene la información del módulo del producto                     | object    | [1..1]           |
| RegisterInternalTransfers.Product.Module.ModuleReference             | Código del módulo Ahorros / Créditos                                           | integer   | [1..1]           |
| **RegisterInternalTransfers.Product.Channel**                        | Objeto que contiene la información del canal                                   | object    | [1..1]           |
| RegisterInternalTransfers.Product.Channel.ChannelReference           | Código del canal de apertura Ventanilla ó Aplicativo                           | integer   | [1..1]           |



## API Response

| **Nombre del Campo**                                  | **Descripción**                                | **Tipo**  | **Cardinalidad** |
|-------------------------------------------------------|------------------------------------------------|-----------|------------------|
| **Header param**                                      |                                                |           |                  |
| **HTTP Code**                                         | Codigo HTTP de respuesta                       | integer   | [1..1]           |
| **HTTP Status**                                       | Mensaje HTTP de respuesta                      | string    | [1..1]           |
| **Body**                                              |                                                |           |                  |
| **RegisterInternalTransfersResponse**                 | Objeto que contiene los datos de respuesta     | object    | [1..1]           |
| Code                                                  | Código de respuesta operación                  | integer   | [1..1]           |
| Message                                               | Mensaje de la operación realizada              | string    | [1..1]           |


## API Response Error

| **Body Error**               | **Descripción**                                    | **Tipo**    | **Cardinalidad** |
|------------------------------|----------------------------------------------------|:-----------:|:----------------:|
| **error**                    | Objeto que contiene la información del error       | array       | [0..n]           |
| error[*].status_code         | Código de error                                    | string      | [1..1]           |
| error[*].message             | mensaje de error                                   | string      | [1..1]           |
