# API Payment to Information Association - Documentación

## Descripción General
**Función:** Actualizar comision - Transferencias internas para cuenta digital


| API SPECIFICATION |                                                                           |
|-------------------|---------------------------------------------------------------------------|
| **API Name**      | payment-to-information-association-b                                                    |
| **Version**       | v1                                                                        |
| **Method**        | PATCH                                                                      |
| **Base Path**     | /payment-to-information-association-b/v1                                    |
| ** Path**         | /internal-transfers/update                             |
| **URI**           | PATCH /payment-to-information-association-b/v1/internal-transfers/update       |


| BACKEND SERVICE|                                         |
|----------------|-----------------------------------------|
| **Protocol**   | JSON                                    |
| **URL**        | http://url-backend.com/basepath/path    |
| **Description**| Breve descripción del backend           |


| BIAN DEFINITIONS       |                                    |
|------------------------|------------------------------------|
| **Business Area**      | Operations and Execution           |
| **Business Domain**    | Payments                           |
| **Service Domain**     | Payment Execution                  |
| **Behavior Qualifier** | internal-transfers    |
| **Action Term**        | update                             |


## API Request

| **Nombre del Campo**                                               | **Descripción**                                                                | **Tipo**  | **Cardinalidad** |
|--------------------------------------------------------------------|--------------------------------------------------------------------------------|-----------|------------------|
| **Header param**                                                   | Parámetros de la cabecera                                                      |           |                  |
| **Path param**                                                     | Parametros de la URL                                                           |           |                  |
| **Query param**                                                    | Parámetros de la consulta                                                      |           |                  |
| CommissionCode                                                     | Código de la comisión                                                          | integer   | [1..1]           |
| **Body**                                                           | Cuerpo del mensaje de entrada                                                  | object    | [1..1]           |
| **UpdateInternalTransfers**                                        | Objeto que contiene los datos de solicitud                                     | object    | [1..1]           |
| **UpdateInternalTransfers.Commission**                             | Objeto que contiene la información relacionada a comisiones                    | object    | [1..1]           |
| UpdateInternalTransfers.Commission.Type                            | LimiteMonto / Operación / Mantenimiento                                        | integer   | [1..1]           |
| UpdateInternalTransfers.Commission.InterplazaTransactionIndicator  | Aplica Inter-Plaza/Plaza                                                       | boolean   | [1..1]           |
| UpdateInternalTransfers.Commission.VariableRateIndicator           | Indicador para determinar si aplica comisionFija / Variable                    | boolean   | [1..1]           |
| UpdateInternalTransfers.Commission.DailyFreeOperationCount         | Cantidad de operacion gratis por día                                           | integer   | [1..1]           |
| UpdateInternalTransfers.Commission.ActiveCommissionIndicator       | Vigencia de la configuración                                                   | boolean   | [1..1]           |
| **UpdateInternalTransfers.Commission.Amount**                      | Objeto que contiene los montos de las comisiones                               | object    | [1..1]           |
| UpdateInternalTransfers.Commission.Amount.Value                    | Monto de la comisión                                                           | number    | [1..1]           |
| UpdateInternalTransfers.Commission.Amount.MaximumValue             | Monto máximo                                                                   | number    | [1..1]           |
| UpdateInternalTransfers.Commission.Amount.MinimumValue             | Monto mínimo                                                                   | number    | [1..1]           |
| **UpdateInternalTransfers.Commission.VariableAmount**              | Objeto que contiene montos variables                                           | object    | [1..1]           |
| UpdateInternalTransfers.Commission.VariableAmount.MaximumValue     | Monto valor máximo                                                             | number    | [1..1]           |
| UpdateInternalTransfers.Commission.VariableAmount.MinimumValue     | Monto valor mínimo                                                             | number    | [1..1]           |
| **UpdateInternalTransfers.Transaction**                            | Objeto que contiene la información de las transacciones                        | object    | [1..1]           |
| UpdateInternalTransfers.Transaction.TransactionReasons             | Array de código de operaciones                                                 | number    | [1..1]           |
| **UpdateInternalTransfers.Transaction.Channel**                    | Objeto que contiene la información del canal                                   | object    | [1..1]           |
| UpdateInternalTransfers.Transaction.Channel.ChannelReference       | Código del canal de operación Ventanilla ó Aplicativo                          | integer   | [1..1]           |
| **UpdateInternalTransfers.Product**                                | Objeto que contiene la información de los productos                            | object    | [1..1]           |
| UpdateInternalTransfers.Product.AdditionalProductCode              | Código del producto de la operación                                            | integer   | [1..1]           |
| **UpdateInternalTransfers.Product.Module**                         | Objeto que contiene la información del módulo del producto                     | object    | [1..1]           |
| UpdateInternalTransfers.Product.Module.ModuleReference             | Código del módulo Ahorros / Créditos                                           | integer   | [1..1]           |
| **UpdateInternalTransfers.Product.Channel**                        | Objeto que contiene la información del canal                                   | object    | [1..1]           |
| UpdateInternalTransfers.Product.Channel.ChannelReference           | Código del canal de apertura Ventanilla ó Aplicativo                           | integer   | [1..1]           |



## API Response

| **Nombre del Campo**                                  | **Descripción**                                | **Tipo**  | **Cardinalidad** |
|-------------------------------------------------------|------------------------------------------------|-----------|------------------|
| **Header param**                                      |                                                |           |                  |
| **HTTP Code**                                         | Codigo HTTP de respuesta                       | integer   | [1..1]           |
| **HTTP Status**                                       | Mensaje HTTP de respuesta                      | string    | [1..1]           |
| **Body**                                              |                                                |           |                  |
| **UpdateInternalTransfersResponse**                   | Objeto que contiene los datos de respuesta     | object    | [1..1]           |
| Code                                                  | Código de respuesta operación                  | integer   | [1..1]           |
| Message                                               | Mensaje de la operación realizada              | string    | [1..1]           |


## API Response Error

| **Body Error**               | **Descripción**                                    | **Tipo**    | **Cardinalidad** |
|------------------------------|----------------------------------------------------|:-----------:|:----------------:|
| **error**                    | Objeto que contiene la información del error       | array       | [0..n]           |
| error[*].status_code         | Código de error                                    | string      | [1..1]           |
| error[*].message             | mensaje de error                                   | string      | [1..1]           |
