# Cúmulo

Método para la consulta de cúmulo para clientes titulares / codeudores hacia SFDC

## Cúmulo de clientes

El método consulta al banco o entidad externa el valor de cúmulo del cliente

### HTTP Request
`GET por/definir`

### Content-type
`application/json`

### Objeto de consulta

> Ejemplo de objeto de consulta

```json
{
    "tipoIdentificacion": "CI",
    "numeroDeIdentificacion": "123456",
    "complementoIdentificacion": "1A",
    "extensionIdentificacion": "SC",
    "tipoProducto": ""
}
```

Atributo | Tipo | Descripción
-------- | ---- | -----------
tipoIdentificacion | string | Codificación del documento de identificación de deudor
numeroDeIdentificacion | number | Número de identificación
complementoIdentificacion | string | Complemento al número de identificación
extensionIdentificacion | string | Sufijo con el código del estado de emisión del carnet
tipoProducto | string | `*por codificar`

### Objeto de respuesta
> Ejemplo de objeto de respuesta

```json
{
    "saldoAdeudado": 987654
}
```

Atributo | Tipo | Descripción
-------- | ---- | -----------
saldoAdeudado | number | Valor adeudado a la fecha de consulta por el cliente titular/codeudor