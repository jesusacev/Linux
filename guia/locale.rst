Locale
=========

El locale nos permite realizar la configuración regional del sistema. Esta nos ayuda a especificar la configuración de idioma para las interfaces de usuario y los servicios que se ejecutan en su sistema. Sus funcionalidades más importantes es que los mensaje enviados por nuestro sistema operativo se enviarán en el idiama que lo configuremos, y si deseamos realizar la instalación de alguna aplicación de tercero, la misma se instalará en el idioma que tengamos configurado en nuestro locale.


- Con el comando locale, vemos la configuración actual::


	$ locale
	LANG=es_VE.UTF-8
	LANGUAGE=
	LC_CTYPE="es_VE.UTF-8"
	LC_NUMERIC="es_VE.UTF-8"
	LC_TIME="es_VE.UTF-8"
	LC_COLLATE="es_VE.UTF-8"
	LC_MONETARY="es_VE.UTF-8"
	LC_MESSAGES="es_VE.UTF-8"
	LC_PAPER="es_VE.UTF-8"
	LC_NAME="es_VE.UTF-8"
	LC_ADDRESS="es_VE.UTF-8"
	LC_TELEPHONE="es_VE.UTF-8"
	LC_MEASUREMENT="es_VE.UTF-8"
	LC_IDENTIFICATION="es_VE.UTF-8"
	LC_ALL=


- Si desea realizar una configuración regional diferente en su sistema, primero debe listar las localidades disponibles con el parámetro -a::


	# locale -a
	aa_DJ
	aa_DJ.iso88591
	aa_DJ.utf8
	aa_ER
	aa_ER@saaho
	aa_ER.utf8
	aa_ER.utf8@saaho
	aa_ET
	aa_ET.utf8
	af_ZA
	af_ZA.iso88591
	af_ZA.utf8
	am_ET
	am_ET.utf8
	an_ES
	an_ES.iso885915
	an_ES.utf8
	ar_AE
	ar_AE.iso88596
	ar_AE.utf8
	ar_BH
	ar_BH.iso88596
	ar_BH.utf8
	ar_DZ
	ar_DZ.iso88596
	ar_DZ.utf8
	ar_EG
	...


- La lista debe ser muy larga. Si desea filtrar las configuraciones regionales dependiendo de las iniciales del idioma que desee, puede hacerlo usando el siguiente comando::


	# locale -a | grep en_
	en_AG
	en_AG.utf8
	en_AU
	en_AU.iso88591
	en_AU.utf8
	en_BW
	en_BW.iso88591
	en_BW.utf8
	en_CA
	en_CA.iso88591
	en_CA.utf8
	en_DK
	en_DK.iso88591
	en_DK.utf8
	en_GB
	en_GB.iso88591
	en_GB.iso885915
	en_GB.utf8
	en_HK
	...

- Probamos la configuración regional del sistema operativo actual, ejecutando un comando y viendo el idioma en que nos retorna la información. En este caso usaremos el comando date::


	$ date
	jue ene 17 10:16:46 -04 2019


- Como podemos observar tanto el mes como el año nos lo retorna en español, debido a que esa es la configuración actual.


- Vuelvo a ejecutar el comando locale::

	$ locale
	LANG=es_VE.UTF-8
	LC_CTYPE="es_VE.UTF-8"
	LC_NUMERIC="es_VE.UTF-8"
	LC_TIME="es_VE.UTF-8"
	LC_COLLATE="es_VE.UTF-8"
	LC_MONETARY="es_VE.UTF-8"
	LC_MESSAGES="es_VE.UTF-8"
	LC_PAPER="es_VE.UTF-8"
	LC_NAME="es_VE.UTF-8"
	LC_ADDRESS="es_VE.UTF-8"
	LC_TELEPHONE="es_VE.UTF-8"
	LC_MEASUREMENT="es_VE.UTF-8"
	LC_IDENTIFICATION="es_VE.UTF-8"
	LC_ALL=


- Si observamos hay una variable llamada LC_ALL que si se modifica, entonces modificará todas las variables que empiezan por LC::

	
	$ export LC_ALL="en_US.utf8"


- Y si nuevamente ejecutamos el comando locale podemos observar como se modifican todas las variables que comienzar por LC con la nueva configuración regional::


	LANG=es_VE.UTF-8
	LC_CTYPE="en_US.utf8"
	LC_NUMERIC="en_US.utf8"
	LC_TIME="en_US.utf8"
	LC_COLLATE="en_US.utf8"
	LC_MONETARY="en_US.utf8"
	LC_MESSAGES="en_US.utf8"
	LC_PAPER="en_US.utf8"
	LC_NAME="en_US.utf8"
	LC_ADDRESS="en_US.utf8"
	LC_TELEPHONE="en_US.utf8"
	LC_MEASUREMENT="en_US.utf8"
	LC_IDENTIFICATION="en_US.utf8"
	LC_ALL=en_US.utf8


- Solo nos resta modificar la variable LANG::


	$ export LANG="en_US.utf8"
	$ locale
	LANG=en_US.utf8
	LC_CTYPE="en_US.utf8"
	LC_NUMERIC="en_US.utf8"
	LC_TIME="en_US.utf8"
	LC_COLLATE="en_US.utf8"
	LC_MONETARY="en_US.utf8"
	LC_MESSAGES="en_US.utf8"
	LC_PAPER="en_US.utf8"
	LC_NAME="en_US.utf8"
	LC_ADDRESS="en_US.utf8"
	LC_TELEPHONE="en_US.utf8"
	LC_MEASUREMENT="en_US.utf8"
	LC_IDENTIFICATION="en_US.utf8"
	LC_ALL=en_US.utf8


- Y ahora si volvemos a ejecutar el comando date, podemos ver que nos retorna la información en inglés::


	$ date
	Thu Jan 17 11:11:28 -04 2019


- Si queremos que el cambio permanezca al reiniciar el sistema operativo, debemos declarar las variables de entorno en el bash_profile en caso de hacerse para un usuario en específico, o en el /etc/profile para todos los usuarios del sistema.


- Dependiendo de la configuración regional del sistema podremos instalar aplicaciones de terceros en el idioma de nuestro gusto.

