# The Monad Manifesto - Annotated

by Jeffrey Snover
as annotated by the PowerShell Community

---

Este proyecto está destinado a preservar [The Monad Manifesto](http://www.jsnover.com/blog/2011/10/01/monad-manifesto/), un documento escrito por el inventor de Microsoft Windows PowerShell [Jeffrey Snover](https://social.technet.microsoft.com/profile/Jeffrey%20Snover%20Windows%20Server) en Microsoft en 2002. La idea de este proyecto fue del autor de Pluralsight [Tim Warner](http://www.pluralsight.com/author/tim-warner), con las anotaciones iniciales que hicieroen Tim y el Microsoft MVP [Don Jones](https://twitter.com/concentrateddon).

El Manifiesto original era un documento prospectivo, anterior a la publicación pública de PowerShell por alrededor de 4 años. En los años transcurridos desde el lanzamiento de PowerShell [2006](http://blogs.msdn.com/b/powershell/archive/2006/11/14/windows-powershell-1-0-released.aspx), el producto ha evolucionado sustancialmente, pero siempre alrededor de los conceptos  descritos en el Manifiesto.

Consideramos que no sólo es importante conservar el documento con fines históricos, sino también anotar y ampliar los diversos conceptos que introduce. Intentaremos vincular las referencias de las tecnologías reales que el Manifiesto predijo y proporcionar explicaciones contextuales en torno a algunas de las directivas del Manifiesto.

Encontrará [^1] notas de pie de página en el texto. Éstas son una característica de [MultiMarkdown](http://fletcherpenney.net/multimarkdown/)que no son compatibles con nuestra plataforma de publicación, pero están destinadas a vincular a las notas de pie de página correspondientes en la parte inferior de la página. En algunos casos, estas son las notas originales de Jeffrey marcadas como "ORIGINAL" para separarlas de las notas a pie de página que nosotros hemos añadido.

---

This guide is released under the Creative Commons Attribution-NoDerivs 3.0 Unported License. The authors encourage you to redistribute this file as widely as possible, but ask that you do not modify the document.

**Was this book helpful?** The author(s) kindly ask(s) that you make a tax-deductible (in the US; check your laws if you live elsewhere) donation of any amount to [The DevOps Collective](https://devopscollective.org/donate/) to support their ongoing work.

**Check for Updates!** Our ebooks are often updated with new and corrected content. We make them available in three ways:

* Our main, authoritative [GitHub organization](https://github.com/devops-collective-inc), with a repo for each book. Visit https://github.com/devops-collective-inc/
* Our [GitBook page](https://www.gitbook.com/@devopscollective), where you can browse books online, or download as PDF, EPUB, or MOBI. Using the online reader, you can link to specific chapters. Visit https://www.gitbook.com/@devopscollective
* On [LeanPub](https://leanpub.com/u/devopscollective), where you can download as PDF, EPUB, or MOBI (login required), and "purchase" the books to make a donation to DevOps Collective. You can also choose to be notified of updates. Visit https://leanpub.com/u/devopscollective

GitBook and LeanPub have slightly different PDF formatting output, so you can choose the one you prefer. LeanPub can also notify you when we push updates. Our main GitHub repo is authoritative; repositories on other sites are usually just mirrors used for the publishing process. GitBook will usually contain our latest version, including not-yet-finished bits; LeanPub always contains the most recent "public release" of any book.
