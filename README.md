# REPOSITORIO DE INSTALACION DEL RADAR METEOROLOGICO SOPHY

- Primero podemos descargar esta guia para seguir el paso a paso y el proceso de instalacion, desde el repositorio de github:
 
  $ git clone git@github.com:sebastianVP/SOPHY_WEATHER_RADAR.git


- Necesitamos ahora  crear un entorno virtual, nos ubicamos en el directorio principal aqui crearemos el entorno virutal:

  $ pwd

  /home/soporte/

- Creamos el entorno virtual:

	$ conda create -n SOPHY_24APRIL2024 python=3.10


- Activamos el entorno virtual:

	$ conda activate SOPHY_24APRIL2024

-  Hacemos ahora la descarga del repositorio de Signal Chain, creamos una carpeta o directorio de trabajo, nos ubicamos en el folder original.

	$ cd  /home/soporte

	$ mkdir WR_SCHAIN_24APRIL2024

- En esta nueva carpeta clonamos el repositorio de Signal Chain:

	$ git clone http://intranet.igp.gob.pe:8082/schain

- Escogemos el branch correspondiente al desarrollo de software de SOPHY.

	$ cd schain

	$ git status 

	(SOPHY_24APRIL2024) soporte@CI-91:~/WR_SCHAIN_24APRIL2024/schain$ git status
	
        On branch master
	
        Your branch is up to date with 'origin/master'.
	
        nothing to commit, working tree clean

	$ git checkout v3.0-WR

	(SOPHY_24APRIL2024) soporte@CI-91:~/WR_SCHAIN_24APRIL2024/schain$ git checkout v3.0-WR 
	
        Switched to branch 'v3.0-WR'
	
        (SOPHY_24APRIL2024) soporte@CI-91:~/WR_SCHAIN_24APRIL2024/schain$ git status
	
        On branch v3.0-WR
	
        nothing to commit, working tree clean
	

