# iaw-practica-11
Práctica WP-SCAN de la asignatura IAW de 2º de Asir.

> IES Celia Viñas (Almería) - Curso 2020/2021
Módulo: IAW - Implantación de Aplicaciones Web
Ciclo: CFGS Administración de Sistemas Informáticos en Red

**Introducción**
------------
En esta práctica vamos a realizar una auditoría de seguridad sobre nuestra instalación de WordPress con la que hemos estado trabajando en las prácticas anteriores.

La herramienta que vamos a utilizar para realizar la auditoría de nuestro sitio web WordPress es WPScan. Podemos instalarlo de varias maneras, pero en esta práctica usaremos un contenedor Docker.

**Instalar imagen Docker de WPScan**
------------
La imagen de WPScan está disponible en el siguiente enlace.
https://hub.docker.com/r/wpscanteam/wpscan/

El siguiente comando muestra una ayuda simple.
`docker run -it --rm wpscanteam/wpscan --help`

Versión detallada.
`docker run -it --rm wpscanteam/wpscan --hh`

**Auditoría de seguridad con WPScan**
------------
Hay varias auditorías que podemos realizar con WPScan. Veamos algunos casos y capturas de ejemplos realizados sobre un Wordpress desplegado con una AMI de Bitnami.

**Caso 1: Auditoría de plugin instalados.**
`docker run -it --rm wpscanteam/wpscan --url $URL  --enumerate p`
![](https://i.imgur.com/g8fIJDh.png)


**Caso 2: Análisis completo.**
`docker run -it --rm wpscanteam/wpscan --url $URL`
![](https://i.imgur.com/j2kwIbz.png)

**Auditoría de seguridad avanzada: uso de token**
------------
Registrándonos en la página web de WPScan y solicitando un token, podemos realizar una análisis en profundidad. Para conseguir dicho token es necesario registrarse con una cuenta de correo electrónico.

**Caso 3: Análisis en profundidad**
`docker run -it --rm wpscanteam/wpscan --url $URL --api-token 8pIlWnF2dxbgfvyQfDAUaV3T3iafo0uO1K8OPr2KKRM`
![](https://i.imgur.com/JvINFxE.png)


**Archivos en el repositorio**
------------
1.**README.md** Documentación.
  
2.**wpscan.sh** Un script pensado para automatizar la instalación de WP-scan en una máquina AWS ubuntu, así como los tres análisis propuestos en la práctica.

**Referencias**
------------
- Guía original para la práctica.
https://josejuansanchez.org/iaw/practica-11/index.html
- Guía de usuario de WPScan.
https://wpscan.com/wordpress-security-scanner
- Guía resumida de WPScan sobre Docker en entorno Ubuntu.
https://es.linux-console.net/?p=213


**Editor Markdown**
------------
- Markdown editor.
https://markdown-editor.github.io/
