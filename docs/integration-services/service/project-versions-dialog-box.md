---
title: "Cuadro de diálogo versiones del proyecto | Documentos de Microsoft"
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.ssis.ssms.isprojectprop.versions.f1
ms.assetid: a48a387c-2e70-45bc-be2e-26e57a9bb2c4
caps.latest.revision: 9
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: bdf9a0d6fa3ae9a022b720ff0bac003cd65c00db
ms.contentlocale: es-es
ms.lasthandoff: 08/03/2017

---
# <a name="project-versions-dialog-box"></a>Cuadro de diálogo Versiones del proyecto
  Use el cuadro de diálogo **Versiones del proyecto** para ver las versiones de un proyecto y restaurar una versión anterior.  
  
 También puede ver las versiones anteriores en la vista [catalog.object_versions &#40;base de datos de SSISDB&#41;](../../integration-services/system-views/catalog-object-versions-ssisdb-database.md) y usar el procedimiento almacenado [catalog.restore_project &#40;base de datos de SSISDB&#41;](../../integration-services/system-stored-procedures/catalog-restore-project-ssisdb-database.md) para restaurar versiones anteriores.  
  
 **¿Qué desea hacer?**  
  
-   [Abrir el cuadro de diálogo Versiones del proyecto](#open_dialog)  
  
-   [Restaurar una versión del proyecto](#restore)  
  
##  <a name="open_dialog"></a> Abrir el cuadro de diálogo Versiones del proyecto  
  
1.  En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conéctese al servidor de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .  
  
     Es decir, conéctese a la instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que hospeda la base de datos de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .  
  
2.  En el Explorador de objetos, expanda el árbol para que se muestre el nodo **Catálogos de Integration Services** .  
  
3.  Expanda el nodo **Catálogos de Integration Services** para mostrar el nodo de **SSISDB** .  
  
4.  El nodo de **SSISDB** contiene una o varias carpetas y cada una de ellas contiene uno o más proyectos. Expanda la carpeta que contiene el proyecto que le interesa.  
  
5.  Haga clic con el botón derecho en el proyecto y, después, haga clic en **Versiones**.  
  
 En el cuadro de diálogo **Versiones del proyecto** , la tabla **Versiones** muestra la lista de versiones del proyecto que se han implementado en el servidor, con la fecha y hora en que se implementaron, así como la fecha y hora en que se restauraron (en su caso), la descripción de la versión y un identificador de versión. Actualmente la versión activa se indica con una marca de verificación de la columna **Actual** de la tabla.  
  
##  <a name="restore"></a> Restaurar una versión del proyecto  
 Para restaurar una versión anterior de un proyecto, seleccione la versión en la tabla **Versiones** y haga clic en **Restaurar a la versión seleccionada**. El proyecto se restaura a la versión seleccionada y esa versión se indica con una marca de verificación en la columna **Actual** de la tabla **Versiones** .  
  
  