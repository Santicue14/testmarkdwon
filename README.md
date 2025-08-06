# Instructivo acuerdo comercial administrador

- [Utilidad](#utilidad)
- [Funcionalidad](#funcionalidad)
  - [Acceso](#acceso)
  - [Búsqueda](#búsqueda)
  - [Alta](#alta)
- [Almacenamiento de datos](#almacenamiento-de-datos)
- [Referencias](#referencias)

# Utilidad

Desde esta sección podremos gestionar las altas, bajas y modificaciones de los distintos acuerdos comerciales que tendrán lugar cuando una solicitud es otorgada a través de un comercio adherido.

# Funcionalidad

## Acceso

Para acceder a esta sección debemos ingresar a Liquidación > Acuerdo Comercial > Acuerdo Comercial > Administrador

![Acceso a panel de administrador](attachments/acceso.png)

## Búsqueda

Una vez accedemos, encontraremos un formulario donde podremos filtrar el / los acuerdos que queremos ver o modificar.
### Campos:
- ***Número de acuerdo***: número del acuerdo comercial.
- ***Código de sucursal***: código de la sucursal con el acuerdo asignado.
- ***Descripción***: descripción del acuerdo.
- ***CUIT***: CUIT de la sucursal.
- ***Forma pago***: forma de pago del acuerdo comercial.
- ***Medio de pago***: medio de pago del acuerdo comercial.
- ***Plazo liquidación***: plazo en días.
 
Cuando ya tenemos nuestros filtros listos, podremos buscar desde el botón superior.

![Acción de buscar](attachments/accion_buscar.png)

### Resultado

Una vez obtenido el resultado podremos exportarlo en *XLSX*, *PDF* o *imprimirlo* (la sección en **verde**).

También, podremos filtrar para *acceder* o *modificar* [^1] los acuerdos comerciales existentes. 

[^1]: [Casos de modificación](#modificación): Será provisorio sólo en casos de acuerdos con anticipos. Este admitirá a la hora de querer modificar el acuerdo la posibilidad de editar **TODOS** los campos, incluyendo el detalle de los rangos, permitiendo eliminar los existentes y agregar nuevos períodos e importes. A diferencia del caso DEFINITIVO, que este será NO EDITABLE, solo permitiendo agregar un archivo (acuerdo final firmado).


![Tabla de resultados](attachments/tabla.png)


## Alta

En caso de querer crear un nuevo acuerdo comercial, accederemos a un formulario presionando el botón "Alta" en la parte superior

![Acceso a formulario de alta](attachments/acceso_alta.png)

Dentro de esta sección encontraremos un formulario con varios campos a completar

1. **F. aplic. contrato:** Encontraremos un casillero donde podremos indicar la fecha de aplicación del contrato.
    ![Fecha de aplicación de contrato](attachments/f_aplic_contrato.png)

2. **Código de sucursal:** Deberemos seleccionar la sucursal la cual tendrá este acuerdo comercial indicando su código.
![Input código sucursal](attachments/cod_sucursal.png)

3. **Otros campos en la sección:** 
 - ***Descripción (autocompleta)***: descripción de la sucursal seleccionada.
 - ***CUIT (autocompleta)***: de la sucursal seleccionada.
 - ***F. firma contrato***: fecha de la firma del contrato de la sucursal. (informativo)
 - ***Estado acuerdo***: el estado del acuerdo puede ser DEFINITIVO / PROVISORIO.[^1]
 - ***Medio de pago***: se elige el medio de pago por el cuál se realizará el acuerdo comercial.
 - ***Plazo de liquidación***: se elige el plazo de liquidación del acuerdo comercial (según sucursal).
 - ***Fecha de inicio / fin***: Lapso de tiempo por el cuál el acuerdo comercial estará vigente.
 - ***Contrato vinculante***: código de contrato de acuerdo comercial.
 - ***Fecha contrato***: fecha del contrato de acuerdo comercial.

![Campos complementarios](attachments/otros_campos_acuerdo.png)

### Excepciones

En esta sección tendremos la opción de exceptuar planes comerciales los cuáles no querremos que tengan acceso a este acuerdo comercial.
Para ello, debemos agregar el código del plan a exceptuar como podemos observar debajo.

![Formulario de exceptuados](attachments/exceptuados.png)

### Rangos

Podremos además, agregar un rango de fechas y un importe donde tomará lugar este acuerdo.
Una vez le demos a agregar, se agregará en la lista el rango seleccionado.
Además podremos agregar un comentario (opcional).
![Formulario de exceptuados](attachments/rangos.png)

### Archivos

Por último se permite agregar un path sobre donde se ubicará el archivo
![Path de archivo sección](attachments/path_archivo.png)


# Almacenamiento de datos

- acuerdocomercial.numero
- acuerdocomercial.fechaContrato
- acuerdocomercial.plazoLiquidacion
- acuerdocomercial.FechaInicio
- acuerdocomercial.FechaFinalizacion
- acuerdocomercial.acuerdoProvisorio (1 verdadero | 0 falso)
- acuerdocomercial.fechaDefinitivo
- acuerdocomercial.acuerdoProvisorioOriginal (1 si nació en provisorio | 0 en definitivo)
- acuerdocomercial.fechaFinalizacionProvisorio
- acuerdocomercial.montoContratoProvisorio
- acuerdocomercial.comentario
- acuerdocomercialrango.fechaDesde
- acuerdocomercialrango.fechaHasta
- acuerdocomercialrango.periodo
- acuerdocomercialrango.importe
- tipoentidad.Descripcion
- formapagoacuerdo.Descripcion
- mediopagoacuerdo.Descripcion
- acuerdocomercialarchivo.fecha
- acuerdocomercialarchivo.hora
- acuerdocomercialarchivo.patharchivo


# Referencias

