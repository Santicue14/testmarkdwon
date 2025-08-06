# Generación de archivo de altas

- [Utilidad](#utilidad)
- [Funcionalidad](#funcionalidad)
  - [Ingreso](#ingreso)
  - [Selección](#selección)
  - [Confirmación](#confirmación)
  - [Visualización](#visualización)
- [Almacenamiento de datos](#almacenamiento-de-datos)
- [Referencias](#referencias)

# Utilidad

A partir de un usuario logueado, esta funcionalidad nos permite la posibilidad de generar archivos de altas en base a los distintos segmentos disponibles.

# Funcionalidad

## Ingreso

Para acceder a esta funcionalidad debemos acceder al menú lateral
ESTRATEGIA > SEGMENTO > ARCHIVO ALTAS
![Acceso a la funcionalidad](/attachments/arch_altas_menu.png)

## Selección

Una vez accedimos a la página, se encontrarán listados los segmentos de los cuáles se podrá generar el archivo correspondiente.

Aparecerán **TODOS** seleccionados, en caso de no requerir de alguno se podrán desmarcar dando click en el casillero correspondiente.
![Selección de segmentos](/attachments/seleccion_segmentos.png)


- En caso de querer desmarcar **TODOS** los casilleros marcados hacemos click en este botón
![Quitar selección](/attachments/quitar_seleccion.png)

---
- De la misma manera, en caso de querer volver a seleccionar todos hacemos click aquí.
![Seleccionar todos](/attachments/seleccionar_todos.png)



## Confirmación

Con los segmentos que desee ya marcados, hacemos click en el botón confirmar.
![Confirmación](/attachments/confirmacion.png)

Una vez confirmado, recibiremos el mensaje de confirmación de la solicitud, y recibiremos un archivo por cada segmento solicitado al email asignado.
![Mensaje de satisfacción](/attachments/mensaje.png)

## Visualización

Una vez descargado el archivo[^1] podremos visualizar la información del mismo.

[^1]: [Archivo de ejemplo](/attachments/20250801122546ESTUDIOALTAS.XLS)

# Almacenamiento de datos


- NUMERO = operacion.NumeroOperacion
- TIPO = tipoenvioestudio.Descripcion
- FECHA = operacion.Fecha
- NOMBRE = persona.Nombre (Relación on operacion.IdCliente = cliente.Id, luego cliente.ClavePersona = persona.ClavePersona)
- TIPODOCUMENTO = tipodocumento.Descripcion
- DOCUMENTO = persona.documento
- CUIL = persona.Cuil
- ESTADOCIVIL = estadocivil.Descripcion
- FECHANACIMIENTO = persona.fechaNacimiento
- SEXO = sexo.descripcion
- DOMICILIO = domicilio.calle + domicilio.numero + domicilio.Piso
- LOCALIDAD = localidad.Descripcion
- PROVINCIA = provincia.Descripcion
- CODIGOPOSTAL = domicilio.CodigoPostal
- LABORAL = (No trae valor)
- DIASMORA = new Date() - operacion.FechaCaida
- TOTALCUOTAS = operacion.CantidadCuotas
- CANTIDADCUOTASVENCIDAS = operacion.CantidadCuotasVencidas
- CANTIDADCUOTASIMPAGAS = operacion.CantidadCuotasImpagas
- NUMEROPRIMERACUOTAVENCIDA = operacion.CuotaCaida
- CAPITALOTORGADO = operacion.importeCapital
- SALDOTOTAL = (operacion.MontoCaido + operacion.deudaAVencer) - operacion.SumatoriaPagos
- DEUDAVENCIDA = operacion.MontoCaido
- PAGOMINIMO = operacion.ImportePagoMinimo
- 1ER VTO = (No trae valor)
- 2DO VTO = (No trae valor)
- VTOIMPAGO = operacion.FechaCaida
- VALORCUOTA = cuotasprestamo.importeCapital + cuotasprestamo.intereses
- VALORCUOTA2DOVENCIMIENTO = operacion.ImporteCuotaTercerVencimiento
- VALORCUOTAULTIMOVTO = operacion.ImporteCuotaUltimoVencimiento
- TIPOPRODUCTO = tipoproductoagrupado.Descripcion
- ARTICULO = articulo.Descripcion
- SUCURSAL = sucursalcliente.Codigo - sucursalcliente.Descripcion
- DESCRIPCIONTELEFONO1 = tipotelefono.Descripcion
- TIPOTELEFONO1 = (No trae valor)
- DATOTELEFONO1 = telefono.TelefonoCompleto
- DESCRIPCIONTELEFONO2 = tipoTelefono.Descripcion
- TIPOTELEFONO2 = (No trae valor)
- DATOTELEFONO2 = telefono.TelefonoCompleto
- DESCRIPCIONTELEFONO3 = tipoTelefono.Descripcion
- TIPOTELEFONO3 = (No trae valor)
- DATOTELEFONO3 = telefono.TelefonoCompleto
- DESCRIPCIONTELEFONO4 = tipoTelefono.Descripcion
- TIPOTELEFONO4 = (No trae valor)
- DATOTELEFONO4 = telefono.TelefonoCompleto
- TELEFONOSADICIONALES = telefono.Descripcion | tipotelefono.Descripcion | telefono.TelefonoCompleto | ...
- FECHAASIGNACION = operacion.fechaEstudio
- FECHAULTIMOPAGO = MAX(cuotasPrestamo.fechaPago)
- DEUDACAPITAL = operacion.CapitalAdeudado
- SALDOAREFINANCIAR = refinanciacion.MontoARefinanciar
- DATOSGESTION = (No trae valor)
- SCORE = cliente.ScoreVeraz
- MAIL = cliente.Mail
- CODIGOCOMPANIA = compania.codigo
- OPERADORASIGNADO = (No trae valor)
- DATOSANEXOS = (No trae valor)
- CONVENIOASOCIADO = operacion.NumeroConvenio





- estudio.codigo
- estudio.descripcion
- estudio.emailAltas


# Referencias

- https://divinf.atlassian.net/wiki/spaces/DFC/pages/237928458/Segmentacion?atlOrigin=eyJpIjoiN2RiNzRjZWViMDk2NDVjOWI4Yzk4N2RiMDMzODAzNTkiLCJwIjoiYyJ9
- https://divinf.atlassian.net/wiki/spaces/DFC/pages/237862920/Marca+Excel?atlOrigin=eyJpIjoiMjJiZDViYWI1ZWZiNDFkZGE0YTVhOGJjZmM2MDMwZmIiLCJwIjoiYyJ9