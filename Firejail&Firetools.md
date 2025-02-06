<p style="text-align: justify;">

## PPS-Unidad1-Actividad4
# 🛠️ Configuración de un entorno controlado

Instalamos la aplicación **Firejail** y **Firetools** en una máquina virtual con el sistema operativo **Ubuntu 22.04**. Para ello, invocamos el siguiente comando:  

``
sudo apt install firejail firetools
``


Posteriormente, instalamos **Konsole**, ya que el terminal de GNOME no se ejecuta correctamente desde **Firejail** (o no hemos logrado lanzarlo).  

Para lanzar el entorno controlado, primero vamos a lanzar el **firetools** para controlar los procesos que lancemos desde **firejail**. Para lanzar **firetools** invocamos el comando:

``
sudo firetools
``

Se nos abrirá un pequeño panel de control alargado:

![1](/Imagenes/1.png)

Ahora, abrimos una terminal Konsole dentro del entorno aislado de Firejail con el siguiente comando:


``
sudo firejail --noprofile konsole
``

y se nos  abrirá una ventana con el terminal:

![2](/Imagenes/2.png)

Finalmente, ejecutamos el programa de la calculadora, previamente copiado de la actividad anterior:

``
python3 Calculadora.py
``

![3](/Imagenes/3.png)

Si nos vamos al panel de control del **Firetools**, podremos pinchar en el **PID** y visualizar información detallada sobre el proceso que se está ejecutando en la sandbox. Esto incluye el nombre del proceso, el usuario que lo ejecuta, el consumo de CPU y memoria, y otros detalles relevantes.

![4](/Imagenes/4.png)

Gracias a Firejail, hemos logrado ejecutar nuestra aplicación en un entorno controlado, aislando su ejecución del resto del sistema. Esto permite mayor seguridad y control sobre los procesos en ejecución.

</p>