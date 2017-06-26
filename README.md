# pyqgis-awesome-linestring-generalizer

<<<<<<< HEAD
# 蚽dice
***

- [Introducci髇 y objetivos](#introducci髇-y-objetivos)
    - [Algoritmos](#algoritmos)
    - [Desarrollo del formulario PyQt4 mediante Qt Designer](#desarrollo-del-formulario-pyqt4-mediante-qt-designer)
- [Desarrollo de la pr醕tica](#desarrollo-de-la-pr醕tica)
- [Prueba y Resultados](#pruebas-y-resultados)
- [Conclusiones](#conclusiones)

# Introducci髇 y Objetivos
El proyecto final de la asignatura **`Desarrollo de aplicaciones SIG`** se ha centrado en las ideas listadas: 
* ``(13)`` **Aplicar el algoritmo de eliminaci髇 de [**`Douglas Peucker`**](https://es.wikipedia.org/wiki/Algoritmo_de_Ramer%E2%80%93Douglas%E2%80%93Peucker)**
* ``(14)`` **Aplicar el algoritmo de suavizamiento **`McMaster`** empleados en** generalizaci髇 cartogr醘ica.
Hemos decidido abordarlo desde **``QGIS (PyQGIS)``** principalmente por tratarse de software libre.

#### Algoritmos:
 - Algoritmo de eliminaci髇 de ***``Douglas-Peucker``***

![Animaci髇 Douglas Peucker](https://upload.wikimedia.org/wikipedia/commons/3/30/Douglas-Peucker_animated.gif)

El algoritmo de Douglas-Peucker se usa para reducir el n鷐ero de puntos utilizados en la aproximaci髇 de una curva. El objetivo del algoritmo es, dada una curva compuesta por segmentos, encontrar una curva similar aproximada con menos puntos. El algoritmo define un par醡etro basado en la m醲ima distancia entre la curva original y la simplificada.
El algoritmo seguido ser韆 el siguiente:

```javascript
function DouglasPeucker(PointList[], epsilon)
    // Busca el punto con la distancia m醲ima
=======
# 脥ndice
***

- [Introducci贸n y objetivos](#introducci贸n-y-objetivos)
    - [Algoritmos](#algoritmos)
    - [Desarrollo del formulario PyQt4 mediante Qt Designer](#desarrollo-del-formulario-pyqt4-mediante-qt-designer)
- [Desarrollo de la pr谩ctica](#desarrollo-de-la-pr谩ctica)
- [Prueba y Resultados](#pruebas-y-resultados)
- [Conclusiones](#conclusiones)

# Introducci贸n y Objetivos
El proyecto final de la asignatura **`Desarrollo de aplicaciones SIG`** se ha centrado en las ideas listadas: 
* ``(13)`` **Aplicar el algoritmo de eliminaci贸n de [**`Douglas Peucker`**](https://es.wikipedia.org/wiki/Algoritmo_de_Ramer%E2%80%93Douglas%E2%80%93Peucker)**
* ``(14)`` **Aplicar el algoritmo de suavizamiento **`McMaster`** empleados en** generalizaci贸n cartogr谩fica.
Hemos decidido abordarlo desde **``QGIS (PyQGIS)``** principalmente por tratarse de software libre.

#### Algoritmos:
 - Algoritmo de eliminaci贸n de ***``Douglas-Peucker``***

![Animaci贸n Douglas Peucker](https://upload.wikimedia.org/wikipedia/commons/3/30/Douglas-Peucker_animated.gif)

El algoritmo de Douglas-Peucker se usa para reducir el n煤mero de puntos utilizados en la aproximaci贸n de una curva. El objetivo del algoritmo es, dada una curva compuesta por segmentos, encontrar una curva similar aproximada con menos puntos. El algoritmo define un par谩metro basado en la m谩xima distancia entre la curva original y la simplificada.
El algoritmo seguido ser铆a el siguiente:

```javascript
function DouglasPeucker(PointList[], epsilon)
    // Busca el punto con la distancia m谩xima
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
    dmax = 0
    index = 0
    end = length(PointList)
    for i = 1 to ( end - 1) {
        d = shortestDistanceToSegment(PointList[i], Line(PointList[1], PointList[end])) 
        if ( d > dmax ) {
            index = i
            dmax = d
        }
    }
    // Si la distancia es mayor que epsilon, simplificar recursivamente
    if ( dmax > epsilon ) {
        // Llamada recursiva
        recResults1[] = DouglasPeucker(PointList[1...index], epsilon)
        recResults2[] = DouglasPeucker(PointList[index...end], epsilon)
 
<<<<<<< HEAD
        // Construcci髇 de la lista resultado
=======
        // Construcci贸n de la lista resultado
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        ResultList[] = {recResults1[1...end-1] recResults2[1...end]}
    } else {
        ResultList[] = {PointList[1], PointList[end]}
    }
    // Devolver el resultado
    return ResultList[]
end
```

<<<<<<< HEAD
En resumen, el algoritmo construye una linea desde el primer hasta el 鷏timo punto de la linea y busca el vertice con una mayor distancia (que forme un 醤gulo recto) al segmento y lo agrega si est� a una distancia mayor a epsilon. Con los dos segmentos formados se repetir韆 el proceso hasta no haber puntos o que estos no superen el umbral epsilon. Es un proceso recursivo d髇de la nueva curva es generada a partir de los puntos que han permanecido tras aplicar el algoritmo.

**Algoritmo de suavizado de McMaster**
Tambi閚 conocido como algoritmo de deslizamiento de McMaster. Este algoritmo dejar� fijos el primer y 鷏timo punto de la l韓ea y calcular� la nueva posici髇 (posici髇 media) de los dem醩 puntos a partir de sus coordenadas y las de sus vecinos.
Tiene un par醡etro de entrada que es el n鷐ero de vertices con los que calcular� la media de las coordenadas de cada uno, por lo que este deber� ser un n鷐ero impar (mismo n鷐ero de vecinos a cada lado del v閞tice y el propio v閞tice). Los v閞tices que no entren en el vecindario de suavizado se quedar醤 como estaban.
=======
En resumen, el algoritmo construye una linea desde el primer hasta el 煤ltimo punto de la linea y busca el vertice con una mayor distancia (que forme un 谩ngulo recto) al segmento y lo agrega si est谩 a una distancia mayor a epsilon. Con los dos segmentos formados se repetir铆a el proceso hasta no haber puntos o que estos no superen el umbral epsilon. Es un proceso recursivo d贸nde la nueva curva es generada a partir de los puntos que han permanecido tras aplicar el algoritmo.

**Algoritmo de suavizado de McMaster**
Tambi茅n conocido como algoritmo de deslizamiento de McMaster. Este algoritmo dejar谩 fijos el primer y 煤ltimo punto de la l铆nea y calcular谩 la nueva posici贸n (posici贸n media) de los dem谩s puntos a partir de sus coordenadas y las de sus vecinos.
Tiene un par谩metro de entrada que es el n煤mero de vertices con los que calcular谩 la media de las coordenadas de cada uno, por lo que este deber谩 ser un n煤mero impar (mismo n煤mero de vecinos a cada lado del v茅rtice y el propio v茅rtice). Los v茅rtices que no entren en el vecindario de suavizado se quedar谩n como estaban.
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449

El algoritmo seguido es el siguiente:

```javascript
function McMaster(PointList[], nu)
    half_nu = int(nu/2) # nu = 3 -> half_nu = 1
    end = length(PointList)
    x0, y0 = PointList[0]
    x1, y1 = PointList[-1]
    smooth_points = []
    smooth_points.append([x0,y0])
    
    for i = half_nu to (end - half_nu){
        Xactual, Yactual = PointList[i]
        for j = -half_nu to half_nu{
            x, y +=  PointList[i + j]
        }
        mediax, mediay = x/nu, y/nu
        smooth_points.append(mediax, mediay)
    }
    return smooth_points[]
```

<<<<<<< HEAD
Decir que los algoritmos planteados est醤 escritos en pseudoc骴igo y no responden a ning鷑 lenguaje de programaci髇 en s�.
Con este algoritmo lo que se conseguir� es un suavizado de las curvas por lo que 閟tas no ser醤 tan acentuadas.

# Desarrollo del formulario PyQt4 mediante Qt Designer

# Desarrollo de la pr醕tica
En primer lugar hemos utilizado ``uic.py`` para convertir el archivo ``.ui`` en un archivo ``.py`` que usaremos como archivo del proyecto.

Hemos a馻dido en la parte superior del archivo los imports necesarios para realizar nuestro proyecto:
=======
Decir que los algoritmos planteados est谩n escritos en pseudoc贸digo y no responden a ning煤n lenguaje de programaci贸n en s铆.
Con este algoritmo lo que se conseguir谩 es un suavizado de las curvas por lo que 茅stas no ser谩n tan acentuadas.

# Desarrollo del formulario PyQt4 mediante Qt Designer

# Desarrollo de la pr谩ctica
En primer lugar hemos utilizado ``uic.py`` para convertir el archivo ``.ui`` en un archivo ``.py`` que usaremos como archivo del proyecto.

Hemos a帽adido en la parte superior del archivo los imports necesarios para realizar nuestro proyecto:
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449

```python
# -*- coding: utf-8 -*-
import math
import sys
import os
from PyQt4 import QtCore, QtGui
from qgis.core import *
from qgis.gui import *
import qgis
from PyQt4.QtCore import SIGNAL, Qt
from PyQt4.QtGui import QFileDialog, QMainWindow, QMessageBox
from functools import partial
```

<<<<<<< HEAD
Despu閟 de los imports tomamos una referencia del **registro** de ``QGIS``:
=======
Despu茅s de los imports tomamos una referencia del **registro** de ``QGIS``:
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449

```python
registry = QgsMapLayerRegistry.instance()
```

<<<<<<< HEAD
A continuaci髇 se muestra el c骴igo del formulario. Mostraremos solo las partes del c骴igo escritas por nosotros y evitaremos poner el c骴igo generado por uic.
=======
A continuaci贸n se muestra el c贸digo del formulario. Mostraremos solo las partes del c贸digo escritas por nosotros y evitaremos poner el c贸digo generado por uic.
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449

```python
# Clase MainWindow
class MainWindow(QMainWindow):

    # Constructor
    def __init__(self):
        QMainWindow.__init__(self)

        # Capa original
        self.original = None

<<<<<<< HEAD
        # Capa para mostrar la previsualizaci髇
=======
        # Capa para mostrar la previsualizaci贸n
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        self.preview = None

        # Carpeta de salida de datos
        self.folder= None

        # Objeto de la clase GeneraLine (para aplicar algoritmos sobre la capa)
        self.simplify = GeneraLine()

        # namespace Algorithms (Contiene los nombres de los algorritmos)
        self.Algorithms = GeneraLine.Algorithms

        # Inicializamos el formulario
        self.__init_ui()

        # Conectamos los eventos con los funciones

<<<<<<< HEAD
        # Bot髇 previsualizar algoritmo Douglas Peucker
        self.btn_prev_dp.clicked.connect( partial(self.__showPreviewCanvas, self.Algorithms.DOUGLAS_PEUCKER) )

        # Bot髇 previsualizar algoritmo McMaster
        self.btn_prev_mcm.clicked.connect( partial(self.__showPreviewCanvas, self.Algorithms.MC_MASTER) )

        # Bot髇 cargar SHP
        self.btn_load_shp.clicked.connect(self.__openDialog)

        # Bot髇 abrir di醠ogo para seleccionar carpeta de salida
=======
        # Bot贸n previsualizar algoritmo Douglas Peucker
        self.btn_prev_dp.clicked.connect( partial(self.__showPreviewCanvas, self.Algorithms.DOUGLAS_PEUCKER) )

        # Bot贸n previsualizar algoritmo McMaster
        self.btn_prev_mcm.clicked.connect( partial(self.__showPreviewCanvas, self.Algorithms.MC_MASTER) )

        # Bot贸n cargar SHP
        self.btn_load_shp.clicked.connect(self.__openDialog)

        # Bot贸n abrir di谩logo para seleccionar carpeta de salida
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        self.btn_sal.clicked.connect(self.__openDialog_folder)

        # Control de escala - Cuando se modifique la escala en el widget
        self.scaleControl.scaleChanged.connect(self.on_scale_changed)

        # Cuando cambia la escala en el canvas
        self.canvas.scaleChanged.connect(self.on_canvas_scale_changed)

        # Checkbox Algoritmo McMaster
        self.cb_dp.stateChanged.connect(self.activaGuardar)

        # Checkbox Algoritmo Douglas Peucker
        self.cb_mcm.stateChanged.connect(self.activaGuardar)

<<<<<<< HEAD
        # Bot髇 Guardar
=======
        # Bot贸n Guardar
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        self.btn_do.clicked.connect(self.guardaSHP)

    '''
    @method: guardaSHP
    @brief: Guarda los resultados en shapefile en el directorio de salida
            dependiendo de los checbox marcados
    '''
    def guardaSHP(self):

<<<<<<< HEAD
        # Si el checbox del algoritmo douglas peucker est� marcado
=======
        # Si el checbox del algoritmo douglas peucker est谩 marcado
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        if self.cb_dp.isChecked():

            # Aplicamos el algoritmo
            self.simplify.applyAlgorithm(self.Algorithms.DOUGLAS_PEUCKER, self.spn_dp.value())

            # Obtenemos el string con la ruta de salida del shapefile
            filepath = os.path.join( self.folder
                                    , '{}_{}_{}_{}'.format(
                                            'DOUGLAS_PEUCKER'
                                            , self.spn_dp.value()
                                            , self.simplify.layer.name()
                                            , '.shp') )

            # Guardamos la capa
            QgsVectorFileWriter.writeAsVectorFormat(self.simplify.layer_salida, filepath, 'utf-8', None, "ESRI Shapefile")

<<<<<<< HEAD
        # Si el checbox del algoritmo McMaster est� marcado
=======
        # Si el checbox del algoritmo McMaster est谩 marcado
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        if self.cb_mcm.isChecked():

            # Aplicamos el algoritmo
            self.simplify.applyAlgorithm(self.Algorithms.MC_MASTER, self.spn_mcm.value())

            # Obtenemos el string con la ruta de salida del shapefile
            filepath = os.path.join( self.folder
                                    , '{}_{}_{}_{}'.format(
                                            'MC_MASTER'
                                            , self.spn_mcm.value()
                                            , self.simplify.layer.name()
                                            , '.shp') )

            # Guardamos la capa
            QgsVectorFileWriter.writeAsVectorFormat(self.simplify.layer_salida, filepath, 'utf-8', None, "ESRI Shapefile")

<<<<<<< HEAD
        # Mostramos un mensaje de informaci髇
        QMessageBox.information(None, u'蓌ito', u'Guardado con 閤ito en : '+ str(self.folder))

    '''
    @method: activaGuardar
    @brief: Activa el bot髇 de guardar dependiendo de los checbox marcados
=======
        # Mostramos un mensaje de informaci贸n
        QMessageBox.information(None, u'脡xito', u'Guardado con 茅xito en : '+ str(self.folder))

    '''
    @method: activaGuardar
    @brief: Activa el bot贸n de guardar dependiendo de los checbox marcados
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
            y si se ha especificado carpeta de salida
    '''
    def activaGuardar(self):

<<<<<<< HEAD
        # Si el checbox de el algoritmo Douglas Peucker est� marcado
        if self.cb_dp.isChecked() or self.cb_mcm.isChecked():
            # Si se ha especificado carpeta de salida
            if self.folder:
                # Activamos el bot髇 de guardar
                self.btn_do.setEnabled(True)

        # Si ning鷑 checbox est� marcado
        else:
            # Desactivamos el bot髇 de guardar
=======
        # Si el checbox de el algoritmo Douglas Peucker est谩 marcado
        if self.cb_dp.isChecked() or self.cb_mcm.isChecked():
            # Si se ha especificado carpeta de salida
            if self.folder:
                # Activamos el bot贸n de guardar
                self.btn_do.setEnabled(True)

        # Si ning煤n checbox est谩 marcado
        else:
            # Desactivamos el bot贸n de guardar
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
            self.btn_do.setEnabled(False)


    '''
    @method: __showPreviewCanvas
<<<<<<< HEAD
    @brief: Muestra la previsualizaci髇 de aplicar el algoritmo con el par醡etro
=======
    @brief: Muestra la previsualizaci贸n de aplicar el algoritmo con el par谩metro
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
            seleccionado
    @param: algorithm - nombre del algoritmo a aplicar
    '''
    def __showPreviewCanvas(self, algorithm) :

        # Si el algoritmo seleccionado es Douglas-Peucker
        if algorithm == self.Algorithms.DOUGLAS_PEUCKER :
<<<<<<< HEAD
            # El parametro ser� el espec韋icado en el spiner de Douglas-Peucker
            param = self.spn_dp.value()
        else :
            # El parametro ser� el espec韋icado en el spiner de McMaster
            param = self.spn_mcm.value()

        # Aplicamos el algoritmo con el par醡etro introducido sobre la capa
=======
            # El parametro ser谩 el espec铆ficado en el spiner de Douglas-Peucker
            param = self.spn_dp.value()
        else :
            # El parametro ser谩 el espec铆ficado en el spiner de McMaster
            param = self.spn_mcm.value()

        # Aplicamos el algoritmo con el par谩metro introducido sobre la capa
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        self.simplify.applyAlgorithm(algorithm, param)

        # Se activa el checkbox de suavizado
        self.cb_suav.setEnabled(True)

        # El checkbox de suavizado se pone en checked (ya que la capa se encuentra visible)
        self.cb_suav.setCheckState(Qt.Checked)

        # Asignamos a la capa preview un objeto de la clase QgsMapCanvasLayer a partir de
        # la capa de salida almacenada en el objeto de la clase GeneraLine
        self.preview = QgsMapCanvasLayer(self.simplify.layer_salida)

<<<<<<< HEAD
        # Conectamos al checkbox la funci髇 para cambiar la visualizaci髇 de la capa generalizada
        self.cb_suav.clicked.connect( partial(self.toggleCanvasVisibilityLayer, self.preview) )

        # A馻dimos al canvas las dos capas (se visualizan)
=======
        # Conectamos al checkbox la funci贸n para cambiar la visualizaci贸n de la capa generalizada
        self.cb_suav.clicked.connect( partial(self.toggleCanvasVisibilityLayer, self.preview) )

        # A帽adimos al canvas las dos capas (se visualizan)
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        self.canvas.setLayerSet([ self.original, self.preview ])


    '''
    @method: __openDialog
<<<<<<< HEAD
    @brief: Muestra un di醠ogo para seleccionar el archivo SHP
=======
    @brief: Muestra un di谩logo para seleccionar el archivo SHP
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
    '''
    def __openDialog(self):
        # Se crea un objeto del tipo QFileDialog
        dlg = QFileDialog()

        # Busca por archivos existentes en el sistema
        dlg.setFileMode(QFileDialog.ExistingFile)
<<<<<<< HEAD
        # Solo mostrar archivos con extensi髇 shp
=======
        # Solo mostrar archivos con extensi贸n shp
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        dlg.setFilter("shapefile (*.shp)")

        # Cuando devuelva True ( Cuando se haya seleccionado la carpeta de salida )
        if dlg.exec_():
            # Obtenemos la ruta del archivo
            filepath = map(str, list(dlg.selectedFiles()))[0]
<<<<<<< HEAD
            # Llamamos a la funci髇 __addLayer con la ruta del archivo para a馻dirlo como capa
=======
            # Llamamos a la funci贸n __addLayer con la ruta del archivo para a帽adirlo como capa
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
            self.__addLayer(filepath)


    '''
    @method: __openDialog_folder
<<<<<<< HEAD
    @brief: Muestra un di醠ogo para seleccionar la carpeta de salida
=======
    @brief: Muestra un di谩logo para seleccionar la carpeta de salida
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
    '''
    def __openDialog_folder(self):
        # Crea un dialogo para seleccionar un directorio y devuelve la ruta
        self.folder = QFileDialog().getExistingDirectory()

        # Muestra en el label la ruta de la carpeta de salida
        self.label_selected_folder.setText(self.folder)

<<<<<<< HEAD
        # Llamamos a la funci髇 activaGuardar
=======
        # Llamamos a la funci贸n activaGuardar
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        self.activaGuardar()

    '''
    @method: __addLayer
    @brief: Crea las capas de entrada y salida a partir del path
    @param: path - ruta de la capa de entrada
    '''
    def __addLayer(self, path):

        # Objeto de la clase QgsVectorLayer ( capa de entrada )
        layer = QgsVectorLayer(path, os.path.basename(path), "ogr")

        # Si la capa no es de tipo lineString
        if not layer.geometryType()==1:
<<<<<<< HEAD
            # Devuelve un mensaje de aviso y no contin鷄
=======
            # Devuelve un mensaje de aviso y no contin煤a
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
            QMessageBox.information(None,'Warning', 'No se trata de una capa LineString')
            return

        # Creamos un objeto de tipo QgsMapCanvasLayer
<<<<<<< HEAD
        # De esta forma podremos activar o desactivar la visualizaci髇 a partir de la capa
=======
        # De esta forma podremos activar o desactivar la visualizaci贸n a partir de la capa
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        # y no utilizando la clase QgsLegend
        self.original = QgsMapCanvasLayer(layer)

        # Asignamos la capa al objeto de la clase GeneraLine ( capa de entrada )
        self.simplify.setLayer(layer)

<<<<<<< HEAD
        # Ponemos al canvas la extensi髇 de la capa de entrada
        self.canvas.setExtent(layer.extent())

        # A馻dimos al canvas la capa original
        self.canvas.setLayerSet([self.original])

        # Le aplicamos simbolog韆
=======
        # Ponemos al canvas la extensi贸n de la capa de entrada
        self.canvas.setExtent(layer.extent())

        # A帽adimos al canvas la capa original
        self.canvas.setLayerSet([self.original])

        # Le aplicamos simbolog铆a
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        symbols = layer.rendererV2().symbols()
        symbol = symbols[0]
        symbol.setColor(QtGui.QColor.fromRgb(204, 51, 51))

        # Activamos botones y checkbox para que se pueda interactuar

<<<<<<< HEAD
        # Bot髇 previsualizar la generalizaci髇 de Douglas-Peucker
        self.btn_prev_dp.setEnabled(True)
        # Bot髇 previsualizar la generalizaci髇 de McMaster
        self.btn_prev_mcm.setEnabled(True)
        # Se activa el checkbox de visualizaci髇 de la capa de entrada
=======
        # Bot贸n previsualizar la generalizaci贸n de Douglas-Peucker
        self.btn_prev_dp.setEnabled(True)
        # Bot贸n previsualizar la generalizaci贸n de McMaster
        self.btn_prev_mcm.setEnabled(True)
        # Se activa el checkbox de visualizaci贸n de la capa de entrada
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        self.cb_ori.setEnabled(True)
        # Se marca como checked
        self.cb_ori.setCheckState(Qt.Checked)
        # Se activa el checkbox del algoritmo Douglas-Peucker
        self.cb_dp.setEnabled(True)
        # Se activa el checkbox del algoritmo McMaster
        self.cb_mcm.setEnabled(True)
<<<<<<< HEAD
        # Se activa el bot髇 de zoom extensi髇
=======
        # Se activa el bot贸n de zoom extensi贸n
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        self.btn_zoom.setEnabled(True)
        # Se activa el spiner de Douglas-Peucker
        self.spn_dp.setEnabled(True)
        # Se activa el spiner de McMaster
        self.spn_mcm.setEnabled(True)
        # Se activa el control de escala
        self.scaleControl.setEnabled(True)
        # Mostramos en el label el nombre de la capa seleccionada
        self.label_shp_path.setText(layer.name())

        # Ponemos como sistema de referencia del canvas el de la capa de entrada
        self.canvas.mapRenderer().setDestinationCrs(QgsCoordinateReferenceSystem(layer.crs().authid()))

<<<<<<< HEAD
        # Conectamos al checkbox de visualizaci髇 de la capa de entrada a su funci髇
        self.cb_ori.toggled.connect( partial(self.toggleCanvasVisibilityLayer, self.original) )

        # Conecta el bot髇 de zoom con su funci髇
=======
        # Conectamos al checkbox de visualizaci贸n de la capa de entrada a su funci贸n
        self.cb_ori.toggled.connect( partial(self.toggleCanvasVisibilityLayer, self.original) )

        # Conecta el bot贸n de zoom con su funci贸n
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        self.btn_zoom.clicked.connect( partial( self.zoomExt, layer ) )


    '''
    @method: zoomExt
<<<<<<< HEAD
    @brief: Realiza un zoom extensi髇 de la capa de entrada en el canvas
    @param: layer - capa de visualizaci髇
    '''
    def zoomExt(self,layer):
        # Asignamos la extensi髇 del canvas a la extensi髇 de la capa
=======
    @brief: Realiza un zoom extensi贸n de la capa de entrada en el canvas
    @param: layer - capa de visualizaci贸n
    '''
    def zoomExt(self,layer):
        # Asignamos la extensi贸n del canvas a la extensi贸n de la capa
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        self.canvas.setExtent(layer.extent())
        # Refrescamos el canvas
        self.canvas.refresh()

    '''
    @method: toggleCanvasVisibilityLayer
<<<<<<< HEAD
    @brief: Se visualiza o no la capa en funci髇 del estado de la capa
    @param: layer - capa de visualizaci髇
    '''
    def toggleCanvasVisibilityLayer(self, layer):
        # Boolean del estado de visualizaci髇 la capa
        visibility = layer.isVisible()

        # Asignamos la visualizaci髇 de la capa a lo contrario que hab韆 antes
        layer.setVisible(not visibility)

        # Hay que volver a a馻dir las capas para que se muestren
=======
    @brief: Se visualiza o no la capa en funci贸n del estado de la capa
    @param: layer - capa de visualizaci贸n
    '''
    def toggleCanvasVisibilityLayer(self, layer):
        # Boolean del estado de visualizaci贸n la capa
        visibility = layer.isVisible()

        # Asignamos la visualizaci贸n de la capa a lo contrario que hab铆a antes
        layer.setVisible(not visibility)

        # Hay que volver a a帽adir las capas para que se muestren
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        layerSet = [ l for l in [self.original, self.preview] if l]
        self.canvas.setLayerSet(layerSet)

        # Refrescamos el canvas
        self.canvas.refresh()

    '''
    @method: on_scale_changed
    @brief: Se ejecuta cuando cambia la escala del QgsScaleWidget.
            Modifica la escala del canvas.
    '''
    def on_scale_changed(self):

        #iface.mapCanvas().zoomScale(1 / (self.scaleControl.scale() if not self.scaleControl.scale() == 0 else 1 ) )

<<<<<<< HEAD
        # Modificamos la escala del canvas en funci髇 del QgsScaleWidget
=======
        # Modificamos la escala del canvas en funci贸n del QgsScaleWidget
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        self.canvas.zoomScale(1 / (self.scaleControl.scale() if not self.scaleControl.scale() == 0 else 1 ) )

        # Refrescamos el canvas
        self.canvas.refresh()

    '''
    @method: on_canvas_scale_changed
    @brief: Se ejecuta cuando cambia la escala del canvas.
            Modifica la escala del QgsScaleWidget.
    '''
    def on_canvas_scale_changed(self, scale):
<<<<<<< HEAD
        # Modifica la escala del QgsScaleWidget en funci髇 de la escala del canvas
=======
        # Modifica la escala del QgsScaleWidget en funci贸n de la escala del canvas
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        self.scaleControl.setScale(1 / scale)


    '''
    @method: __init_ui
    @brief: Inicializa los componentes del formulario. Obtenido de uic.
<<<<<<< HEAD
            A馻di閚dole componente de QGIS: Canvas, QgsScaleWidget
=======
            A帽adi茅ndole componente de QGIS: Canvas, QgsScaleWidget
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
    '''
    def __init_ui(self):
        # solo hemos tenido que crear el canvas y el QgsScaleWidget
        self.canvas_container = QtGui.QHBoxLayout()
        self.canvas_container.setObjectName(_fromUtf8("canvas_container"))

        self.canvas = QgsMapCanvas()
        self.canvas_container.addWidget( self.canvas )

        self.scaleControl = QgsScaleWidget()
        self.scaleControl.setMapCanvas(self.canvas)
        self.scaleControl.setScaleFromCanvas()
        self.scaleControl.setEnabled(False)
        self.map_controls_container.addWidget( self.scaleControl )

        self.verticalLayout_3.addLayout(self.map_controls_container)

        self.verticalLayout_3.addLayout(self.canvas_container)
```

<<<<<<< HEAD
A continuaci髇 mostramos la clase **``GeneraLine``** que es la encargada de realizar los algoritmos.
=======
A continuaci贸n mostramos la clase **``GeneraLine``** que es la encargada de realizar los algoritmos.
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449

```python

'''
@class: Algorithms
@brief: namespace para los algoritmos
'''
class Algorithms:
    MC_MASTER = 'MC_MASTER'
    DOUGLAS_PEUCKER = 'DOUGLAS_PEUCKER'

'''
@class: GeneraLine
<<<<<<< HEAD
@brief: Clase que servir� para ejecutar los algoritmos
        de suavizado y reducci髇 de puntos sobre una capa de L韓eas
=======
@brief: Clase que servir谩 para ejecutar los algoritmos
        de suavizado y reducci贸n de puntos sobre una capa de L铆neas
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
@param: layer - Capa de entrada
'''
class GeneraLine:

<<<<<<< HEAD
    # Variable de clase est醫ica que almacena la clase Algoritmos
=======
    # Variable de clase est谩tica que almacena la clase Algoritmos
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
    Algorithms = Algorithms

    # Lista con los algoritmos posibles
    algorithms = [Algorithms.MC_MASTER, Algorithms.DOUGLAS_PEUCKER]

    # Constructor
    def __init__(self, layer = None):

        # Variable de clase self.layer_salida
<<<<<<< HEAD
        # Almacenar� las features de salida
=======
        # Almacenar谩 las features de salida
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        self.layer_salida = None

        # Si se le pasa layer al constructor
        if layer :
            # Asignamos la capa como variable de clase
            self.setLayer(layer)

    '''
    @method: setLayer
    @brief: Asignamos como variable de clase la capa que se le pasa
            y creamos la capa de salida en memoria (layer_salida)
<<<<<<< HEAD
            con los par醡etros de la capa de entrada (crs, nombre, ...)
=======
            con los par谩metros de la capa de entrada (crs, nombre, ...)
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
    '''
    def setLayer(self, layer):
        # Asignamos la capa
        self.layer = layer

        # Obtenemos el EPSG
        self.__crs = layer.crs().authid()

        # Creamos la capa layer_salida - se guarda en memoria
        self.layer_salida = QgsVectorLayer( 'LineString?crs={}'.format(self.__crs)
                                        , 'generalizacion_{}'.format(self.layer.name())
                                        , 'memory' )

<<<<<<< HEAD
        # Cambiamos la simbolog韆
=======
        # Cambiamos la simbolog铆a
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        symbols = self.layer_salida.rendererV2().symbols()
        symbol = symbols[0]
        # Cambiamos el color de la capa de salida a un tono azulado
        symbol.setColor(QtGui.QColor.fromRgb(102, 102, 255))

<<<<<<< HEAD
        # A馻dimos las capas al registro de QGIS
=======
        # A帽adimos las capas al registro de QGIS
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        registry.addMapLayer(self.layer)
        registry.addMapLayer(self.layer_salida)


    '''
    @method: applyAlgorithm
    @brief: Aplica el algoritmo sobre la capa de entrada y guarda el resultado
            en la capa de salida

    @param: name - nombre del algoritmo a aplicar (namespace Algorithms)
    '''
    def applyAlgorithm(self, name, param):

        # Comprobamos el nombre del algoritmo
        if name not in self.algorithms : return None

<<<<<<< HEAD
        # Comenzamos la edici髇 sobre la capa de salida
        with edit(self.layer_salida):
            # Metemos la l骻ica dentro de un bloque try-except
=======
        # Comenzamos la edici贸n sobre la capa de salida
        with edit(self.layer_salida):
            # Metemos la l贸gica dentro de un bloque try-except
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
            try :
                # Eliminamos las features que puedan haber
                # en la capa de salida (de proceso anteriores)
                listOfIds = [feat.id() for feat in self.layer_salida.getFeatures()]
                self.layer_salida.deleteFeatures( listOfIds )

                # Recorreremos todas las features de la capa de entrada
                for feature in self.layer.getFeatures():

<<<<<<< HEAD
                    # Obtenemos una referencia de la geometr韆
                    geom = feature.geometry()

                    # Creamos una feature temporal
                    # Servir� para recorrer geometr韆s multiparte
                    temp_feature = QgsFeature()

                    # Comprobamos la geomtr韆
                    if not geom : continue

                    # Se crea un nuevo feature (temporal)
                    # Servir� para crear la feature de la capa de salida
                    f = QgsFeature()


                    # Si la geometr韆 es multiparte (MULTILINESTRING)
=======
                    # Obtenemos una referencia de la geometr铆a
                    geom = feature.geometry()

                    # Creamos una feature temporal
                    # Servir谩 para recorrer geometr铆as multiparte
                    temp_feature = QgsFeature()

                    # Comprobamos la geomtr铆a
                    if not geom : continue

                    # Se crea un nuevo feature (temporal)
                    # Servir谩 para crear la feature de la capa de salida
                    f = QgsFeature()


                    # Si la geometr铆a es multiparte (MULTILINESTRING)
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
                    if geom.isMultipart():
                        # Recorremos cada LineString (geom) dentro del MultiLineString
                        for geom_ in geom.asGeometryCollection():

<<<<<<< HEAD
                            # Asignamos la geometr韆 a la feature temporal
                            temp_feature.setGeometry(geom_)

                            # Extraemos los puntos de la geomtr韆
                            points = self.__extractPoints(temp_feature)

                            # Ejecutamos el algoritmo pertinente
                            # sobre los puntos extraidos de la geometr韆 que estamos recorriendo
=======
                            # Asignamos la geometr铆a a la feature temporal
                            temp_feature.setGeometry(geom_)

                            # Extraemos los puntos de la geomtr铆a
                            points = self.__extractPoints(temp_feature)

                            # Ejecutamos el algoritmo pertinente
                            # sobre los puntos extraidos de la geometr铆a que estamos recorriendo
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
                            if name == self.Algorithms.MC_MASTER:
                                resultPoints = [ QgsPoint(*x) for x in self.__mcMaster(points, param) ] #if len(x) > 1 ]
                            else :
                                resultPoints = [ QgsPoint(*x) for x in self.__douglasPeucker(points, param) ] #if len(x) > 1 ]

<<<<<<< HEAD
                            # Obtenemoss la geometr韆 (Polyline) resultante de aplicar el algoritmo
                            resultLine = QgsGeometry.fromPolyline(resultPoints)
                            # A馻dimos la geomtr韆 a la feature temporal
                            f.setGeometry(resultLine)

                            # A馻dimos la feature a la capa de salida
                            self.layer_salida.addFeature(f)

                    # Si la geometr韆 no es multiparte
                    else :

                        # Extraemos los puntos de la geomtr韆
                        points = self.__extractPoints(feature)

                        # Se crea un nuevo feature (temporal)
                        # Servir� para crear la feature de la capa de salida
                        f = QgsFeature()

                        # Ejecutamos el algoritmo pertinente
                        # sobre los puntos extraidos de la geometr韆 que estamos recorriendo
=======
                            # Obtenemoss la geometr铆a (Polyline) resultante de aplicar el algoritmo
                            resultLine = QgsGeometry.fromPolyline(resultPoints)
                            # A帽adimos la geomtr铆a a la feature temporal
                            f.setGeometry(resultLine)

                            # A帽adimos la feature a la capa de salida
                            self.layer_salida.addFeature(f)

                    # Si la geometr铆a no es multiparte
                    else :

                        # Extraemos los puntos de la geomtr铆a
                        points = self.__extractPoints(feature)

                        # Se crea un nuevo feature (temporal)
                        # Servir谩 para crear la feature de la capa de salida
                        f = QgsFeature()

                        # Ejecutamos el algoritmo pertinente
                        # sobre los puntos extraidos de la geometr铆a que estamos recorriendo
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
                        if name == self.Algorithms.MC_MASTER:
                            resultPoints = [ QgsPoint(*x) for x in self.__mcMaster(points, param) ] #if len(x) > 1 ]
                        else :
                            resultPoints = [ QgsPoint(*x) for x in self.__douglasPeucker(points, param) ] #if len(x) > 1 ]


<<<<<<< HEAD
                        # Obtenemoss la geometr韆 (Polyline) resultante de aplicar el algoritmo
                        resultLine = QgsGeometry.fromPolyline(resultPoints)
                        # A馻dimos la geomtr韆 a la feature temporal
                        f.setGeometry(resultLine)

                        # A馻dimos la feature a la capa de salida
                        self.layer_salida.addFeature(f)
            # Si se produce una excepci髇
=======
                        # Obtenemoss la geometr铆a (Polyline) resultante de aplicar el algoritmo
                        resultLine = QgsGeometry.fromPolyline(resultPoints)
                        # A帽adimos la geomtr铆a a la feature temporal
                        f.setGeometry(resultLine)

                        # A帽adimos la feature a la capa de salida
                        self.layer_salida.addFeature(f)
            # Si se produce una excepci贸n
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
            except Exception as e:
                # mostramos un mensaje de error
                QMessageBox.information(None, 'ERROR!', str(e))

                print 'error', e

    '''
    @method: __shortestDistance
<<<<<<< HEAD
    @brief: Devuelve la ditancia m醩 corta entre
            un punto y una recta
    @param: point - lista con los valores x,y del punto ej: [1000, 1000]
    @param: line: lista con los par醡etros a,b,c que definen una l韓ea ax + by + c = 0
    @return: double - distancia m醩 corta
=======
    @brief: Devuelve la ditancia m谩s corta entre
            un punto y una recta
    @param: point - lista con los valores x,y del punto ej: [1000, 1000]
    @param: line: lista con los par谩metros a,b,c que definen una l铆nea ax + by + c = 0
    @return: double - distancia m谩s corta
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
    '''
    def __shortestDistance(self,point, line):
        # Extraemos las coordenadas del punto
        xp, yp = point
<<<<<<< HEAD
        # Extraemos los par醡etros de la l韓ea
        a, b, c = line
        # Calculamos y deolvemos la ditancia m韓ima entre el punto y la recta
=======
        # Extraemos los par谩metros de la l铆nea
        a, b, c = line
        # Calculamos y deolvemos la ditancia m铆nima entre el punto y la recta
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        return math.fabs(a*xp + b*yp + c)/math.sqrt(a**2 + b**2)

    '''
    @method: __extractPoints
    @brief: Extrae los puntos de una feature (simple)
    @param: feature - feature de entrada
<<<<<<< HEAD
    @return: [] - lista de puntos de la geomtr韆 del feature pasado como par醡etro
    '''
    def __extractPoints(self, feature):
        # Obtenemos una referencia de la geometr韆
        geom = feature.geometry()

        # Creamos una lista vac韆
        points = []

        # Comprobamos que la geometr韆 no sea None
        # En cuyo caso devolvemos una lista vac韆
=======
    @return: [] - lista de puntos de la geomtr铆a del feature pasado como par谩metro
    '''
    def __extractPoints(self, feature):
        # Obtenemos una referencia de la geometr铆a
        geom = feature.geometry()

        # Creamos una lista vac铆a
        points = []

        # Comprobamos que la geometr铆a no sea None
        # En cuyo caso devolvemos una lista vac铆a
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        if geom == None: return points

        # contador
        i = 0

<<<<<<< HEAD
        # Bucle while que recorre los  v閞tices de
        # la geometr韆
        while(geom.vertexAt(i) != QgsPoint(0,0)):
            # Obtenemos el v閞tice seg鷑 el 韉ice i
            # y lo a馻dimos a la lista
=======
        # Bucle while que recorre los  v茅rtices de
        # la geometr铆a
        while(geom.vertexAt(i) != QgsPoint(0,0)):
            # Obtenemos el v茅rtice seg煤n el 铆dice i
            # y lo a帽adimos a la lista
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
            points.append(geom.vertexAt(i))
            # aumentamos el contador en 1
            i += 1

        # Devolvemos la lista
        return points

    '''
    @method: __mcMaster
<<<<<<< HEAD
    @brief: Aplica el algoritmo de generalizaci髇 de McMaster
    @param: points - lista de puntos de la geomtr韆 de la capa de entrada
    @param:  mu - n鷐ero de vertices que entran en el c醠culo de la media (impar > 1)
    @return: [] - lista de puntos con las coordenadas de la l韓ea suavizada
    '''
    def __mcMaster(self, points, mu):
            # Si no hay puntos devuelve una lista vac韆
            if not points : return []
            # Par醡etro para el vecindario de cada vertice
=======
    @brief: Aplica el algoritmo de generalizaci贸n de McMaster
    @param: points - lista de puntos de la geomtr铆a de la capa de entrada
    @param:  mu - n煤mero de vertices que entran en el c谩lculo de la media (impar > 1)
    @return: [] - lista de puntos con las coordenadas de la l铆nea suavizada
    '''
    def __mcMaster(self, points, mu):
            # Si no hay puntos devuelve una lista vac铆a
            if not points : return []
            # Par谩metro para el vecindario de cada vertice
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
            half_mu = int(math.floor(mu/2))
            # Longitud de la lista de puntos
            end = len(points)

            # Lista con los puntos del suavizado
<<<<<<< HEAD
            # empezamos a馻diendo los puntos primeros que quedan fuera del rango
=======
            # empezamos a帽adiendo los puntos primeros que quedan fuera del rango
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
            # [0, half_mu)
            smooth_points = map( list, points[ : half_mu ] )
            #print smooth_points

<<<<<<< HEAD
            # Generamos un iterador para obtener los 韓dices de los puntos de los
=======
            # Generamos un iterador para obtener los 铆ndices de los puntos de los
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
            # cuales podemos aplicar un vecindario de mu
            for i in range(half_mu, end - half_mu):

                # Obtenemos el punto situado en medio del vecindario
                xactual, yactual = points[i]

                # Obtenemos los puntos que forman parte del vecindario
                computed_points = points[i - half_mu : i + (mu + 1)/2]

                # Obtenemos las coordenadas de los puntos en listas (una para cada coord)
                xcoords = [p[0] for p in computed_points]
                ycoords = [p[1] for p in computed_points]

<<<<<<< HEAD
                # Obtenemos la media geom閠rica de los puntos que conforman el vecindario
                mediax, mediay = sum(xcoords)/len(xcoords), sum(ycoords)/len(ycoords)


                # Y realizamos la media geom閠rica con la media del vecindario y el punto
                # de estudio
                x, y = (mediax + xactual)/2, (mediay + yactual)/2
                # Finalmente lo a馻dimos a la lista de puntos del suavizado
                smooth_points.append([x, y])

            # finalizamos a馻diendo los puntos primeros que quedan fuera del rango
=======
                # Obtenemos la media geom茅trica de los puntos que conforman el vecindario
                mediax, mediay = sum(xcoords)/len(xcoords), sum(ycoords)/len(ycoords)


                # Y realizamos la media geom茅trica con la media del vecindario y el punto
                # de estudio
                x, y = (mediax + xactual)/2, (mediay + yactual)/2
                # Finalmente lo a帽adimos a la lista de puntos del suavizado
                smooth_points.append([x, y])

            # finalizamos a帽adiendo los puntos primeros que quedan fuera del rango
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
            # [end - half_mu, end)
            smooth_points += map( list, points[ -half_mu : ] )

            # Devuelve una lista con los puntos de la linea suavizada por el algoritmo
            # McMaster
            return smooth_points

    '''
    @method: __douglasPeucker
<<<<<<< HEAD
    @brief: Aplica el algoritmo de generalizaci髇 de Douglas-Peucker
    @param: points - lista de puntos de la geomtr韆 de la capa de entrada
    @param:  epsilon - distancia m韓ima para incluir el v閞tice
    @return: [] - lista de puntos con las coordenadas de la l韓ea generalizada
    '''
    def  __douglasPeucker(self,points, epsilon):
        # Distancia m醲ima
        dmax = 0
        # 蚽dice de la posici髇 en la lista del punto de m醲ima distancia
        index = 0

        # 蚽dice final para el bucle
=======
    @brief: Aplica el algoritmo de generalizaci贸n de Douglas-Peucker
    @param: points - lista de puntos de la geomtr铆a de la capa de entrada
    @param:  epsilon - distancia m铆nima para incluir el v茅rtice
    @return: [] - lista de puntos con las coordenadas de la l铆nea generalizada
    '''
    def  __douglasPeucker(self,points, epsilon):
        # Distancia m谩xima
        dmax = 0
        # 脥ndice de la posici贸n en la lista del punto de m谩xima distancia
        index = 0

        # 脥ndice final para el bucle
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        end = len(points) - 1

        # Punto inicial
        x0, y0 = points[0]
        # Punto final
        x1, y1 = points[-1]

<<<<<<< HEAD
        # Par醡etros de la recta
=======
        # Par谩metros de la recta
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        a = y1 - y0
        b = -(x1 - x0)
        c = a*(-x0) - b*y0


<<<<<<< HEAD
        # Si el primer y el 鷏timo punto son el mismo
        if a == 0 and b == 0 : return []

        # Generamos un iterador para obtener los 韓dices
=======
        # Si el primer y el 煤ltimo punto son el mismo
        if a == 0 and b == 0 : return []

        # Generamos un iterador para obtener los 铆ndices
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        for i in range(1, end):

            # punto
            p = points[i]

<<<<<<< HEAD
            # distancia m醩 corta entre el punto y la recta
=======
            # distancia m谩s corta entre el punto y la recta
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
            d = self.__shortestDistance(p, [a, b, c])

            # Si la distancia es mayor que lo que haya almacenado en dmax
            if d > dmax :
<<<<<<< HEAD
                # Guardamos el 韓dice y la distancia en las variables
                index = i
                dmax = d

        # Si la ditancia m醲ima es mayor o igual que epsilon
        if dmax >= epsilon :
            # Realizamos el algoritmo

            # res_ini almacenar� los resultados de aplicar el algoritmo otra vez
            # (recursividad) sobre la porci髇 de la lista de puntos desde 0 hasta el 韓dice
            # del punto de "distancia m醲ima sobre la recta" + 1
            res_ini = self.__douglasPeucker(points[: index + 1], epsilon)

            # res_fin almacenar� los resultados de aplicar el algoritmo otra vez
            # (recursividad) sobre la porci髇 de la lista de puntos desde el 韓dice
            # del punto de "distancia m醲ima sobre la recta" hasta len(points)
=======
                # Guardamos el 铆ndice y la distancia en las variables
                index = i
                dmax = d

        # Si la ditancia m谩xima es mayor o igual que epsilon
        if dmax >= epsilon :
            # Realizamos el algoritmo

            # res_ini almacenar谩 los resultados de aplicar el algoritmo otra vez
            # (recursividad) sobre la porci贸n de la lista de puntos desde 0 hasta el 铆ndice
            # del punto de "distancia m谩xima sobre la recta" + 1
            res_ini = self.__douglasPeucker(points[: index + 1], epsilon)

            # res_fin almacenar谩 los resultados de aplicar el algoritmo otra vez
            # (recursividad) sobre la porci贸n de la lista de puntos desde el 铆ndice
            # del punto de "distancia m谩xima sobre la recta" hasta len(points)
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
            res_fin = self.__douglasPeucker(points[index : ], epsilon)

            # Juntamos las dos listas resultantes y devolvemos el array juntado
            return res_ini[:-1] + res_fin

<<<<<<< HEAD
        # Si la distancia m醲ima es menor que epsilon
=======
        # Si la distancia m谩xima es menor que epsilon
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
        else :
            # Devolvemos una lista con los puntos inicial y final
            return [ points[0], points[-1] ]


```

<<<<<<< HEAD
En primero lugar, lo que hicimos fue desarrollar los algoritmos en python como funciones y viendo si podriamos desarrollar otros procesos como funciones tambi閚. Por ejemplo el c醠culo de la distancia m韓ima en el caso del algoritmo **Douglas-Peucker**, se ha desarrollado como una funci髇 externa.
    
Una vez desarrollados los algoritmos los metimos en una clase GeneraLine y hicimos checkeos como ver si la capa que se introduce es del tipo *`LineString(if layer.wkbType()==QGis.WKBLineString: ...)`*, comprovar si la capa es multiparte o recoger el EPSG de la capa. Para cada capa se recorrer醤 todos sus features y se aplicar� el algoritmo seleccionado.

Creamos la funci髇 *`__extractPoints(feature)`* para extraer todos los puntos de cada feature y poder as� aplicar los algoritmos sobre estos.
Con la funci髇 predefinida de PyQgis vertexAt(i), siendo i el 韓dice del v閞tice, extraemos de la geometria de cada feature dichos puntos de la siguiente manera:
=======
En primero lugar, lo que hicimos fue desarrollar los algoritmos en python como funciones y viendo si podriamos desarrollar otros procesos como funciones tambi茅n. Por ejemplo el c谩lculo de la distancia m铆nima en el caso del algoritmo **Douglas-Peucker**, se ha desarrollado como una funci贸n externa.
    
Una vez desarrollados los algoritmos los metimos en una clase GeneraLine y hicimos checkeos como ver si la capa que se introduce es del tipo *`LineString(if layer.wkbType()==QGis.WKBLineString: ...)`*, comprovar si la capa es multiparte o recoger el EPSG de la capa. Para cada capa se recorrer谩n todos sus features y se aplicar谩 el algoritmo seleccionado.

Creamos la funci贸n *`__extractPoints(feature)`* para extraer todos los puntos de cada feature y poder as铆 aplicar los algoritmos sobre estos.
Con la funci贸n predefinida de PyQgis vertexAt(i), siendo i el 铆ndice del v茅rtice, extraemos de la geometria de cada feature dichos puntos de la siguiente manera:
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449

```python
def __extractPoints(self, feature):
        geom = feature.geometry()
        points = []
        if geom == None: return points
        i = 0
        while(geom.vertexAt(i) != QgsPoint(0,0)):
            points.append(geom.vertexAt(i))
            i += 1
        return points
```


# Pruebas y Resultados
Al terminar y depurar el programa hicimos varias pruebas para ver que tal funciona.
<<<<<<< HEAD
- Capa de Orograf韆 (curvas)
Sabiendo que no tiene sentido generalizar de esta forma las curvas de nivel ya que pierden su significado geogr醘ico y nos inventar韆mos una forma del terreno distinta, hemos probado para ver como funcionan los algor韙mos sobre un curvado tan complejo con distintos valores de par醡etro.
    - Algoritmo Douglas-Peucker - distancia m韓ima 50
    - Algoritmo Douglas-Peucker - distancia m韓ima 5
    - Algoritmo Douglas-Peucker - distancia m韓ima 1
    Vemos que el algoritmo funciona mejor para este caso con una distancia m韓ima peque馻.
    - Algoritmo McMaster - vecindario 9
    - Algoritmo McMaster - vecindario 21
Como las curvas var韆n mucho en vecindarios peque駉s se observa al aplicar vecindarios m醩 grandes como el suavizado se aleja de la curva original dr醩icamente al realizar la media de todo el vecindario.

- Capa de Hidrograf韆
Para lineas menos cambiantes dependiende de nuestro pr髉osito nos servir� uno mejor que otro. Para generalizar usaremos el algoritmo de Douglas-Peucker (eliminando puntos) y para suavizar usaremos el algor韙mo de McMaster el cual atenuar� los picos generados por la intersecci髇 en los v閞tices (curvar� la linea).
=======
- Capa de Orograf铆a (curvas)
Sabiendo que no tiene sentido generalizar de esta forma las curvas de nivel ya que pierden su significado geogr谩fico y nos inventar铆amos una forma del terreno distinta, hemos probado para ver como funcionan los algor铆tmos sobre un curvado tan complejo con distintos valores de par谩metro.
    - Algoritmo Douglas-Peucker - distancia m铆nima 50
    - Algoritmo Douglas-Peucker - distancia m铆nima 5
    - Algoritmo Douglas-Peucker - distancia m铆nima 1
    Vemos que el algoritmo funciona mejor para este caso con una distancia m铆nima peque帽a.
    - Algoritmo McMaster - vecindario 9
    - Algoritmo McMaster - vecindario 21
Como las curvas var铆an mucho en vecindarios peque帽os se observa al aplicar vecindarios m谩s grandes como el suavizado se aleja de la curva original dr谩sicamente al realizar la media de todo el vecindario.

- Capa de Hidrograf铆a
Para lineas menos cambiantes dependiende de nuestro pr贸posito nos servir谩 uno mejor que otro. Para generalizar usaremos el algoritmo de Douglas-Peucker (eliminando puntos) y para suavizar usaremos el algor铆tmo de McMaster el cual atenuar谩 los picos generados por la intersecci贸n en los v茅rtices (curvar谩 la linea).
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
    - prueba1 _50
    - hidro_dp_20

    - hidro_mcm_9


# Conclusiones

Tras realizar varias pruebas con el software generado podemos poner en la mesa distintos puntos favorables y distintos puntos a mejorar:

- **Respecto al UI generado**

<<<<<<< HEAD
Se ha elaborado un UI bastante logrado que alberga muchas funcionalidades. Se podr韆n mejorar diversos aspectos de menor importancia que podr韆n ver luz en futuros releases.

Un aspecto importante que no se ha llegado a conseguir pero que se puede ver en el archivo [project_sig2.py](https://github.com/hectormg92/pyqgis-awesome-linestring-generalizer/blob/master/project_sig2.py) es ejecutar los procesos de la clase GeneraLine en otro hilo de ejecuci髇 para no interferir con el hilo de renderizado del UI y de esta manera no bloquearlo.

- **Respecto a los algoritmos**

El par醡etro a introducir en el algoritmo de Douglas Peucker, para mejorar la experiencia del usuario, deber韆 ser un n鷐ero comprendido entre 0 y 1 (escalando con la distancia m醲ima entre los distintos v閞tices con la recta (que une el punto inicial y final).

Adem醩 esta misma idea tambi閚 se podr韆 aplicar al algoritmo McMster con el n鷐ero de v閞tices m醲imo (ya que el m韓imo es tres).

Se podr韆 llevar a cabo una funcionalidad extra que concatenara distintas 髍denes para ejecutar varios algoritmos de una vez con el resultado del proceso anterior (Parecido a como hace ArcMap con ModelBuilder).
Por ejemplo:

- Proceso 1 : Aplicar Douglas Peucker a la capa de entrada
- Proceso 2 : Aplicar McMaster a la capa resultante del proceso 1
=======
Se ha elaborado un UI bastante logrado que alberga muchas funcionalidades. Se podr铆an mejorar diversos aspectos de menor importancia que podr铆an ver luz en futuros releases.

Un aspecto importante que no se ha llegado a conseguir pero que se puede ver en el archivo [project_sig2.py](https://github.com/hectormg92/pyqgis-awesome-linestring-generalizer/blob/master/project_sig2.py) es ejecutar los procesos de la clase GeneraLine en otro hilo de ejecuci贸n para no interferir con el hilo de renderizado del UI y de esta manera no bloquearlo.

- **Respecto a los algoritmos**

El par谩metro a introducir en el algoritmo de Douglas Peucker, para mejorar la experiencia del usuario, deber铆a ser un n煤mero comprendido entre 0 y 1 (escalando con la distancia m谩xima entre los distintos v茅rtices con la recta (que une el punto inicial y final).

Adem谩s esta misma idea tambi茅n se podr铆a aplicar al algoritmo McMster con el n煤mero de v茅rtices m谩ximo (ya que el m铆nimo es tres).

Se podr铆a llevar a cabo una funcionalidad extra que concatenara distintas 贸rdenes para ejecutar varios algoritmos de una vez con el resultado del proceso anterior (Parecido a como hace ArcMap con ModelBuilder).
Por ejemplo:

- Proceso 1 : Aplicar Douglas Peucker a la capa de entrada
- Proceso 2 : Aplicar McMaster a la capa resultante del proceso 1





    
    
    
    
    
    
    
>>>>>>> ae56f17afc1c98bcc4e77b9e0bdce7986984a449
