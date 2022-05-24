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
    "numeroDeSolicitud": "1000000001"
}
```

Atributo | Tipo | Descripción
-------- | ---- | -----------
numeroDeSolicitud | string | Número de operación o referencia del producto a asegurar

### Objeto de respuesta
> Ejemplo de objeto de respuesta

```json
{
    "tipoDeOperacion": "DHL",
    "moneda": "USD",
    "montoSolicitado": 30000,
    "montoAprobado": 10000,
    "plazoCredito": 100,
    "departamento": 100,
    "ciudad": 100,
    "lineaDeCredito" : {
        "numero": "",
        "moneda": "USD",
        "fechaDeVigencia": "2020-02-15"
    },
    "deudores": [, 
        {
            "tipoIdentificacion": "CI",
            "numeroDeIdentificacion": "123456",
            "complementoIdentificacion": "1A",
            "extensionIdentificacion": "SC",
            "tipoDeDeudor": "Titular"
        },
        {
            "tipoIdentificacion": "CI",
            "numeroDeIdentificacion": "987654",
            "complementoIdentificacion": "1A",
            "extensionIdentificacion": "SC",
            "tipoDeDeudor": "Codeudor"
        }
    ]
}
```

Atributo | Tipo | Descripción
-------- | ---- | -----------
tipoDeOperacion | string | Codificación del tipo de crédito u operación `*por codificar`
moneda | string | Codificación de la [moneda ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)
montoSolicitado | number | Valor del crédito total
montoAprobado | number | Valor apreobado del crédito
plazoCredito | number | Plazo en meses del crédito
departamento | number | Código del departamento donde se solicitó el crédito `*por codificar`
ciudad | number | Código de la ciudad donde se solicitó el crédito `*por codificar`
lineaDeCredito | Objeto de [Línea de Crédito](#linea-de-credito) | Parámetros de la línea de crédito
deudores | Arreglo de [Deudores](#deudores) | Listado de deudores

### Línea de Crédito

Atributo | Tipo | Descripción
-------- | ---- | -----------
numero | string | Número de la línea de crédito
moneda | string | Codificación de la [moneda ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)
fechaDeVigencia | date | Fecha de vigencia

### Deudores

Atributo | Tipo | Descripción
-------- | ---- | -----------
tipoIdentificacion | string | Codificación del documento de identificación de deudor
numeroDeIdentificacion | number | Número de identificación
complementoIdentificacion | string | Complemento al número de identificación
extensionIdentificacion | string | Sufijo con el código del estado de emisión del carnet
tipoDeDeudor | string | Tipo de deudor `Titular` o `Codeudor`