# Financiera

Consulta a la entidad financiera o agente externo de la información del crédito para el producto de desgravamen.

## Consultar información financiera

El método consulta al banco o entidad externa la información financiera del crédito u operación a realizar

### HTTP Request
`GET por/definir`

### Content-type
`application/json`

### Objeto de consulta

> Ejemplo de objeto de consulta

```json
{
    "numeroDeOperacion": "1000000001"
}
```

Atributo | Tipo | Descripción
-------- | ---- | -----------
numeroDeOperacion | string | Número de operación o referencia del producto a asegurar

### Objeto de respuesta
> Ejemplo de objeto de respuesta

```json
{
    "tipoDeOperacion": "DHL",
    "moneda": "USD",
    "montoSolicitado": 30000,
    "deudores": [ 
        {
            "tipoIdentificacion": "CI",
            "numeroDeIdentificacion": "123456",
            "extension": "SC",
            "tipoDeDeudor": "Titular",
            "porcentajeOperacion": 100,
            "moneda": "USD",
            "montoActualSolicitado": 100,
            "plazoPresenteCredito": 100,
            "valorAcumulado": 100
        },
        {
            "tipoIdentificacion": "CI",
            "numeroDeIdentificacion": "987654",
            "extension": "SC",
            "tipoDeDeudor": "Codeudor",
            "porcentajeOperacion": 100,
            "moneda": "USD",
            "montoActualSolicitado": 100,
            "plazoPresenteCredito": 100,
            "valorAcumulado": 100
        }
    ]
}
```

Atributo | Tipo | Descripción
-------- | ---- | -----------
tipoDeOperacion | string | Codificación del tipo de crédito u operación `*por codificar`
moneda | string | Codificación de la moneda ISO 4217
montoSolicitado | number | Valor del crédito total
deudores | Arreglo de [Deudores](#deudores) | Listado de deudores

### Deudores

Atributo | Tipo | Descripción
-------- | ---- | -----------
tipoIdentificacion | string | Codificación del documento de identificación de deudor
numeroDeIdentificacion | string | Número de identificación
extension | string | Sufijo con el código del estado de emisión del carnet
tipoDeDeudor | string | Tipo de deudor `Titular` o `Codeudor`
porcentajeOperacion | number | Porcentaje de participación de la operación
moneda | string | Codificación de la moneda ISO 4217
montoActualSolicitado | number | Valor del crédito total
plazoPresenteCredito | number | Plazo en meses del crédito
valorAcumulado | number | Valor del cúmulo para el deudor