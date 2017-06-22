# Capítulo 1 - ¿Qué es Monad?
___
Monad [^1-1] [^1-2] es la próxima generación de plataformas para la automatización administrativa. Monad resuelve los problemas de gestión tradicionales aprovechando la [Plataforma .NET](http://bit.ly/1PAsRao). Desde el primer prototipo (limitado), se pueden resaltar beneficios significativos para desarrolladores, testers, usuarios avanzados y administradores. Monad aprovecha [^ 1-6] el [.NET Common Runtime](http://bit.ly/1Q0TrV3) Runtime para proporcionar un potente, consistente, intuitivo, extensible y útil conjunto de herramientas que reducen los costos de administración y hacen que la vida de los no programadores sea mucho más sencilla. 

Monad consta de:

1. [Monad Automation Model (MAM)](): Un modelo de automatización basado en [clases .NET](http://bit.ly/1R9oPTO), métodos y atributos para producir [Cmdlets](https://msdn.microsoft.com/en-us/library/ms714395(v=vs.85).aspx).[^1-3]
2. [Monad Shell (MSH)](): Un entorno de ejecución de scripts basado en .NET para exponer los Cmdlets como herramientas de línea de comandos de [API](https://msdn.microsoft.com/en-us/library/ms123401.aspx) y un shell de línea de comandos programable e interactivo.
3. [Monad Management Models (MMM)](): El conjunto con las clases de base de código administrado (o interfaces) para implementar escenarios de administración específicos y herramientas administrativas in-the-box para ejecutar esos escenarios.  
4. [Monad Remote Scripting (MRS)](): Conjunto de componentes basados en  [Web Services](https://msdn.microsoft.com/en-us/library/ms950421.aspx) que permiten ejecutar secuencias de comandos remotamente en muchas máquinas [^1-4].
5. [Monad Management Console (MMC)](): Un modelo basado en .NET y un conjunto de servicios para la creación de GUIs de administración sobre [MSH](https://technet.microsoft.com/en-us/magazine/2005.11.scripting.aspx) exponiendo todas las interacciones de GUI como secuencias de comandos visibles por el usuario [^1-5].

Este [white paper](https://en.wikipedia.org/wiki/White_paper) presenta el enfoque tradicional de la automatización administrativa, sus fortalezas y deficiencias. A continuación, se presenta una visión general de los principales componentes de Monad. Un conjunto de [propuestas de valor](https://en.wikipedia.org/wiki/Value_proposition) se articula entonces para las audiencias objetivo de Monad.

___

**Notas:**

[^1-1]: (ORIGINAL) Este no es un documento técnico de Windows PowerShell ni es una descripción precisa de cómo funciona [V1.0](http://blogs.msdn.com/b/powershell/archive/2006/11/14/windows-powershell-1-0-released.aspx). Esta es una versión del original Manifiesto de Monad que articuló la visión a largo plazo y comenzó el esfuerzo de desarrollo que se convirtió en [PowerShell](http://bit.ly/1Q0TyzZ). Muchos de los elementos descritos en este documento han sido liberados y otros han proporcionado una buena hoja de ruta para el futuro. El documento se ha actualizado para su publicación. La información confidencial ha sido eliminada y los ejemplos se actualizan para reflejar la sintaxis actual.

[^1-2]: (ORIGINAL) [Monads](https://en.wikipedia.org/wiki/Monadology) are [Leibniz’s](https://en.wikipedia.org/wiki/Gottfried_Wilhelm_Leibniz) term for the fundamental unit of existence that aggregates into compounds to implement a purpose. In this philosophy, everything is a composition of Monads. This captures what we want to achieve with [composable](https://en.wikipedia.org/wiki/Composability) management. More information on Monadology can be found at: [http://www.wise.virginia.edu/philosophy/phil206/Leibniz.html](http://www.wise.virginia.edu/philosophy/phil206/Leibniz.html)

[^1-3]: Version 1 of PowerShell shipped in 2006, and provided the implementation for these cmdlets. Cmdlets today are written in [.NET languages](https://en.wikipedia.org/wiki/List_of_CLI_languages), and consist of a single class per cmdlet. PowerShell provides a base class that does much of the heavy lifting; developers define properties of the class that become parameters, and override specific methods to participate in the pipeline lifecycle. Cmdlets, along with the overall environment, were the first of four major vision points proposed in the Manifesto.

[^1-4]: Remoting was introduced in PowerShell [version 2](http://blogs.msdn.com/b/powershell/archive/2009/07/23/windows-powershell-2-0-rtm.aspx), which shipped in the box with Windows Vista and Windows Server 2008. [Remoting](https://technet.microsoft.com/en-us/magazine/ff700227.aspx) is the second of the four major vision points proposed in the Manifesto.

[^1-5]: Although never exposed as an [MMC](https://msdn.microsoft.com/en-us/library/bb742441.aspx) per se, PowerShell's engine was implemented as a .NET class. Any .NET application can instantiate the engine, run commands, and translate the output into a GUI display. [Exchange Server 2007](https://technet.microsoft.com/en-us/magazine/2006.12.managementshell.aspx) was the first product to do so, and remains one of the best examples of the "full-on PowerShell approach" to administration.

[^1-6]: It should be noted that PowerShell very nearly didn't exist because of its dependency on .NET. At the time, in 2004-2006, a startling number of high-profile managed code projects were failing, contributing to the delays in Windows Vista. Running around Microsoft preaching about some management scripting language written in .NET wasn't politically correct at the time. In fact, it was so risky that the Exchange Server team actually built in _entire intermediate API_ under their PowerShell cmdlets, on the theory that they could trash the cmdlets and switch to something else more easily, if needed.



