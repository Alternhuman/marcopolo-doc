Requisitos funcionales
----------------------

CU1-Descubrimiento de nodos
~~~~~~~~~~~~~~~~~~~~~~~~~~~

- **Versión**: 
- **Autores**: 
- **Fuentes**: 
- **Objetivos asociados**: 
- **Requisitos asociados**: 
- **Descripción**: A petición de un usuario o aplicación, una instancia del *software* realizará una operación de descubrimiento de los diferentes nodos presentes en la red.
- **Precondición**: La instancia de Marco debe haber sido iniciado previamente.
- **Secuencia normal**:

    1. A través de los diferentes mecanismos de interconexión, una aplicación o usuario solicita el descubrimiento de nodos presentes en la red.
    2. El mecanismo de interconexión recibe los diferentes parámetros y los procesa. En caso de que la evaluación no sea satisfactoria, se inicia el caso de uso RF4 y posteriormente la ejecución finaliza. En caso contrario, se continúa la secuencia.
    3. El mecanismo de interconexión envía los parámetros a la instancia local de Marco, que realiza la acción solicitada.
    4. Transcurre un pequeño tiempo de espera para las respuestas de los nodos presentes en la red. Este es definido por el usuario, o en caso de que no sea indicado se utiliza un tiempo por defecto. Durante la espera son procesadas las respuestas que se reciben. 
    5. La instancia procesa los datos y los envía a la instancia del conector con la aplicación.
    6. El conector determina si los datos son válidos y los retorna a la aplicación. En caso contrario, comienza el caso de uso RF4.

- **Poscondición**: Se han descubierto los diferentes nodos presentes en el sistema.
- **Excepciones**

    + **No se puede establecer una conexión con la instancia de Marco**: En este caso el conector envía un mensaje de error específico para cada plataforma (excepción, código de estado...) indicando esta situación, con el objetivo de que la aplicación pueda recuperarse del error (asumir unos valores por defecto que sustituyan a los datos solicitados, realizar la operación de nuevo...).
- **Rendimiento**:
- **Frecuencia**:
- **Importancia**:
- **Urgencia**: Muy urgente
- **Estado**: Completo
- **Estabilidad**: Estable
- **Comentarios**

CU2-Descubrimiento de servicios
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

- **Versión**: 
- **Autores**: 
- **Fuentes**: 
- **Objetivos asociados**: 
- **Requisitos asociados**: 
- **Descripción**: Los diferentes usuarios del sistema podrán realizar operaciones de descubrimiento de servicios ofrecidos por los diferentes nodos que conforman el sistema.
- **Precondición**: La instancia de Marco debe haber sido iniciado previamente.
- **Secuencia normal**:

    1. A través de los diferentes mecanismos de interconexión, una aplicación o usuario solicita el descubrimiento de todos los servicios que un nodo presente en la red ofrece.
    2. El mecanismo de interconexión recibe los diferentes parámetros y los procesa. En caso de que la evaluación no sea satisfactoria, se inicia el caso de uso RF4 y posteriormente la ejecución finaliza. En caso contrario, se continúa la secuencia.
    3. El mecanismo de interconexión envía los parámetros a la instancia local de Marco, que realiza la acción solicitada.
    4. Transcurre un pequeño tiempo de espera para las respuestas de los nodos presentes en la red.
    5. La instancia procesa los datos y los envía a la instancia del conector con la aplicación.
    6. El conector determina si los datos son válidos y los retorna a la aplicación. En caso contrario, comienza el caso de uso RF4.
    7. Se retornan los datos recogidos o una lista vacía en caso de la búsqueda haya sido infructuosa.
    
- **Poscondición**: Se han descubierto todos los nodos presentes en el sistema que ofrecen el servicio solicitado.
- **Excepciones**: 
    
    + **No se puede establecer una conexión con la instancia de Marco**: En este caso el conector envía un mensaje de error específico para cada plataforma (excepción, código de estado...) indicando esta situación, con el objetivo de que la aplicación pueda recuperarse del error (asumir unos valores por defecto que sustituyan a los datos solicitados, realizar la operación de nuevo...).

- **Rendimiento**
- **Frecuencia**
- **Importancia**: Alta
- **Urgencia**: Elevada
- **Estado**: Completo
- **Estabilidad**: Estable
- **Comentarios**


CU3-Consulta a un nodo
~~~~~~~~~~~~~~~~~~~~~~

