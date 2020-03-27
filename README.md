# Proyecto festival ACME - Ubicuos 

### Descripción del proyecto

La empresa ACME quiere preparar un festival en la ciudad de Popayán. Para tener éxito la empresa ha solicitado una aplicación móvil basada en NFC (llamada Festival ACME) que le permita:

- Entrada al festival rápido y con orden. Con las pulseras NFC los asistentes pueden entrar en el recinto solo enseñando las pulseras al personal de seguridad, el cual con la aplicación “Festival ACME” puede averiguar si la pulsera es de un asistente o no lo es (muchas personas intentan colarse en dichos festivales) o si cancelo previamente la entrada al festival.

- Pago rápido y eficaz. Los asistentes deben cargar sus pulseras con anticipación en sitios autorizados por medio de la aplicación “Festival ACME” para poder pagar su entrada y su consumo en el festival. De esta forma la empresa pretende decir Adiós a las colas para pagar, adiós a esas barras que se quedaban sin cambio, adiós a esos problemas con el datafono que no permitían cobrar a ciertos asistentes, adiós a las cajas que no cuadraban al final del festival.

## Materiales usados
- **Software:** 
  - MIT APP inventor
- **Hardware:**
  - Pulsera RFID/NFC
  - Dispositivo móvil con sensor NFC

## Flujo de la aplicación

A continuación, se explicará el flujo de la aplicación haciendo uso de capturas en el dispositivo móvil y de los bloques de código desarrollados en App Inventor.

### Estado inicial de la aplicación
La aplicación de ACME festival está diseñada para cumplir las dos partes escritas en la descripción del video. La primera parte, es para controlar la entrada de los asistentes, y la segunda, es la simulación de la recarga de la pulsera y/o compra en tiendas del evento.

<p align="center">
<img src="https://github.com/LuisFelipeL/FestivalACME/blob/master/Images/1.jpg" width="200px">
</p>

#### Entrada
- **Botón "Entrada"**

En este bloque de código, se activan los botones "Registrar Asistente" y "Tomar Asistencia", y se desactivan otros botones y formularios.
<p align="center">
<img src="https://github.com/LuisFelipeL/FestivalACME/blob/master/Images/2.PNG">
</p>

Así se ve en la interfaz.
<p align="center">
<img src="https://github.com/LuisFelipeL/FestivalACME/blob/master/Images/2-1.jpg" width="200px">
</p>

- **Botón "Registrar Asistente"**

En este bloque de código, se activa el NFC del dispositivo móvil para poder **escribir** la pulsera NFC, se activa el formulario para registrar a la persona asistente y se estructura la forma en la que se trabajará los datos dentro de las pulseras NFC. El formato de los datos es el siguiente: _"ACME/NombreAsistente/PagoFestival/SaldoTotal"_
<p align="center">
<img src="https://github.com/LuisFelipeL/FestivalACME/blob/master/Images/3.PNG">
</p>

Así se ve en la interfaz. En esta parte, es donde se escribe la pulsera NFC con los datos que son escritos en el formulario, pero primero son estructurado en el formato antes escrito.
<p align="center">
<img src="https://github.com/LuisFelipeL/FestivalACME/blob/master/Images/3-1.jpg" width="200px">
<img src="https://github.com/LuisFelipeL/FestivalACME/blob/master/Images/3-2.jpg" width="200px">
</p>

- **Botón "Tomar Asistencia"**

En este bloque de código, se activa el NFC del dispositivo móvil para poder **leer** la pulsera NFC y se escribe un mensaje en pantalla de espera para leer la pulsera y mostrar los datos almacenados en esta.
<p align="center">
<img src="https://github.com/LuisFelipeL/FestivalACME/blob/master/Images/4.PNG">
</p>

Así se ve en la interfaz.
<p align="center">
<img src="https://github.com/LuisFelipeL/FestivalACME/blob/master/Images/4-1.jpg" width="200px">
</p>

- **Función "TagRead()"**

En este bloque de código, se activa cuando el sensor detecta una pulsera NFC en modo **lectura**, lo primero es comprobar el formato almacenado en la pulsera, para luego dividir los datos usando la función Split en los "/".

Como primer filtro, se comprueba si la pulsera es autentica del festival, si no lo es, mostrará un mensaje en rojo, diciendo: "No es una manilla oficial del Festival ACME".

