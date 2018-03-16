---
layout: default
title: Campos
permalink: /Operacion/system/sconfig/scam
editable: si
---

# SCAM - Campos

La aplicación SCAM permite la configuración de reglas de negocio, control, tipos de campos y su obligatoriedad por empresa.  

### Parametrizar nueva restricción

Para parametrizar una nueva restricción, es necesario diligenciar el _programa_, el _tab_ al cual pertenece el campo (0 para el maestro y para los detalles el RowId de la parametrización del spro), el _nombre del campo_ (con la ayuda del comando Shift + F11), el _código del lenguaje_ (1 Inglés, 2 Español y 5 Portugues).  

![](scam.png)

**Nombre:** ingresar la etiqueta que se asignará al campo.  
**Descripción:** colocar un texto que se mostrará como ayuda al momento de editar.  
**Obligatorio:** se puede indicar si el campo parametrizado será obligatorio.  
**ErrorId:** se puede colocar un código de un error que se encuentre parametrizado en la opción **SERR - Errores**.  
**Condicion:** se puede parametrizar (en formato JSON) el tipo de datos que se debe validar en el campo y un conjunto de reglas de negocio como validaciones booleanas.  

![](scam1.png)

En el campo **"format"** se debe indicar el tipo de datos que debe validar la aplicación. Los tipos de datos que serán validados son: integer, number, date, time, datetime, url, email. Si este campo no se indica en el **JSON**, el sistema toma por defecto el formato de edición del JqGrid.  

En el campo **"customValidators"** se debe agregar una lista de condiciones lógicas que deben ser validadas, estas líneas serán unidas por medio del operador **"And"** de Javascript (&&), para hacer referencia a el valor que se está almacenado en el campo se debe utilizar la variable **"value"**.  

Si se desea hacer una validación de longitud de una cadena, se deben utilizar las funciones "maxLength(value, N)" y "minLength(value, N)" donde N es la longitud que será validada. Adicionalmente, se pueden validar expresiones regulares por medio de la función "evaluateRegex(pattern, value)" donde pattern es la expresión regular que será validada.  

### Parametrizar restricciones maestro tipo A y B

![](scam2.png)

En la aplicación BBAN:  

![](scam3.png)

El error parametrizado se mostrará al momento de guardar si no se cumple alguna de las condiciones parametrizadas.  

![](scam4.png)

### Parametrización restricciones maestros tipo C

Ingresamos a la aplicación SCAM y realizamos los cambios deseados.  

![](scam5.png)

Validamos en la aplicación correspondiente, que el cambio se haya efectuado satisfactoriamente.  

![](scam6.png)

El error parametrizado se mostrará al momento de guardar en caso tal que no se cumpla alguna de las condiciones definidas.  

![](scam7.png)

### Parametrización detalles opciones tipo B y C

Ingresamos a la aplicación SCAM y realizamos los cambios deseados.  

![](scam8.png)

Validamos en la aplicación correspondiente, que el cambio se haya efectuado satisfactoriamente.  

![](scam9.png)

El error parametrizado se mostrará al momento de guardar en caso tal que no se cumpla alguna de las condiciones definidas.  

![](scam10.png)

### Parametrización Zoom

Ingresamos a la aplicación SCAM y realizamos los cambios deseados.  

![](scam11.png)

Validamos en la aplicación correspondiente, que el cambio se haya efectuado satisfactoriamente.  

![](scam12.png)

![](scam13.png)

El error parametrizado se mostrará al momento de guardar en caso tal que no se cumpla alguna de las condiciones definidas.  

![](scam14.png)

### [Parametrizar Valores por Defectos](http://docs.oasiscom.com/Operacion/system/sconfig/scam#parametrizar-valores-por-defectos)

Esta nueva funcionalidad permite declarar valores por defecto sobre campos (Listas, Fechas, Flags, etc) de aplicaciones de parametrización básica sin detalle como lo son: BBAN, BCOL. También para aplicaciones de parametrización que contengan detalle, como: BPRO, BTER, BDOC, BUBI, entre otras. Igualmente, para aplicaciones de movimientos o transacciones como lo son: CMOV, TMOV, KMOV, etc.  

A continuación veámos algunos ejemplos.  

* Configuración en aplicaciones de parametrización con sólo maestro y con maestro y detalle.  

En el siguiente ejemplo para la aplicación BBAN - Bancos, definiremos que el campo llamado _Bank Code_ tríaga automáticamente el valor 100. Para ello, consultaremos en el campo _ProgramId_ la aplicación BBAN, seleccionamos el campo que deseamos parametrizar, en este caso _Bank Code_ e ingresamos el valor 100 en la columna _Default_. Damos click en el botón **Guardar** para salvar los cambios.  

![](scam15.png)

Al crear un nuevo registro en la opción BBAN, traerá el valor 100 en el campo _Bank Code_.  

![](scam16.png)

* Configuración en aplicaciones de movimientos.  

En la aplicación GFAC - Facturas, definiremos que al crear un nuevo registro el check _QuotaCopayment_ esté activo. Para ello, igualmente consultamos la aplicación GFAC y seleccionamos el campo a parametrizar, allí en la columna _Default_ digitamos la palabra _true_.  

![](scam17.png)

Al crear un registro en la aplicación GFAC.  

![](scam18.png)

* Parametrización en el detalle de aplicaciones de movimientos.  

Definiremos que al crear un renglón en el detalle de la aplicación GFAC- Facturas, el campo _Quantity_ tríga automáticamente el número 30.  

![](scam19.png)

Al crear un renglón en la aplicación GFAC.  

![](scam20.png)

* Parametrización en un Zoom.  

Como ejemplo, parametrizaremos que al crear un cliente en la aplicación GFAC, el campo _ClientType_ traíga automáticamente el tipo _CÉDULA_.  

Consultamos por la opción **ZGFAC** y seleccionamos el nombre del zoom a parametrizar. En el campo _Default_ ingresamos la letra **C** correspondiente a cédula.  

![](scam22.png)

Al crear un nuevo tercero en la aplicación GFAC.  

![](scam21.png)

### [Mensajes de error en tiempo de edición](http://docs.oasiscom.com/Operacion/system/sconfig/scam#mensajes-de-error-en-tiempo-de-edición)

Esta funcionalidad permite enseñar mensajes de error en los campos previamente parametrizados, mientras se esté editando un registro y no solamente cuando se de click en el botón _Guardar_.