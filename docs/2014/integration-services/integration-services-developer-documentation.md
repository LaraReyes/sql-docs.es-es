---
title: Developer&#39;guía (Integration Services) | Documentos de Microsoft
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- docset-sql-devref
- integration-services
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Integration Services, programming
- SSIS, programming
- SQL Server Integration Services, programming
- packages [Integration Services], programming
ms.assetid: 60fe148b-a7c4-4289-ae3e-2e949fc1886c
caps.latest.revision: 76
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 7649030fb22c9e0786d481f34a29974dcddbe863
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36104081"
---
# <a name="developer39s-guide-integration-services"></a>Developer&#39;guía (Integration Services)
  [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] incluye un modelo de objetos completamente reescrito, que se ha mejorado con muchas características que consiguen que la extensión y la programación de paquetes resulten más sencillas, flexibles y eficaces. Los desarrolladores pueden extender y programar prácticamente cualquier aspecto de los paquetes de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].  
  
 Como desarrollador de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], existen dos enfoques fundamentales que puede aplicar en la programación de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:  
  
-   Puede extender los paquetes escribiendo componentes que pasan a estar disponibles en el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] para proporcionar funcionalidad personalizada en un paquete.  
  
-   Puede crear, configurar y ejecutar paquetes mediante programación desde sus propias aplicaciones.  
  
 Si los componentes integrados en [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no cumplen sus requisitos, puede ampliar la potencia de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] codificando sus propias extensiones. En este enfoque, tiene dos opciones diferentes:  
  
-   Para el uso ad hoc en un paquete único, puede crear una tarea personalizada escribiendo código en la tarea Script o bien crear un componente de flujo de datos personalizado escribiendo código en el componente de script, que puede configurar como origen, transformación o destino. Estos eficaces contenedores escriben automáticamente el código de la infraestructura y permiten centrarse exclusivamente en desarrollar la funcionalidad personalizada; sin embargo, no se reutilizan con facilidad en otro lugar.  
  
-   Para el uso en varios paquetes, puede crear extensiones de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] personalizadas como administradores de conexión, tareas, enumeradores, proveedores de registro y componentes de flujo de datos. El modelo de objetos de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] administrado contiene clases base que proporcionan un punto de inicio y consiguen que el desarrollo de extensiones resulte más fácil que nunca.  
  
 Si desea crear paquetes de forma dinámica o administrar y ejecutar paquetes de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] fuera del entorno de desarrollo, puede manipular los paquetes mediante programación. Puede cargar, modificar y ejecutar los paquetes existentes o bien puede crear y ejecutar paquetes completamente nuevos mediante programación. En este enfoque, tiene un intervalo de opciones continuo:  
  
-   Cargar y ejecutar un paquete existente sin modificarlo.  
  
-   Cargar un paquete existente, volver a configurarlo (por ejemplo, especificar un origen de datos diferente) y ejecutarlo.  
  
-   Crear un nuevo paquete, agregar y configurar componentes, realizar cambios objeto a objeto y propiedad a propiedad, guardarlo y ejecutarlo.  
  
 Estos enfoques de la programación de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] se describen en esta sección y se muestran con ejemplos.  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general sobre la programación de Integration Services](integration-services-programming-overview.md)  
 Describe los roles de flujo de control y flujo de datos en el desarrollo de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].  
  
 [Descripción de las transformaciones sincrónicas y asincrónicas](understanding-synchronous-and-asynchronous-transformations.md)  
 Describe la distinción importante entre las salidas sincrónicas y asincrónicas, y los componentes que las utilizan en el flujo de datos.  
  
 [Trabajar con administradores de conexiones mediante programación](working-with-connection-managers-programmatically.md)  
 Muestra los administradores de conexiones que puede usar en el código administrado y los valores que devuelven cuando en el código se llama al método `AcquireConnection`.  
  
 [Ampliar paquetes con scripting](extending-packages-scripting/extending-packages-with-scripting.md)  
 Describe cómo extender el flujo de control mediante la tarea Script o el flujo de datos mediante el componente de script.  
  
 [Ampliar paquetes con objetos personalizados](extending-packages-custom-objects/extending-packages-with-custom-objects.md)  
 Describe cómo crear y programar tareas personalizadas de programa, componentes de flujo de datos y otros objetos de paquete para su uso en varios paquetes.  
  
 [Compilar paquetes mediante programación](building-packages-programmatically/building-packages-programmatically.md)  
 Describe cómo crear, configurar y guardar los paquetes de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] mediante programación.  
  
 [Ejecutar y administrar paquetes mediante programación](run-manage-packages-programmatically/running-and-managing-packages-programmatically.md)  
 Describe cómo enumerar, ejecutar y administrar paquetes de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] mediante programación.  
  
## <a name="reference"></a>Referencia  
 [Referencia de errores y mensajes de Integration Services](integration-services-error-and-message-reference.md)  
 Enumera los códigos de error predefinidos de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], junto con sus nombres simbólicos y descripciones.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Herramientas para solucionar problemas del desarrollo de paquetes](troubleshooting/troubleshooting-tools-for-package-development.md)  
 Describe las características y herramientas que ofrece [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para solucionar problemas de los paquetes durante el desarrollo.  
  
## <a name="external-resources"></a>Recursos externos  
  
-   Ejemplos de CodePlex, en la página [Integration Services Product Samples](http://go.microsoft.com/fwlink/?LinkID=131204)de www.codeplex.com/MSFTISProdSamples.  
  
## <a name="see-also"></a>Vea también  
 [SQL Server Integration Services](sql-server-integration-services.md)  
  
  