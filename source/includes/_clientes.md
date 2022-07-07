# Clientes

Consulta a la entidad financiera o agente externo de la información del cliente.

## Consultar clientes

El método consulta al banco o entidad externa la información personal, de contacto y relaciones del cliente

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
    "extensionIdentificacion": "SC",        
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
    "nombre": "Juanita",
    "apellidoPaterno": "Pérez",
    "apellidoMaterno": "Ramirez",
    "apellidoDeCasada": "de Rodríguez",
    "sexo": "Femenino",
    "fechaDeNacimiento": "1970-05-21",
    "correoElectronico": "juanita.perez@prueba.com",
    "estadoCivil": "Casado/a",
    "nacionalidad": "Boliviana",
    "redesSociales": "",
    "cantidadHijos": 0,
    "ingresoPesos": "",
    "nivelIngresos": 00000,
    "nivelEducacion": "",
    "discapacitado": false,
    "tipoDeVivienda": "",
    "porcentajeCreditoAsumido": 70,
    "informacionDelConyuge": {
        "nombre": "Juan",
        "apellidoPaterno": "Rodríguez",
        "apellidoMaterno": "Sanchez",
        "apellidoDeCasada": "",
        "sexo": "Masculino",
        "fechaDeNacimiento": "1968-03-14",
        "correoElectronico": "juan.rodriguez@prueba.com",
    },
    "informacionDeResidencia": {
        "paisDeResidencia": "Bolivia",
        "direccion": "Calle del Alto, N 50",
        "departamento": "La Paz",
        "ciudad": "La Paz",
        "telefono": "1234567",
        "celular" : "12345678"
    },
    "informacionLaboral": {
        "lugarDeTrabajo": "Empresa de construcción ABC",
        "cargo": "Gerente",
        "profesion": "Ingeniero",
        "actividadEconomica": "",
        "fechaDeIngresoAlTrabajo": "2020-02-15",
        "domicilioComercial": "Calle de los ingenieros, N 12",
        "departamento": "La Paz",
        "ciudad": "La Paz",
        "telefono": "1234567",
        "correoElectronico": "contacto@abcconstructores.com" 
    },
    "referencias": [
        {
            "tipo": "Personal",
            "nombre": "Juan",
            "apellidoPaterno": "Pérez",
            "apellidoMaterno": "Ramirez",
            "apellidoDeCasada": "",
            "relacion": "Hermano",
            "telefono": "1234789",
            "correoElectronico": "juan@prueba.com",
            "entidad": ""
        },
        {
            "tipo": "Bancaria",
            "nombre": "Alberto",
            "apellidoPaterno": "Marquez",
            "apellidoMaterno": "",
            "apellidoDeCasada": "",
            "relacion": "",
            "telefono": "1234789",
            "correoElectronico": "alberto@bancomayor.com",
            "entidad": "Banco Mayor"
        }
    ]
}
```

Atributo | tipo | Requerido | Descripción
-------- | ---- | --------- | -----------
nombre | string | true | Nombres del cliente
apellidoPaterno | string | true | Apellido paterno del cliente
apellidoMaterno | string | false | Apellido materno del cliente
apellidoDeCasada | string | false | Apellido de casada de la cliente
sexo | string | true | Sexo del cliente. Valores permitidos `Masculino` o `Femenino`
fechaDeNacimiento | date | true | Fecha de nacimiento del cliente
correoElectronico | string | true | Correo electrónico del cliente
estadoCivil | string | true | Estado civil del cliente. Valores permitidos `Casado`, `Soltero`, `Separado` o `Viudo`
nacionalidad | number | Código de la nacionalidad del cliente `*por definir*`
redesSociales | string | `*por definir*`
cantidadHijos | number | Cantidad de hijos del cliente
ingresoPesos | number | `*por definir*`
nivelIngresos | number | `*por definir*`
nivelEducacion | string | `*por definir*`
discapacitado | boolean | `*por definir*`
tipoDeVivienda | string | `*por definir*`
porcentajeCreditoAsumido | number | Porcentaje del crédito asumido por el cliente
informacionDelConyuge | [Información del cónyuge](#Informacion-del-conyugue) | false | Contiene la información del cónyuge del cliente
informacionDeResidencia | [Información de residencia](#Informacion-de-residencia) | true | Contiene la información de residencia del cliente
informacionLaboral | [Información laboral](#Informacion-laboral) | true | Contiene la información laboral del cliente
referencias | Arreglo de [Referencias](#Referencias) | false | Referencias personales y bancarias del cliente

### Información del cónyuge

Atributo | tipo | Requerido | Descripción
-------- | ---- | --------- | -----------
nombre | string | true | Nombres del cónyuge
apellidoPaterno | string | true | Apellido paterno del cónyuge
apellidoMaterno | string | false | Apellido materno del cónyuge
apellidoDeCasada | string | false | Apellido de casada de la cónyuge
sexo | string | true | Sexo del cónyuge. Valores permitidos `Masculino` o `Femenino`
fechaDeNacimiento | date | true | Fecha de nacimiento del cónyuge
correoElectronico | string | true | Correo electrónico del cónyuge

### Información de residencia

Atributo | tipo | Requerido | Descripción
-------- | ---- | --------- | -----------
paisDeResidencia | string | true | Código del país de residencia del cliente
direccion | string | true | Dirección de residencia del cliente
departamento | string | true | Departamento de residencia `*Por definir si es codificado`
ciudad | string | true | Ciudad de residencia `*Por definir si es codificado`
telefono | string | true | Teléfono del cliente
celular | string | true | Celular del cliente

### Información laboral

Atributo | tipo | Requerido | Descripción
-------- | ---- | --------- | -----------
lugarDeTrabajo | string | true | Lugar de trabajo del cliente `*por definir*`
cargo | string | false | Cargo del cliente
profesion | string | true | Profesión del cliente `revisar el listado de profesiones`
actividadEconomica | string | false | Códigos CAEDEC
fechaDeIngresoAlTrabajo | date | false | 
domicilioComercial | string | false | 
departamento | string | false | Departamento del lugar de trabajo `*Por definir si es codificado`
ciudad | string | false | Ciudad del lugar de trabajo `*Por definir si es codificado`
telefono | string | false | Teléfono del lugar de trabajo
correoElectronico | string | false | Correo electrónico del lugar de trabajo

### Referencias

Atributo | tipo | Requerido | Descripción
-------- | ---- | --------- | -----------
tipo | string | true | Define el tipo de referencia. Los valores válidos son `Personal` o `Bancaria`
nombre | string | true | Nombres del contacto de referencia
apellidoPaterno | string | true | Apellido paterno del contacto de referencia
apellidoMaterno | string | false | Apellido materno del contacto de referencia
apellidoDeCasada | string | false | Apellido de casada de la contacto de referencia
relacion | string | false | Si el tipo de referencia es `Personal` aca se escribe el tipo de relación personal que tiene el contacto con el cliente
telefono | string | false | Teléfono del lugar de trabajo
correoElectronico | string | true | Correo electrónico del contacto
entidad | string | false | Si el tipo de referencia es `Bancaria` aca se escribe la entidad bancaria a la que pertenece el contacto
