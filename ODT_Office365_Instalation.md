
## Office Deployment Tool

Para poder instalar **Microsoft Office 365** con la Herramienta de Implementación de Office (**Office Deployment Tool**) vamos a necesitar 3 archivos:

- [ ] setup.exe
- [ ] conf.xml
- [ ] Office

El primero es el instalador, un **.exe** el segundo es un **.xml** que guardará la configuración de como queremos instalar nuestro **Office 365** y el tercero son los datos de **Office 365**. Ahora vamos a ver como conseguir estos archivos.

### Primer paso
Tenemos que descargar las **ODT** (Herramienta de Implementación de Office), aquí tenemos el enlace de la página oficial.

- [Office Deployment Tool](https://www.microsoft.com/en-us/download/details.aspx?id=49117)

Una vez dentro de la página, le daremos al botón de "**Download**". Y nos descargará un **.exe**

![](/imagenes/foto1.png)

Al ejecutar este **.exe** nos pedirá una ruta donde descomprimir archivos, crearemos una carpeta con un nombre identificativo previamente para hacerlo ahí.

![](/imagenes/foto2.png)

Ahora ejecutamos el **.exe** como administrador.

![](/imagenes/foto3.png)

Permitimos que haga cambios en el dispositivo.

![](/imagenes/foto4.png)

Ahora aceptamos los términos de licencia de Microsoft y seguimos.

![](/imagenes/foto5.png)

Elegimos la carpeta que habíamos creado anteriormente y aceptamos.

![](/imagenes/foto6.png)

Veremos el mensaje de que se ha extraído correctamente.

![](/imagenes/foto7.png)

Este es el contenido que nos deja. Para la instalación/actualización de Office 365 no vamos a necesitar estos **.xml** así que los podemos borrar.

![](/imagenes/foto8.png)

- [x] setup.exe
- [ ] conf.xml
- [ ] Office

Ahora necesitamos crear nuestro archivo **.xml** con nuestra configuración que variará según nuestras preferencias. Podemos crearlo en esta página web.

- [Configuration XML](https://config.office.com/deploymentsettings)

Al abrir el enlace nos encontramos con esta interfaz. En el punto 1 es el apartado donde seleccionaremos nuestras preferencias en cuanto a la configuración y el punto 2 es un resumen de lo que hemos seleccionado.

![](/imagenes/foto9.png)

Vamos con la configuración. En el apartado de **Productos y versiones** para este caso dejaremos esta configuración:

![](/imagenes/foto10.png)

En **Idioma** esta:

![](/imagenes/foto11.png)

En **Instalación** esta:
> Si hubiésemos querido ocultar la ventana de instalación por cualquier casual, tendríamos que haber desmarcado la casilla que dice "**Mostrar instalación al usuario**".

![](/imagenes/foto12.png)

En **Actualizar** esta:

![](/imagenes/foto13.png)

En **Licencias y activación** esta:

![](/imagenes/foto14.png)

En **General** esta:

![](/imagenes/foto15.png)

Y en **Preferencias de aplicación** esta:

![](/imagenes/foto16.png)

Ahora con todo configurado, exportaremos el archivo.

![](/imagenes/foto17.png)

Elegimos la siguiente opción y aceptamos.

![](/imagenes/foto18.png)

Aceptamos los términos de contrato de licencia y elegimos un nombre para nuestro archivo de configuración.

![](/imagenes/foto19.png)

Este es el archivo de configuración **.xml**.

![](/imagenes/foto20.png)

```xml
<Configuration ID="2a864b9c-b5f9-4b93-9f74-8392d12acbc1">
	<Add OfficeClientEdition="64" Channel="Current">
		<Product ID="O365ProPlusEEANoTeamsRetail">
			<Language ID="es-es"/>
			<ExcludeApp ID="Groove"/>
			<ExcludeApp ID="Lync"/>
			<ExcludeApp ID="OneDrive"/>
			<ExcludeApp ID="Bing"/>
		</Product>
	</Add>
	<Property Name="SharedComputerLicensing" Value="1"/>
	<Property Name="FORCEAPPSHUTDOWN" Value="FALSE"/>
	<Property Name="DeviceBasedLicensing" Value="0"/>
	<Property Name="SCLCacheOverride" Value="0"/>
	<Updates Enabled="TRUE"/>
	<RemoveMSI/>
	<Display Level="Full" AcceptEULA="TRUE"/>
</Configuration>
```

Ya tenemos dos de esos tres archivos que necesitamos.

![](/imagenes/foto21.png)

- [x] setup.exe
- [x] conf.xml
- [ ] Office

Ahora es momento de abrir una **cmd** como **administrador** para conseguir ese tercer fichero.

![](/imagenes/foto22.png)

Ahora nos dirigimos a la ruta donde se encuentran los dos archivos (**conf.xml** y el **setup.exe**).

![](/imagenes/foto23.png)

Ahora usamos el siguiente comando:

```cmd
setup /download conf.xml
```

Nos creará la carpeta **Office**, esperaremos hasta que acabe para introducir el siguiente comando.

![](/imagenes/foto24.png)

- [x] setup.exe
- [x] conf.xml
- [x] Office

Ahora con esto ya tenemos los 3 archivos que necesitábamos. Con el siguiente comando podríamos instalar o actualizar la aplicación.

```cmd
setup /configure conf.xml
```

![](/imagenes/foto25.png)

Solo quedaría esperar a que acabe de instalar ¡Y ya lo tendremos!

![](/imagenes/foto26.png)

![](/imagenes/foto27.png)

