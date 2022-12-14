# ESTRATEGIAS DE TRADING EN PYTHON - ALGOTRADING
#### Por SaraSTEM
>~ _Programar tus estrategias en Bolsa es fácil_ ~

## Descripción

En este repo encontrarás todas las estrategias de Trading que programo en Python, conocido como Trading Algorítmico. Están compuestas por:

- Descarga de datos
- Cuerpo de la estrategia
- Backtesting

Todo esto me permite hacer Trading de forma eficiente. Opero cada día con el broker XTB, con el que puedes [abrir una cuenta real grauita](https://www.xtb.com/es/abrir-cuenta-real?cxd=35312_576021&affid=35312&utm_source=affiliate&utm_medium=TextLink&utm_campaign=35312&utm_content=REAL%20GEO&utm_term=Spanish).

Si descargas el repo en tu ordenador, podrás testear cualquier parámetro como el producto, timeframe, capital, etc. en cualquiera de las estrategias. Para descargarlo, sigue los siguientes pasos:

## Instalación previa

Primero debemos descargar "Git" y "Python3" en nuestro ordenador. Los podemos encontrar en:

- __Git__: https://git-scm.com/downloads
- __Python3__: https://www.python.org/downloads/

Además, debemos tener un entorno de desarrollo o IDE para poder abrir los archivos escritos en Python. Yo recomiendo Visual Studio Code por su simplicidad de uso. Lo puedes descargar aquí:

- __Visual Studio Code__: https://code.visualstudio.com/download
## Visual Studio Code

Una vez descargado todo, abrimos Visual Studio Code. Pinchamos en "Terminal"->"Nuevo terminal".
Se abrirá un terminal en la parte baja donde escribiremos los siguientes comandos:

1. Entramos en la carpeta donde vamos a alojar el proyecto, por ejemplo el escritorio, y escribimos el siguiente código: 

`cd Desktop`

2. Una vez dentro, clonamos el proyecto escribiendo lo siguiente:

`git clone https://github.com/SaraStemTrading/algotrading_python.git`

3. Entramos en la carpeta especificada:

`cd algotrading_python`

4. Una vez dentro, desplegamos un entorno virtual del siguiente modo: 

`python -m venv env`

Si no funciona, probamos con:

`python3 -m venv env`

5. Activamos el entorno virtual "env":

En Windows: 

`env\Scripts\activate.bat`

En Mac: 

`source ./env/bin/activate`

Nos fijaremos que estamos dentro del entorno porque aparece __(env)__ en la línea de comandos.

6. Por útlimo, debemos instalar las dependencias para que el algoritmo funcione correctamente.
Esto lo hacemos con la ayuda del archivo __"requirements.txt"__. Para su instalación, escribimos: 

`pip install -r requirements.txt`

7. Finalmente, en el explorador de la izquierda en Visual Studio Code, podemos __abrir la carpeta__ donde hemos instalado el algoritmo (hemos usado el escritorio) para ver todos los archivos.

## Parámetros de las estrategias: archivo "variables_(nombre-de-la-estrategia).env" 

Una vez instalado todo lo anterior, y abierta la carpeta de la estrategia que queremos probar, vamos a reescribir el archivo __.env__ que viene dentro, fundamental para la correcta ejecución de nuestra estrategia, ya que tendrá todos los datos iniciales necesarios. En concreto, son los siguientes parámetros:

- __product__: Aquí debemos poner entre comillas el ticker del activo al que queremos aplicarle la estrategia y ver el backtesting. Tienes la lista completa en la web de Yahoo Finanzas, dentro del apartado Mercados, puedes buscar el producto que quieras: https://es.finance.yahoo.com.
- __period__: Esto solo se debe rellenar para datos intradía. Aquí debemos poner entre comillas el periodo de tiempo en el que queremos que nos muestre los datos, y debe inferior a 60 días.
Adjunto imagen con los periodos y timeframes disponibles:
![periodyf](https://www.sarastem.com/wp-content/uploads/2022/06/periodsYF.png)
- __interval__: Aquí podremos entre comillas el timeframe que queremos para testear nuestra estrategia.
- __period_bb__: Este es un ejemplo de períodos para un indicador concreto (en este caso las Bandas de Bollinger), pero debes añadir tantos períodos como indicadores tenga la estrategia, que ya viene por defecto en el documento.
- __risk_op__: Aquí ponemos el riesgo por operación que queremos asumir. Se pone en tantos por uno. Yo suelo trabajar con un riesgo del 2% sobre el capital en cada operación.
- __capital__: Aquí ponemos el capital con el que queremos testear nuestra estrategia.
- __commission__: Poner aquí la comisión a aplicar por operación, en tantos por uno. He usado 0,2% en cada operación.
- __margin__: Finalmente, ponemos el margen de apalancamiento, en tantos por uno. En mi caso he usado 1:50, es decir, 0,05.

## Funcionamiento del algoritmo
Una vez rellenados los apartados anteriores, podemos ejecutar el código del algoritmo desde Visual Studio Code y valorar los resultados obtenidos, que aparecerán en el propio terminal de la plataforma. Esto lo haremos escribiendo en el terminal:

`python3 (nombre-de-la-estrategia)_main.py`

**_Nota:_** Recuerda que para probar otros parámetros en esta estrategia, solo debes modificar el archivo ".env"

## Resultados
Los resultados de la estrategia (con  los parámetros indicados en el archivo ".env"), se pueden ver en el terminal de Visual Studio Code. En concreto, se arrojarán los siguientes datos:

- __Rentabilidad (%)__ 
- __Rentabilidad anualizada (%)__ -> Para poder comparar diferentes estrategias con diferentes horizontes y timeframes.
- __Número de operaciones__ -> Número total de operaciones realizadas por la estrategia.
- __Ratio de aciertos (%)__
- __Máximo drawdown (%)__ -> Peor racha de pérdidas.
- __Volatilidad (%)__
- __Ratio Sharpe, Ratio Sortino y Ratio Calmar__ -> Mejor es la estrategia cuanto mayor sean estos ratios. Serán 0 si la rentabilidad es negativa.
- __Factor de beneficio__ -> Mejor es la estrategia cuanto mayor sea este número. Lo ideal es superior a 1,5.
- __Calidad__ -> Mejor es la estrategia cuanto mayor sea este número. Lo ideal es superior a 1,6.
- __Benchmark__ -> Rentabilidad del benchmark en %. Lo ideal es batirlo.
- __Caída desde el pico__ -> Caída actual del equity en días.
- __Duración DD__ -> Duración en días del Drawdown. Con estos dos últimos datos es importante ver que los días son diferentes para comprobar que la estrategia no esté actualmente haciendo el Drawdown.


## Notas finales
Con toda esta información, puedes hacer pruebas y valorar tus propios resultados en cuestión de segundos. Si quieres ver vídeos explicativos de cada estrategia con trading en directo, [entra en mi página web](https://sarastem.com/estrategias-de-trading).

**¡Unete al Trading eficiente!**

Espero que te resulte de utilidad.

PD: Toda ayuda o sugerencia con el código es bienvenida, ya que mi background es financiero y no informático 😉

**_SaraSTEM | Trading Algorítmico_** 👩🏻‍💻
