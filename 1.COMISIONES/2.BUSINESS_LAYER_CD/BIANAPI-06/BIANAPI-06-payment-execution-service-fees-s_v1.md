# API Payment to Information Association - Documentación

## Descripción General
**Función:** Exponer la funcionalidad de listar comisiones en transferencias internas para cuentas digitales.


| **API SPECIFICATION **|                                                                                        |
|-----------------------|---------------------------------------------------------------------------|
| **API Name**          | payment-to-information-association-b                                                     |
| **Version**           | v1                                                                                     |
| **Method**            | GET                                                                                    |
| **Base Path**         | /payment-to-information-association-b/v1                                                  |
| **Path**              | /internal-transfers/retrieve                                                           |
| **URI**               | GET /payment-to-information-association-b/v1/internal-transfers/retrieve                   |


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
| **Behavior Qualifier**     | internal-transfers                 |
| **Action Term**            | retrieve                           |


## API Request

| **Nombre del Campo  *         | ** Descripción **                                                          | **Tipo**    | **Cardinalidad** |
|-------------------------------|----------------------------------------------------------------------------|-------------|------------------|
| **Header param**              |                                                                            |             |                  |
| **Path param**                |                                                                            |             |                  |
| **Query param**               |                                                                            |             |                  |
| AdditionalProductCode         | Código del producto de la operación                                        | integer     | [1..1]           |
| ProductChannelReference       | Código del canal de apertura Ventanilla ó Aplicativo                       | integer     | [1..1]           |
| TransactionChannelReference   | Código del canal de operación Ventanilla ó Aplicativo                      | integer     | [1..1]           |
| ComissionType                 | Identificador del tipo de concepto de comisión Mantenimiento ó Interplaza  | integer     | [1..1]           |
| InterplazaIndicator           | Indicador Interplaza ó plaza                                               | boolean     | [1..1]           |


## API Response 

| **Nombre del Campo**                                                                                                       | **Descripción**                                              | **Tipo**  | **Cardinalidad** |
|----------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------|-----------|------------------|
| **Header param**                                                                                                           |                                                              |           |                  |
| HTTP Code                                                                                                                  | Código HTTP de respuesta                                     | integer   | [1..1]           |
| HTTP Status                                                                                                                | Mensaje HTTP de respuesta                                    | string    | [1..1]           |
| **Body Successful**                                                                                                        | Cuerpo del mensaje de respuesta                              | object    |                  |
| **RetrieveServiceFeesInternalTransfersResponse**                                                                           | Objeto que contiene la respuesta del cálculo de comisiones   | object    | [1..n]           |
| **RetrieveServiceFeesInternalTransfersResponse.Commisions[n]**                                                             | Lista de comisiones                                          | array     | [1..n]           |
| **RetrieveServiceFeesInternalTransfersResponse.Commisions[n].Commission**                                                  | Objeto que contiene las comisiones                           | object    | [0..1]           |
| RetrieveServiceFeesInternalTransfersResponse.Commisions[n].Commission.Code                                                 | Código de la comisión                                        | integer   | [1..1]           |
| **RetrieveServiceFeesInternalTransfersResponse.Commisions[n].Commission.Transactions[n]**                                  | Lista de las comisiones de concepto                          | array     | [1..n]           |
| RetrieveServiceFeesInternalTransfersResponse.Commisions[n].Commission.Transactions[n].Transaction.Code                     | Código de concepto de operación                              | integer   | [1..1]           |
| RetrieveServiceFeesInternalTransfersResponse.Commisions[n].Commission.Transactions[n].Transaction.AdditionalInformation    | Descripción del concepto de la operación                     | string    | [1..1]           |
| RetrieveServiceFeesInternalTransfersResponse.Commisions[n].Commission.ActiveCommissionIndicator                            | Indicador de Vigencia de la comisión                         | boolean   | [1..1]           |
| RetrieveServiceFeesInternalTransfersResponse.Commisions[n].Commission.DailyFreeOperationCount                              | Cantidad de operaciones libres por día                       | integer   | [0..1]           |
| RetrieveServiceFeesInternalTransfersResponse.Commisions[n].Commission.InterplazaTransactionIndicator                       | Indicador para determinar si es Interplaza ó plaza           | boolean   | [1..1]           |
| RetrieveServiceFeesInternalTransfersResponse.Commisions[n].Commission.VariableRateIndicator                                | Indicador para determinar si es tasa Variable ó Fijo         | boolean   | [1..1]           |
| **RetrieveServiceFeesInternalTransfersResponse.Commisions[n].Commission.Amount**                                           | Objeto que contiene los montos                               | object    | [1..n]           |
| RetrieveServiceFeesInternalTransfersResponse.Commisions[n].Commission.Amount.Value                                         | Monto comisión                                               | number    | [1..1]           |
| RetrieveServiceFeesInternalTransfersResponse.Commisions[n].Commission.Amount.MinimumValue                                  | Monto mínimo                                                 | number    | [1..1]           |
| RetrieveServiceFeesInternalTransfersResponse.Commisions[n].Commission.Amount.MaximumValue                                  | Monto máximo                                                 | number    | [1..n]           |
| **RetrieveServiceFeesInternalTransfersResponse.Commisions[n].Commission.VariableAmount**                                   | Objeto que contiene montos variables                         | object    | [1..n]           |
| RetrieveServiceFeesInternalTransfersResponse.Commisions[n].Commission.VariableAmount.MinimumValue                          | Monto mínimo variable                                        | number    | [1..1]           |
| RetrieveServiceFeesInternalTransfersResponse.Commisions[n].Commission.VariableAmount.MaximumValue                          | Monto máximo variable                                        | number    | [1..1]           |


## API Response Error

| **Body Error**               | **Descripción**                                    | **Tipo**    | **Cardinalidad** |
|------------------------------|----------------------------------------------------|:-----------:|:----------------:|
| **error**                    | Objeto que contiene la información del error       | array       | [0..n]           |
| error[*].status_code         | Código de error                                    | string      | [1..1]           |
| error[*].message             | mensaje de error                                   | string      | [1..1]           |