- **Versión**: 
- **Autores**: 
- **Fuentes**: 
- **Objetivos asociados**: 
- **Requisitos asociados**: 
- **Descripción**: El software podrá realizar operaciones de consulta a un nodo específico en la red.
- **Precondición**: La instancia de Marco debe haber sido iniciado previamente.
- **Secuencia normal**:
    
    1. A través de los diferentes mecanismos de interconexión, una aplicación o usuario solicita el descubrimiento todos los nodos presentes en la red ofertantes de un servicio identificado por una cadena de texto.
    2. El mecanismo de interconexión recibe los diferentes parámetros y los procesa. En caso de que la evaluación no sea satisfactoria, se inicia el caso de uso RF4 y posteriormente la ejecución finaliza. En caso contrario, se continúa la secuencia.
    3. El mecanismo de interconexión envía los parámetros a la instancia local de Marco, que realiza la acción solicitada, enviando una petición al nodo solicitante.
    4. Transcurre un pequeño tiempo de espera para la respuesta del nodo. 
    5. En caso de que el nodo consultado responda, se procesa la lista de servicios incluida en el mensaje.
    6. La instancia procesa los datos y los envía a la instancia del conector con la aplicación.
    7. El conector determina si los datos son válidos y los retorna a la aplicación. En caso contrario, comienza el caso de uso RF4.
- **Poscondición**: Se han descubierto los servicios ofrecidos por un nodo.
- **Excepciones**: 

    + **No se puede establecer una conexión con la instancia de Marco**: En este caso el conector envía un mensaje de error específico para cada plataforma (excepción, código de estado...) indicando esta situación, con el objetivo de que la aplicación pueda recuperarse del error (asumir unos valores por defecto que sustituyan a los datos solicitados, realizar la operación de nuevo...).
    + **El nodo no se encuentra presente en la red**: El usuario es notificado de esta situación. 
- **Rendimiento**
- **Frecuencia**:
- **Importancia**: Alta
- **Urgencia**: Muy alta
- **Estado**: Completo
- **Estabilidad**: Estable
- **Comentarios**

CU4-Error
~~~~~~~~~

- **Versión**: 
- **Autores**: 
- **Fuentes**: 
- **Objetivos asociados**: 
- **Requisitos asociados**: 
- **Descripción**: En caso de que se produzca un error en una tarea, se analiza la situación que ha desencadenado dicho estado y se ofrecen al usuario, en caso de que sea posible, opciones de recuperación.
- **Precondición**: Se debe haber producido un error.
- **Secuencia normal**:

    1. Un error ha sido emitido por alguno de los componentes involucrados en una operación.
    2. El componente que detecta dicho error determina las causas del mismo, identificando diferentes características como el estado del sistema, códigos retornados por funciones, mensajes intercambiados entre componentes, etcétera.
    3. El componente informa al usuario o aplicación, o en su defecto, delega esta tarea a otra entidad en la cadena de comunicación.
    4. El componente determina cuál es el mecanismo de notificación adecuado para la situación dada, y realiza la acción asociada (lanzar una excepción, emitir un código de error, escribir una entrada en un registro...).
- **Poscondición**: El usuario o aplicación es notificado del error.
- **Excepciones**
- **Rendimiento**
- **Frecuencia**
- **Importancia**: Media
- **Urgencia**: Alta
- **Estado**: Completo
- **Estabilidad**: Estable
- **Comentarios**

.. 
    - **Versión**: 
    - **Autores**: 
    - **Fuentes**: 
    - **Objetivos asociados**: 
    - **Requisitos asociados**: 
    - **Descripción**
    - **Precondición**
    - **Secuencia normal**
    - **Poscondición**
    - **Excepciones**
    - **Rendimiento**
    - **Frecuencia**
    - **Importancia**
    - **Urgencia**
    - **Estado**
    - **Estabilidad**
    - **Comentarios**

Publicar un servicio raíz
-------------------------
 
- **Versión**: 
- **Autores**: 
- **Fuentes**: 
- **Objetivos asociados**: 
- **Requisitos asociados**: 
- **Descripción**: Un servicio raíz es aquel que es publicado para todo el sistema, sin que se incluya en el identificador el nombre del usuario.
- **Precondición**: Una instancia de Polo debe estar ejecutándose en el sistema.
- **Secuencia normal**
- **Poscondición**
- **Excepciones**
- **Rendimiento**
- **Frecuencia**
- **Importancia**
- **Urgencia**
- **Estado**
- **Estabilidad**
- **Comentarios**

Publicar un servicio de usuario
-------------------------------

Eliminar un servicio
--------------------


Diagrama de casos de uso
~~~~~~~~~~~~~~~~~~~~~~~~

**Paquete de casos de uso**

.. image:: ../img/cu_paquetes.*

**Paquete Marco**

.. image:: ../img/cu_Marco.*
    :align: center

**Paquete Polo**

.. image:: ../img/cu_Polo.*
    :align: center
