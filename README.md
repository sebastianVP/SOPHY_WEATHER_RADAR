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
	

- Instalamos ahora Signal Chain la rama correspondiente a v3.0-WR

	$ cd  schainpy

	$ pwd
        
        /home/soporte/WR_SCHAIN_24APRIL2024/schain/schainpy
 
        $ pip install -e ../


	$ python
	
	(SOPHY_24APRIL2024) soporte@CI-91:~/WR_SCHAIN_24APRIL2024/schain/schainpy$ python
	
	Python 3.10.14 | packaged by conda-forge | (main, Mar 20 2024, 12:45:18) [GCC 12.3.0] on linux
	
	Type "help", "copyright", "credits" or "license" for more information.
	
	>>> import schainpy
	
	>>> exit()


- Buscamos ahora el script de procesamiento.
	
	$ cd /home/soporte/WR_SCHAIN_24APRIL2024/schain/schainpy/scripts

- Editamos el archivo indicando el PATH correspondiente, en nuestro caso.

	$ PATH = '/media/soporte/DATA/sophy'

- Instalacion de libreria Cartopy

	$ pip install cartopy

- Modificar el archivo jroIO_mira35c.py y 

        $ nano  /home/soporte/WR_SCHAIN_24APRIL2024/schain/schainpy/model/io/jroIO_mira35c.py

	Comentar la linea 12.

- Modificar el archivo jroproc_parameters.py

        $ nano /home/soporte/WR_SCHAIN_24APRIL2024/schain/schainpy/model/proc/jroproc_parameters.py

	Comentar la linea 22.


- Falta instalar la libreria digital_rf, para esto nos ubicamos en el siguiente diretorio.


	En la carpeta que definimos como directorio de trabajo ubicaremos el directorio para instalar digital_rf	

	$ cd /home/soporte/WR_SCHAIN_24APRIL2024

	$ git clone https://github.com/MITHaystack/digital_rf.git

	$ cd digital_rf

	Instalamos la libreria mako previamente.

	$ pip install mako 

	$ pip install pytz

	$ cmake ..

	$ make

	$ sudo make install

	$ sudo ldconfig

- Para probar toda la instalacion nos ubicamos en el siguiente directorio y ejecutamos el siguiente comando:

	$ cd /home/soporte/WR_SCHAIN_24APRIL2024/schain/schainpy/scripts
 
        $ python sophy_proc.py HYO_CC4_CC64_COMB@2022-12-27T00-00-32 --parameters Z  --plot --save --show --rmDC --label Z_04 --range 60 --start_time "22:00:00"
