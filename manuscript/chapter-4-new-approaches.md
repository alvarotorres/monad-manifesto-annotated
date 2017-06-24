# Capítulo 4 - Nuevos enfoques
___
Monad adopta nuevos enfoques a los problemas de 1) construcción de comandos, 2) composición de soluciones 3) modelos de gestión y 4) GUI de gestión. La arquitectura de Monad proviene de las siguientes observaciones:

1. La mayoría de las soluciones son desarrolladas “in house” y compuestas por comandos existentes por los administradores.
2. La mayoría de las soluciones se centran en la automatización de la gestión o la provisión de correcciones ad hoc.
3. La mayoría de los administradores no son programadores “natos”. O bien no tienen el deseo, la habilidad o (más a menudo), el tiempo para hacer una programación sofisticada.
4. La mayoría de los desarrolladores de aplicaciones no harán que su código sea manejable a menos que haya un beneficio inmediato y sustancial para el usuario [^4-5]

## 4.1 - Un nuevo enfoque para construir comandos
El enfoque tradicional de la construcción de comandos es ineficiente. Gran parte del esfuerzo se dedica a reescribir las mismas funciones una y otra vez por diferentes personas de diferentes maneras. Todos para:

  * Analizar, validar y codificar la entrada de usuario.
  * Documentar su uso.
  * Dejar registro de actividades.
  * Formatear datos, resultados de salida e informes de errores.
  * Operar en nodos remotos o conjuntos de nodos remotos.
   
Sin embargo, a pesar de toda esta coincidencia, la mayoría de las plataformas [^4-1] [^4-2] proporcionan poco o ningún apoyo para hacer estas actividades de manera coherente. El resultado es que los comandos de hoy en día son ineficientes para desarrollar e inconsistentes en su forma de usar [^4-6].

Monad adopta un enfoque diferente que proporciona a los desarrolladores el máximo aprovechamiento y la máxima consistencia para los usuarios finales, mediante la definición de un modelo de automatización para aplicaciones que afecta a las funciones comunes para que puedan implementarse una vez en un entorno de ejecución común [^4-3]. Los desarrolladores ya no producen ejecutables autónomos. En su lugar, escriben piezas de código muy enfocadas como  clases .NET (Cmdlets) que luego se exponen como API, comandos e interfaces gráficas. Las funciones comunes se implementan y prueban una vez y proporcionan un conjunto único de semántica, así como un conjunto coherente y uniforme de mensajes de error. [^4-7]

