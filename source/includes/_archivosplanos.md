# Archivos Planos

## Certificado de cobertura emitido asociado a una Operación

> Ejemplo de campos del archivo

```txt
Tipo de documento,
Número,
Complemento,
Extensión,
Tipo de producto,
Fecha de solicitud,
Número de solicitud *,
Número de operación,
jts_oid,
Tipo de Operación,
Número Línea de Crédito

* Solo aplica para Operaciones con Flujo. Para las fuera de Flujo viene vacío
```

### Periodicidad
Diario
### Horario
\>= 00:00
### Repositorio
SFTP
### Tipo de archivo
TXT
### Nombre Archivo:
OP_CRED_YYYY_MM_DD


## Alimentar el detalle de primas cobradas en el Banco diariamente.

> Ejemplo de campos del archivo

```txt
Numero operación ASFI,
Tipo_Producto (Reg/No Reg),
Jts_oid,
Fecha desembolso,
Fecha vencimiento operación,
Monto desembolsado,
Valor asegurado operación (Saldo),
Intereses reportados,
Periodo coberturado de pago en días,
Prima Total,
Diferimiento (SI/NO),
Tipo de documento,
Número,
Complemento,
Extensión
```

### Periodicidad
Diario
### Horario
\>= 00:00
### Repositorio
SFTP
### Tipo de archivo
TXT
### Nombre Archivo:
CONC_COB_PRIMAS_YYYY_MM_DD


## Datos de solicitud seguro Tarjetas de Crédito

> Ejemplo de campos del archivo

```txt
Tipo de documento,
Número,
Complemento,
Extensión,
Tipo Tarjeta,
Nombre Tarjeta,
Nro Tarjeta CMS,
Nro Cuenta CMS,
Nro Solicitud,
Nro Operación,
Límite de tarjeta crédito,
Fecha vencimiento tarjeta,
Moneda,
NIT,
Producto TC/Producto *,
Prima,
Fecha de Alta,
Fecha de corte mensual,
Tipo de Seguro (Desgravamen, Sepelio y Protección),
Grupo Afinidad

* Dentro de Tarjetas de Crédito se requiere identificar a que tipo de tarjeta corresponde.
```

### Periodicidad
Diario
### Horario
\>= 00:00
### Repositorio
SFTP
### Tipo de archivo
TXT
### Nombre Archivo:
SEG_TC_YYYY_MM_DD


## Datos de solicitud seguro Tarjetas de Débito

> Ejemplo de campos del archivo

```txt
Tipo de documento,
Número,
Complemento,
Extensión,
Tipo Tarjeta,
Nombre Tarjeta,
Sucursal,
Seguro Protección,
ID Tarjeta/Nro Tarjeta,
Fecha vencimiento tarjeta,
Moneda,
NIT,
Prima,
Fecha de Alta
```

### Periodicidad
Diario
### Horario
\>= 00:00
### Repositorio
SFTP
### Tipo de archivo
TXT
### Nombre Archivo:
SEG_TD_YYYY_MM_DD


## Conciliación de pagos Tarjetas de Crédito

> Ejemplo de campos del archivo

```txt
Nro Tarjeta CMS,
Nro Cuenta CMS,
Sucursal,
Jts_oid,
Nro Operación,
Limite Credito,
Nombre TarjetaHabiente,
Tipo de documento,
Número,
Complemento,
Extensión,
Saldo Deudor,
Moneda,
Fecha de Alta,
Prima Total
Fecha de corte mensual,
Tipo de Seguro (Desgravamen, Sepelio y Protección)
```

### Periodicidad
Mensual     Banco debe confirmar fecha exacta de cada mes 
### Horario
\>= 00:00
### Repositorio
SFTP
### Tipo de archivo
TXT
### Nombre Archivo:
CONC_COB_TC_YYYY_MM_DD


## Conciliación de pagos Tarjetas de Débito

> Ejemplo de campos del archivo

```txt
ID Tarjeta/Nro Tarjeta,
Moneda,
Saldo Jts_oid,
Tipo de documento,
Número,
Complemento,
Extensión,
Saldo,
Período,
Importe,
Sucursal TJD
```

### Periodicidad
Mensual     Banco debe confirmar fecha exacta de cada mes 
### Horario
\>= 00:00
### Repositorio
SFTP
### Tipo de archivo
TXT
### Nombre Archivo:
CONC_COB_TD_YYYY_MM_DD
