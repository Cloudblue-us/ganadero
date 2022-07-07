# Cuentas 

Métodos para consulta de cuentas de clientes

## Cuentas de Clientes

El método consulta al banco o entidad externa las cuentas con las que cuenta un cliente

### HTTP Request
`GET por/definir`

### Content-type
`application/json`

### Objeto de consulta

> Ejemplo de objeto de consulta

```json
{
    "tipoDeIdentificacion": "CI",
    "numeroDeIdentificacion": 12345,
    "complementoIdentificacion": "1A",
    "extensionIdentificacion": "LP"
}
```

Atributo | Tipo | Requerido | Descripción
-------- | ---- | --------- | -----------
tipoDeIdentificacion | string | true | Tipo de identificación del cliente, CI para carnet de identificación, CIE para Cédula de extranjería
numeroDeIdentificacion | number | true | Número del carnet de identificación
complementoIdentificacion | string | true | Complemento al número de identificación
extensionIdentificacion | string | true | Sufijo con el código del estado de emisión del carnet

### Objeto de respuesta
> Ejemplo de objeto de respuesta

```json
{
    "id": 4613,
    "cuenta": 400445631546,
    "moneda": 0,
    "tipoProducto": "CAH",
    "estado": "Activo"
}
```

Atributo | Tipo | Descripción
-------- | ---- | -----------
id | string | Identificador de cuenta (Código único)
cuenta | string | Numero de cuenta bancaria
moneda | string | Moneda de la cuenta
tipoProducto | string | Código del Tipo de Producto (CAH/CC)
estado | string | Estado de la cuenta
