---
title: "Cuadro de diálogo Establecer valor de parámetro | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-non-specified
ms.prod_service: integration-services
ms.service: 
ms.component: service
ms.reviewer: 
ms.suite: sql
ms.technology: integration-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ce9c2201-4e9a-4495-948f-b68deeaa7955
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 537e5e3ca57a706ad3267a3a445263c8772dd984
ms.sourcegitcommit: 6bbecec786b0900db86203a04afef490c8d7bfab
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2017
---
# <a name="set-parameter-value-dialog-box"></a>Cuadro de diálogo Establecer valor de parámetro
  Utilice el cuadro de diálogo **Establecer valor de parámetro** para establecer los valores de los parámetros y las propiedades de administrador de conexiones, para los proyectos y los paquetes.  
  
 **¿Qué desea hacer?**  
  
-   [Abrir el cuadro de diálogo Establecer valor de parámetro](#open_dialog)  
  
-   [Configurar las opciones](#option)  
  
##  <a name="open_dialog"></a> Abrir el cuadro de diálogo Establecer valor de parámetro  
  
1.  En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conéctese al servidor de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .  
  
     Se conectará a la instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que hospeda la base de datos SSISDB.  
  
2.  En el Explorador de objetos, expanda el árbol para que se muestre el nodo **Catálogos de Integration Services** .  
  
3.  Expanda el nodo **SSISDB** .  
  
4.  Haga clic con el botón derecho en un paquete o proyecto, haga clic en **Configurar**y, luego, haga clic en el botón de puntos suspensivos de la pestaña **Parámetros** o en la pestaña **Administradores de conexiones** .  
  
##  <a name="option"></a> Configurar las opciones  
 **Parámetro**  
 Muestra el nombre de parámetro.  
  
 **Tipo**  
 Enumera el tipo de datos del valor de parámetro.  
  
 **Description**  
 Muestra una descripción opcional del parámetro.  
  
 **Editar valor**  
 Seleccione esta opción para editar el valor del parámetro.  
  
 **Usar valor predeterminado del paquete**  
 Seleccione esta opción para usar el valor predeterminado del parámetro almacenado en este paquete.  
  
 **Usar la variable de entorno**  
 Seleccione esta opción para usar un valor de variable almacenado en el entorno, al que hace referencia el proyecto o el paquete. Para agregar una referencia de entorno a un proyecto o a un paquete, use el cuadro de diálogo **Configurar** . Para más información, consulte [Configure Dialog Box](../../integration-services/catalog/configure-dialog-box.md).  
  
  