## 4.2 - Un nuevo enfoque para componer soluciones
El enfoque tradicional para componer soluciones es difícil y frágil. Utiliza “pipelines” para realizar análisis basado en oraciones de flujos de texto [^4-4]. Estos mecanismos son incómodos, inconsistentes e imprecisos. Los administradores pasan la mayor parte de su tiempo buscando mecanismos para resolver problemas, en lugar de resolver dichos problemas. Monad tiene un enfoque diferente que proporciona un motor de ejecución de secuencias de comandos preciso y potente para crear tuberías (pipelines) de objetos .NET. En lugar de canalizar texto no estructurado, canalizamos objetos .NET [^4-8]. Esto permite que los componentes de la canalización (pipelines) operen a bajo nivel directamente sobre los objetos y sus propiedades utilizando las API [.NET Reflection] (http://msdn.microsoft.com/library/default.asp?url=/library/en-us/cpguide/html/cpconreflectionoverview.asp). (Las API de Reflection permiten encontrar el tipo de un objeto, las propiedades y métodos que tiene, obtener los valores de propiedades e invocar sus métodos).

El entorno de tiempo de ejecución de Monad proporciona un medio para acceder a los cmdlets y ejecutar secuencias de comandos en máquinas remotas a través de Web Services. [^4-9]

## 4.3 - Un nuevo enfoque de los modelos de gestión

El enfoque tradicional de los modelos de gestión produce una experiencia de administración inconsistente. Hoy en día hay miles de comandos optimizados localmente. Cada desarrollador de comandos define su propio modelo de gestión con un conjunto de nombres y conceptos. Mientras se produce la copia de comandos populares, no hay incentivo sistémico para hacerlo. Se han hecho esfuerzos para proporcionar directrices que impulsen la optimización global, pero el peso del legado ha dificultado que tales esfuerzos ganen mucha fuerza.

Una situación similar existe con las tecnologías de instrumentación actuales que languidecen debido a la falta de soporte de herramientas. Los esfuerzos de evangelización por instrumentación son difíciles a medida que los grupos [de productos] rechazan la estrategia "construye y vendrá". Los desarrolladores de herramientas se resisten a la vasta superficie de los objetos y responden proporcionando una funcionalidad genérica (como supervisión o navegación) a través de una amplia gama de objetos o proporcionando funciones complejas para un pequeño conjunto de problemas.

Monad adopta un enfoque diferente: minimiza el coste de la automatización y proporciona un beneficio inmediato para el usuario final proporcionando **clases de extensión de automatización** basadas en escenarios y herramientas in-the-box que explotan esas clases. Monad puede soportar casi cualquier esquema de automatización, pero alienta firmemente el uso de esquemas estándar proporcionando un conjunto de clases base para escenarios administrativos específicos. Estas clases base incluyen: Navegación, Diagnóstico, Configuración, Ciclo de Vida y Operaciones [^4-10]. Dichas clases proporcionan una sintaxis común, conmutadores, mensajes de error internacionalizados y soluciones a problemas de escenarios comunes (por ejemplo, una implementación común de una pila de directorios para todos los comandos de navegación). Monad también proporciona un conjunto de controles de interfaz de usuario y herramientas que se suministran con el sistema operativo que controla dichas extensiones para realizar una tarea de gestión específica


## 4.4 - Un Nuevo Enfoque a las Herramientas GUI de Gestión

El enfoque tradicional de las GUI de administración proporciona un mínimo de apalancamiento para desarrolladores. Las herramientas de GUI de administración de Windows de hoy en día se desarrollan de la misma manera que una aplicación completa. Tienen código de interfaz gráfica de usuario, aplicación de lógica de dominio/restricción y acceso de API a objetos administrados locales y remotos. Los servicios de GUI de gestión se limitan en gran medida a un contenedor de interfaz de usuario que facilita la multiplexación de varias herramientas y un cierto nivel de integración. Este enfoque requiere un esfuerzo significativo y un conjunto de pruebas exhaustivo. Dado que gran parte de la lógica del dominio y la imposición de restricciones está incrustada en la GUI, es común que las líneas de comandos expongan un subconjunto de las funciones de una GUI. El enfoque tradicional funciona en contra de la automatización.

Monad adopta un enfoque diferente que proporciona un rico conjunto de servicios orientados a la gestión para desarrollar herramientas de GUI de gestión. Estos servicios permiten que las GUI de administración se superpongan al motor de secuencias de comandos y Cmdlets. Esto proporciona auditoría, grabación/reproducción de macros y herramientas integradas de GUI/línea de comandos. Esto disminuye el nivel de habilidad requerido para desarrollar una GUI de administración, al simplificar el acceso y el control de los objetos de administración transparentes de manera remota. También permite a los usuarios ver los scripts ejecutados por las interacciones GUI que les ayuda a aprender la capa de automatización y crear sus propios scripts automatizados. La estratificación reduce la matriz de pruebas aprovechando las pruebas realizadas en la línea de comandos y las secuencias de comandos y solo es necesario probar las rutas GUI para invocar esas funciones. La GUI de administración también puede exponer su funcionamiento interno a través de Cmdlets que proporciona a los desarrolladores, probadores y soporte un fácil acceso al estado interno y el control de la GUI para la depuración/diagnóstico/prueba automatizada.

___

**Notes:**
[^4-1]: ORIGINAL: UNIX has the [getopt()](http://www.gnu.org/software/libc/manual/html_node/Using-Getopt.html) call for simple command option parsing. 

[^4-2]: ORIGINAL: [VMS DCL](http://h71000.www7.hp.com/doc/732final/9996/9996pro.html) and AS400’s CL are the exceptions to this.  They provide a common command parser so the commands that use this have a high degree of syntactic consistency.

[^4-3]: ORIGINAL: There is a wonderful synergy between programmer’s desire to minimize the amount of code they write for management and customers desire to have a consistent management experience.

[^4-4]: Prayer based parsing is when you parse the text and pray that you got it right. e.g. Cut off the first 3 (or was it 4?) lines, cut out column 30-40 (assuming that those spaces are not tabs), cast that as an integer (hmm. – does anyone use 64 bits?...well let’s just hope its 32 bits).

[^4-5]: Meaning, most developers won't implement interfaces that administrators can use to manage the application. At best, a "lazy" developer might simply put all their configuration information into a text file and call that "manageable." Ironically, that's essentially how Unix is built from the ground up, and it _is_ manageable, because there's little as easy as modifying a text file, especially if it's structured (as in JSON or XML).

[^4-6]: Which is why developers hate making them and admins hate using them.

[^4-7]: This is the model PowerShell adopted. Cmdlets are instances of a class, which they inherit as their base. That class provides a ton of common functionality, so that the actual code in a cmdlet is around 99% focused on whatever it is that cmdlet is doing. The cmdlet developer doesn't focus on parsing command-line arguments, validating mandatory items, etc.

[^4-8]: An "object" in this sense is little more than a set of structured data, not unlike a database table or a spreadsheet. Each object represents some management component, and its properties represent bits of information about that object. Commands don't have to parse these objects to find data, because .Net understands the object structure and can simply retrieve bits of information by referring to the property names.

[^4-9]: One of the first oblique references to what became PowerShell Remoting, which is indeed a web service based on WS-MAN (Web Services for Management). 

[^4-10]: PowerShell never really went with specific base classes for these different scenarios, but this is the origin of PowerShell's standardized list of verbs to be used in cmdlet names. This concept also drove the creation of the PSProvider and PSDrive abstraction, wherein any data store could be exposed as a "disk drive," thus enabling a standardized set of commands to manipulate any data store so exposed.
