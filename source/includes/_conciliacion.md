# Conciliación 

Métodos para la conciliación de pagos hacia SF

## Conciliación de pago de pólizas

El método consulta al banco o entidad externa las pólizas que se han pagado en un rango de fechas

### HTTP Request
`GET por/definir`

### Content-type
`application/json`

### Objeto de consulta

> Ejemplo de objeto de consulta

```json
{
    "fechaInicial" : "2022-05-21",
    "fechaFinal" : "2022-05-21"
}
```

Atributo | Tipo | Descripción
-------- | ---- | -----------
fechaInicial | Date | Fecha inicial de la consulta de pólizas pagadas
fechaFinal | Date | Fecha final de la consulta de pólizas pagadas

### Objeto de respuesta
> Ejemplo de objeto de respuesta

```json
{
    "operaciones": [
        {
            "numeroDeOperacion": "101116026",
            "valorAsegurado": 100,
            "periodo": 30,
            "producto": "DHL",
            "tipoIdentificacion": "CI",
            "numeroDeIdentificacion": 123456,
            "complementoIdentificacion": "1A",
            "extensionIdentificacion": "SC"
        },
        {
            "numeroDeOperacion": "101116026",
            "valorAsegurado": 100,
            "periodo": 30,
            "producto": "DHL",
            "tipoIdentificacion": "CI",
            "numeroDeIdentificacion": 123458,
            "complementoIdentificacion": "2A",
            "extensionIdentificacion": "SR"
        },
        {
            "numeroDeOperacion": "101116027",
            "valorAsegurado": 100,
            "periodo": 90,
            "producto": "DHL",
            "tipoIdentificacion": "CI",
            "numeroDeIdentificacion": 876454,
            "complementoIdentificacion": "1A",
            "extensionIdentificacion": "SC"
        }
    ]
}
```

Atributo | Tipo | Descripción
-------- | ---- | -----------
operaciones | Arreglo de [Items de conciliación](#items-de-conciliacion) | Las pólizas a conciliar el pago

### Items de conciliación

Atributo | Tipo | Descripción
-------- | ---- | -----------
numeroDeOperacion | string | Número de operación o referencia del producto a asegurar
valorAsegurado | number | Valor restante de la operacion para el deudor
periodo | number | periodo en días que se estan pagando
producto | string | Codificación del tipo de crédito u operación `*por codificar`
tipoIdentificacion | string | Codificación del documento de identificación de deudor
numeroDeIdentificacion | number | Número de identificación
complementoIdentificacion | string | Complemento al número de identificación
extensionIdentificacion | string | Sufijo con el código del estado de emisión del carnet