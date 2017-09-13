---
title: "Lección 3: Agregar un registro con SSIS | Documentos de Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: get-started-article
applies_to:
- SQL Server 2016
ms.assetid: 64cd24cc-ba8e-4bd7-b10b-6b80d8b04af6
caps.latest.revision: 25
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 0bfc02e0c5930fca3dec339274167cbad5716461
ms.contentlocale: es-es
ms.lasthandoff: 08/03/2017

---
# <a name="lesson-3-add-logging-with-ssis"></a>Lección 3: Agregar registro con SSIS
[!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] incluye características de registro que permiten supervisar y solucionar los problemas de ejecución de paquetes mediante el seguimiento de eventos de tarea y de contenedor. La características de registro son flexibles, pueden habilitarse en el nivel de paquete o en tareas y contendores individuales del paquete. Puede seleccionar qué eventos deben registrarse y crear varios registros para un único paquete.  
  
El registro lo proporciona un proveedor de registro. Cada proveedor de registro puede escribir información de registro en distintos formatos y tipos de destino. [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] proporciona los siguientes proveedores de registro:  
  
-   Archivo de texto  
  
-   [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)]  
  
-   Registro de eventos de Windows  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]  
  
-   Archivo XML  
  
En esta lección, creará una copia del paquete que creó en la [Lección 2: Agregar bucles con SSIS](../integration-services/lesson-2-adding-looping-with-ssis.md). Utilizando este nuevo paquete, luego agregará y configurará el registro para supervisar eventos específicos durante la ejecución del paquete. Si no ha finalizado cualquiera de las lecciones anteriores, también puede copiar el paquete de la lección 2 finalizada incluido en el tutorial.  
  
> [!IMPORTANT]  
> Para este tutorial, se necesita la base de datos de ejemplo **AdventureWorksDW2012** . Para obtener más información sobre cómo instalar e implementar **AdventureWorksDW2012**, [ejemplos de producto de Reporting Services en CodePlex](http://go.microsoft.com/fwlink/p/?LinkID=526910).  
  
## <a name="lesson-tasks"></a>Tareas de la lección  
Esta lección contiene las siguientes tareas:  
  
-   [Paso 1: Copiar el paquete de la lección 2](../integration-services/lesson-3-1-copying-the-lesson-2-package.md)  
  
-   [Paso 2: Agregar y configurar el registro](../integration-services/lesson-3-2-adding-and-configuring-logging.md)  
  
-   [Paso 3: Probar el paquete del Tutorial lección 3](../integration-services/lesson-3-3-testing-the-lesson-3-tutorial-package.md)  
  
## <a name="start-the-lesson"></a>Iniciar la lección  
[Paso 1: Copiar el paquete de la lección 2](../integration-services/lesson-3-1-copying-the-lesson-2-package.md)  
  
  
  
