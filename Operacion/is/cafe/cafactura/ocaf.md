---
layout: default
title: Compras de Café
permalink: /Operacion/is/cafe/cafactura/ocaf
editable: si
---

# OCAF - Compras de Café

La aplicación **OCAF** permite registrar las compras de café que se realicen y así poder ver reflejada la mercancía en los inventarios.  

![](ocaf.png)

**Documento:** seleccionar el documento asignado a la compra de café. Los documentos son parametrizados en la aplicación [**BDOC - Documentos**](http://docs.oasiscom.com/Operacion/common/bsistema/bdoc).  
**Número:** el número de consecutivo será asignado automáticamente por el sistema.  
**Ubicación:** Indicar la ubicación donde va a quedar almacenado el café.  
**Concepto:** Seleccionar del zoom el concepto por el cual se registra la compra del café. Los conceptos son parametrizados en la aplicación [**BCON - Conceptos**](http://docs.oasiscom.com/Operacion/common/bsistema/bcon).   
**Fecha:** fecha en la cual registra la compra del café.  
**Tercero:** número de identificación del tercero a quien se le compró el café. Si el tercero seleccionado es asociado, el sistema arrojará un mensaje de control de color verde indicando que se encuentra hábil.  

Si el cliente no se encuentra registrado en el sistema al momento de realizar la orden de compra, OasisCom permite crear dicho cliente en la base de datos. En el campo tercero daremos click derecho y seleccionaremos _Crear cliente_.  

![](cliente.png)

Para ver todos los terceros registrados es necesario oprimir la tecla _Enter_. Para crear el nuevo cliente, en el zoom agregaremos una nueva fila y diligenciaremos los datos correspondientes al nuevo cliente; igualmente, en el campo _Representante_, el usuario podrá almacenar al referido, finalmente damos click en _Aceptar_ para guardar la información.  

Cuando el usuario registre un tercero en el zoom, este se conservará de tal manera que el usuario pueda seleccionarlo para ser agregado al documento general que se está creando.  

![](cliente1.png)

**Estado:** Estado del registro _Activo, Procesado, Anulado_.  
**Fuente:** seleccionar de la lista desplegable la fuente con que se adquirió la marcancía, ya sea recursos propios, línea de financiamiento, entre otros.  
**Caja:** seleccionar la caja por la cual se desembolsará el dinero para el pago de la mercancía.  
**Baba:** registrar el porcentaje de baba o mucílago que contiene el café en cereza.  

#### _Detalle_

En el detalle se encuentran los datos relacionados con el café, sus características.  

**Muestra:** número de gramos obtenidos para la muestra. Este valor es traído por defecto por el sistema al momento de crear un nuevo registro.  

![](ocaf10.png)

 Dicho valor puede ser parametrizable en la aplicación WVAR - Variables, en esta aplicación nos ubicamos en el campo _VariableId_ y consultamos por el nombre _DefaultValueSample_ que hace referencia al campo **Muestra** de la aplicación OCAF. Ya en el registro, editamos la cantidad en el campo _Formula_ como se muestra a continuación.  

![](ocaf11.png)

#### **Actualización de la formula de liquidación del café, con el esquema de reconocimiento del porcentaje de la pasilla.**  

* A continuación se anexan las imágenes del ejemplo, donde se evidencia que ambas compras poseen la misma información de análisis de calidades **(Muestra, almendra sana y pasilla)** pero el precio kilo es diferente basado en las dos formulaciones.
* La configuración con las variables que se usan para el nuevo cálculo,   “CalculateMethodCoffeePrice”  = 1 indica que la formulación esta encendida, Cero que el precio de café se calculara sin tener en cuenta la valoración de las pasillas.  


* **[WVAR]**-Variable
![](ocaf18.png)  

* **[ODES]**-Precio de Cafe.
![](ocaf19.png)



NOTA:   Las imágenes 3 y 4 contiene la configuración con las variables que se usan para el nuevo cálculo,   “CalculateMethodCoffeePrice”  = 1 indica que la formulación esta encendida, Cero que el precio de café se calculara sin tener en cuenta la valoración de las pasillas.


Ahora, al momento de crear otro registro en la aplicación OCAF, el campo _Muestra_ traerá el valor que acabamos de asignar, de esta misma forma sucede con el campo _Flete_.  

![](ocaf23.png)

**Sacos:** cantidad de sacos de café.  
**Cantidad bruto:** cantidad en kilos.  
**Destare:** peso del costal.  
**Cantidad:** cantidad real de café.  
**Producto:** el sistema sugiere el producto luego de haber diligenciado la calidad del mismo.  

#### Vista Previa

La aplicación también cuenta con una vista previa que brinda soporte de compras de café.  

![](ocaf1.png)


## [Compra de Café por Factor](http://docs.oasiscom.com/Operacion/is/cafe/cafactura/ocaf#compra-de-café-por-factor)

Para realizar compra de café por Factor, adicionamos un nuevo registro dando click en el botón ![](+.png) de la barra de herramientas del maestro y diligenciamos el formulario.  

![](ocaf2.png)

##### _Datos Básicos_

**Documento:** El sistema traerá por defecto el documento CF - Compra de café.  
**Ubicación:** seleccionar la ubicación desde donde se compra el café, el sistema por defectó traerá la ubicación que se encuentre asociada al usuario que realiza el registro de compra. Las ubicaciones son parametrizables en la aplicación [**BUBI - Ubicaciones Organización**](http://docs.oasiscom.com/Operacion/common/borgan/bubi) 
**Concepto:** seleccionar el concepto por el cual se realiza la compra de café, en este caso seleccionar _Compra x Factor_. Los conceptos son parametrizables en la aplicación [**BCON - Conceptos**](http://docs.oasiscom.com/Operacion/common/bsistema/bcon).  

![](ocaf3.png)

##### _Datos Tercero_

**Tercero:** ingresar el número de identificación del tercero que vende el café a la cooperativa. El sistema validará automáticamente si el tercero es asociado, está hábil o inhábil, este mensaje de control sólo es de manera informativa y no interrumpe el proceso.  

![](ocaf4.png)

**Fuente:** seleccionar la fuente de donde provienen los recursos para comprar el café, ya sea por recursos propios o línea de financiamiento.  
**Caja:** el sistema por defecto asignará la caja de donde se tomarán los recursos para la compra del café, si se desea cambiar, damos doble click sobre el campo y seleccionamos la caja desde el zoom.  
**Dirección:** seleccionamos del zoom el nombre de la finca que vende el café. Las direcciones son parametrizables en la aplicación **BDIR - Direcciones**.  
**Sello:** seleccionamos del zoom el sello de certificación de calidad de la finca del cual proviene el café a comprar en caso tal que lo tenga. El sistema valida automáticamente con el nombre de la finca los sellos que esta posee. Los sellos son parametrizables en la aplicación **BDIR - Direcciones**.  
**Condición de pago:** seleccionar la condición de pago del café. Al seleccionar _Cheque_ el sistema activará el flag de _Cheque_ y arrojará el número de cheque.  

##### _Datos Café_

**Muestra:** indicar el mínimo de muestra de café en gramos que se debe tomar para analizar.  
**Sacos:** ingresar el número de sacos que lleva el caficultor para la venta.  
**Peso Bruto:** peso de los sacos de café en kilos.  
**Destare:** peso promedio de los sacos vacíos en total.  
**Cantidad:** el sistema automáticamente arroja la diferencia entre el peso bruto y el destare indicando la cantidad real de café.  
**AlmendraSan:** cantidad en gramos de almendra (café )sana de acuerdo a la muestra.  
**Gramos pasilla:** cantidad en gramos de la almendra (café) defectuosa de acuerdo a la muestra.  
**Gramos broca:** cantidad en gramos de la almendra (café) brocada de acuerdo a la muestra.  
**Producto:** al dar doble click en el campo, el sistema analizará la muestra de café ingresada y arrojará los productos que aplican de acuerdo al rango de factor.  

Diligenciado el formulario, damos click en el botón _Guardar_ y la aplicación arrojará automáticamente un renglón en la pestaña _Detalle_ con los datos de la compra, el factor asignado al producto y el precio.  

![](ocaf5.png)

Al trasladarnos a la pestaña _**Pago**_, veremos un renglón con la condición de pago definida en el maestro de la aplicación, se permite adicionar otra condición de pago a la misma compra siempre y cuando el documento se encuentre en estado _Activo_.  

![](ocaf6.png)  

Cuando el pago se efectua con **Cedula Cafetera**, esta forma de pago se parametriza desde el **BFOR**.  

![](ocaf21.png)  

En el momento de procesar el registro el sistema valida toda la parametrización que se ha mostrado previamente y muestra una ventana para suministrar un **token** que se utiliza en la comunicación con el servicio.  

![](ocaf22.png)  

Al dar clic en el botón "Aceptar" la aplicación intentará conectarse con el sistema de cédula cafetera.  Intregacion realizada al webservice del Banco Bogota configuarcion PSE.  
NOTA: Cuando la comunicación con el banco está activa, la compra de café debe ser exitosa, de lo contrario el registro no debe ser procesado.  


*****
Si el pago se realiza con **BFOR**(forma pago) **diferente** a cedula cafetera se procede asi:  
Confirmar la factura dando click en el botón _Procesar_![](procesar.png) ubicado en la barra de herramientas del maestro y revisamos la pestaña del detalle _Contabilización_ para ver las cuentas contables afectadas.  

![](ocaf7.png)  

Para acceder a la vista previa del documento, damos click en el botón _Imprimir_ ![](impresion.png) ubicado en la barra de herramientas, el cual nos permitirá ver el documento e imprimirlo.  

![](ocaf8.png)  


![](ocaf9.png)  

##COMPRA DE CAFE PAGO DE INCENTIVO FLO.

El sistema para que adicional al precio del producto por factor, teniendo en cuenta el precio base del día, se le cancele el incentivo de $400 por kilo adicional, afectando la cuenta del incentivo en el Pasivo.  
Es de aclarar que como el producto es FLO, normalmente el precio tiene BONIFICACION POR PROGRAMA en la definición del precio del día, lo cual no debe ser tenida en cuenta para el cálculo del precio SI paga el incentivo.  

El incentivo solo se paga hasta 500 kilos durante la vigencia de 2020, si en la compra el asociado vendiera más de 500 kilos el incentivo es solo sobre 500. Por lo anterior, es necesario controlar el pago del incentivo por asociado.  


## [Compra de Café por Factor Húmedo](http://docs.oasiscom.com/Operacion/is/cafe/cafactura/ocaf#compra-de-café-por-factor-húmedo)

Para realizar compra de café por Factor Húmedo, debemos tener en cuenta la parametrización previa de las aplicaciones [**OBTA - Rango Tara y Agua**](http://docs.oasiscom.com/Operacion/is/cafe/caprecio/obta) y [**ODES - Precio de Café**](http://docs.oasiscom.com/Operacion/scm/compras/oprecio/odes). (_Ver aplicaciones_)

Adicionamos un nuevo registro dando click en el botón ![](+.png) de la barra de herramientas del maestro y diligenciamos el formulario tal como se diligencia para el proceso de [**compra de café por factor**](http://docs.oasiscom.com/Operacion/is/cafe/cafactura/ocaf#compra-de-café-por-factor). Para este esquema de compra de café por factor húmedo, debemos tener en cuenta que en el campo _Concepto_ debemos seleccionar el factor _CV - COMP X FACTOR HUM_, el cual permitirá al sistema sujerir los productos correspondientes a dicho factor para la compra.  


![](ocaf13.png)

![](ocaf14.png)


* **Importante:** El sistema validara la RETENCION acumulada diaria, por cada una de las ubicaciones en **OCAF** que esten procesadas, realizando la sumatoria  acumulanda; si aplica y es base de retencion esta se vera reflejada contablemente en la ultimo documento **OCAF**.  


## [Variable de Bonificación](http://docs.oasiscom.com/Operacion/is/cafe/cafactura/ocaf#variable-de-bonificación)

Cuando el factor de rendimiento determina que el café es muy bueno calidad AAA, entonces se le paga un valor adicional, sin que  supere un tope que en este  caso se indica en el WVAR.  
Ajuste a café AAA, se adicionan variable de tope WVAR para evaluar directamente en el descuento, que la bonificación por factor no supere el valor indicado en la variable.  


## [Control descuento Asociados superando Monto de Aportes](http://docs.oasiscom.com/Operacion/is/cafe/cafactura/ocaf#control-descuento-asociados-superando-monto-de-aportes)

Para controlar descuentos a los asociados superando el monto de aportes por año es necesario configurar las siguientes opciones:

Crear característica en la opción **BCRC** que contendrá las diferentes acciones sobre cada transacción.
![](bcrc.png)

Variable de empresa dentro de la opción **WVAR**, donde se registrará el monto de aportes por año.
![](wvar.png)

Con estas configuraciones básicas el sistema controlara los aportes por asociado, si supera el monto de aportes solicitara que se indique si se debe o no realizar el descuento en la transacción, esto se debe indicar en el maestro de la opción **OCAF** columna descuento.

Para realizar o no el descuento se debe indicar en el maestro en la columna ya mencionada.
![](ocaf24.png)  

El mensaje de control se presentara al momento de confirmar el registro si este supera los aportes parametrizados.
![](ocaf25.png) 

## [Pago concepto transporte](http://docs.oasiscom.com/Operacion/is/cafe/cafactura/ocaf#pago-concepto-transporte)   

Este concepto sirve para controlar el valor del transporte de cada producto, este valor se puede validar al momento de imprimir el registro en el campo Transporte.  

### [Parametrización](http://docs.oasiscom.com/Operacion/is/cafe/cafactura/ocaf#parametrización)   

Para que el sistema valide el pago por transporte se debe tener encuneta la siguiente parametrización: 

#### [WVAR - Variables](http://docs.oasiscom.com/Operacion/is/cafe/cafactura/ocaf#wvar---variables)

![](cafe.png) 

#### [ZBAS - Asociados](http://docs.oasiscom.com/Operacion/is/cafe/cafactura/ocaf#zbas---asociados)

![](cafe1.png) 

#### [BPRO - Productos](http://docs.oasiscom.com/Operacion/is/cafe/cafactura/ocaf#bpro---productos)

![](cafe2.png) 

#### [FPRE - Precios](http://docs.oasiscom.com/Operacion/is/cafe/cafactura/ocaf#fpre---precios)

![](cafe3.png) 

### [Funcionamiento](http://docs.oasiscom.com/Operacion/is/cafe/cafactura/ocaf#funcionamiento)   

En la aplicación OCAF al momento de crear un documento CF por concepto CF, diligenciar la información correspondiente, en el detalle de la aplicación se mostrara un campo llamado PrecioFlete, esto no afectara la contabilización de la retención y se vera reflejado en el reporte.   


![](cafe4.png)

![](cafe5.png)


## [Fidelización Asociados](http://docs.oasiscom.com/Operacion/is/cafe/cafactura/ocaf#fidelización-asociados)   

Para el correcto funcionamiento de la fidelización de asociados en la compra de café se debe tener presente la siguiente configuración:

Se deben tener configurados los códigos de cuenta PUN y VPU para el cálculo de puntos y configurados en el BPLA de los documentos que lo requieran.  En el Código de cuenta PUN debe existir la cuenta puente y VPU la cuenta que tendrá el valor acumulado por cada compra.   


![](fidelizar.png)
![](fidelizar1.png)

Los terceros que tendrán acceso a este beneficio deben estar marcados como clientes frecuentes en BTER, adicional debe existir en FDES configuración de un descuento tipo fidelización de cliente que contiene la formula deseada para realizar la conversión en kilos-puntos-valor.   

![](fidelizar2.png)

Para llevar ese valor otorgado como mayor valor del inventario se debe configurar el documento EN X AU que ajustara ese valor como un movimiento de ajuste al costo.  Adicional su correspondiente configuración en el BPLA.   

![](fidelizar3.png)


![](fidelizar4.png)

Con las configuraciones previas, el sistema está disponible para realizar las compras de forma correcta y si existe lugar de otorgar puntos lo realizara de forma automática.   

![](fidelizar5.png)



![](fidelizar6.png)



![](fidelizar7.png)



![](fidelizar8.png)