Como segundo filtro, se comprueba si se realizó el pago respectivo del festival, si no se ha pagado, mostrará un mensaje en naranja, diciendo: "No se ha realizado el pago. No se le permite el ingreso".

Por último, si se ha realizado el pago, mostrará un mensaje en verde, diciendo: "Se realizó el pago. Puede ingresar.", y además, mostrará los datos del asistente.

<p align="center">
<img src="https://github.com/LuisFelipeL/FestivalACME/blob/master/Images/5.PNG">
</p>

Así se ve en la interfaz y cada una de las posibilidades.
<p align="center">
<img src="https://github.com/LuisFelipeL/FestivalACME/blob/master/Images/5-1.jpg" width="200px">
<img src="https://github.com/LuisFelipeL/FestivalACME/blob/master/Images/5-2.jpg" width="200px">
<img src="https://github.com/LuisFelipeL/FestivalACME/blob/master/Images/5-3.jpg" width="200px">
</p>

#### Recarga y compra

- **Botón "Tienda"**

En este bloque de código, se activan los botones "Validar", "Recargar", "Compra", y se desactivan los botones de "Entrada" y formularios.
<p align="center">
<img src="https://github.com/LuisFelipeL/FestivalACME/blob/master/Images/6.PNG">
</p>

Así se ve en la interfaz.
<p align="center">
<img src="https://github.com/LuisFelipeL/FestivalACME/blob/master/Images/6-1.jpg" width="200px">
</p>

- **Botón "Validar"**

En este bloque de código, es igual a el apartado de "Tomar Asistencia", esto se hace con el fin de cargar los datos de la pulsera en memoria para luego sobre escribir y actualizar los datos. Se activa el NFC del dispositivo móvil para poder **leer** y se escribe un mensaje en pantalla de espera para leer la pulsera y mostrar los datos almacenados en esta.
<p align="center">
<img src="https://github.com/LuisFelipeL/FestivalACME/blob/master/Images/7.PNG">
</p>

Así se ve en la interfaz.
<p align="center">
<img src="https://github.com/LuisFelipeL/FestivalACME/blob/master/Images/7-1.jpg" width="200px">
<img src="https://github.com/LuisFelipeL/FestivalACME/blob/master/Images/7-2.jpg" width="200px">
</p>

- **Botón "Recargar"**

En este bloque de código, simula la recarga de saldo que luego va ser usado para comprar viveres dentro del festival, lo que se hace es tomar los datos cagados en el apartado de "Validar" y adicionar el monto escrito en el input al saldo del asistente.
<p align="center">
<img src="https://github.com/LuisFelipeL/FestivalACME/blob/master/Images/8.PNG">
</p>

Así se ve en la interfaz.
<p align="center">
<img src="https://github.com/LuisFelipeL/FestivalACME/blob/master/Images/8-1.jpg" width="200px">
</p>

- **Función "TagWrite()"**

En este bloque de código, se activa cuando el sensor detecta una pulsera NFC en modo **escritura**, se muestra en la vista de "Recargar" y "Compra" cuando la transacción se realizó satisfactoriamente.
<p align="center">
<img src="https://github.com/LuisFelipeL/FestivalACME/blob/master/Images/9.PNG">
</p>

Así se ve en la interfaz. En la segunda imagen se hace uso otra vez del botón "Validar" para comprobar que se añadio corectamente a saldo total del asistente.
<p align="center">
<img src="https://github.com/LuisFelipeL/FestivalACME/blob/master/Images/9-1.jpg" width="200px">
<img src="https://github.com/LuisFelipeL/FestivalACME/blob/master/Images/9-2.jpg" width="200px">
</p>

- **Botón "Compra"**

En este ultimo bloque de código, es muy similar al apartado de "Recargar" solo que aqui simula la compra y sustrae una cuantia al saldo total del asistente. 
<p align="center">
<img src="https://github.com/LuisFelipeL/FestivalACME/blob/master/Images/10.PNG">
</p>

Así se ve en la interfaz.
<p align="center">
<img src="https://github.com/LuisFelipeL/FestivalACME/blob/master/Images/10-1.jpg" width="200px">
<img src="https://github.com/LuisFelipeL/FestivalACME/blob/master/Images/10-2.jpg" width="200px">
<img src="https://github.com/LuisFelipeL/FestivalACME/blob/master/Images/10-3.jpg" width="200px">
</p>
