---
title: "Agregar minigráficos y barras de datos (generador de informes y SSRS) | Documentos de Microsoft"
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b297c2e-d48b-41b0-aabd-29680cdcdb05
caps.latest.revision: 8
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: a9f084fc55a0f3011a40c6f2d8a2cfcdf61dc9f2
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2017

---
# <a name="add-sparklines-and-data-bars-report-builder-and-ssrs"></a>Agregar minigráficos y barras de datos (Generador de informes y SSRS)
  Los minigráficos y barras de datos son gráficos pequeños y accesorios que comunican mucha información con pocos detalles. Para más información, vea [Minigráficos y barras de datos &#40;Generador de informes y SSRS&#41;](../../reporting-services/report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).  
  
 En los informes paginados de [!INCLUDE[ssRSnoversion_md](../../includes/ssrsnoversion-md.md)] , los minigráficos y las barras de datos suelen colocarse en celdas de una tabla o matriz. Normalmente, los minigráficos solo muestran una serie cada uno. Las barras de datos puede contener uno o varios puntos de datos. El efecto de los minigráficos y las barras de datos deriva de la repetición de la información de la serie para cada fila de la tabla o matriz.  
  
## <a name="to-add-a-sparkline-or-data-bar-to-a-table-or-matrix"></a>Para agregar un minigráfico o una barra de datos a una tabla o matriz  
  
1.  Si aún no lo ha hecho, cree una [tabla](../../reporting-services/report-design/tables-report-builder-and-ssrs.md) o [matriz](../../reporting-services/report-design/create-a-matrix-report-builder-and-ssrs.md) con los datos que quiera mostrar.  
  
2.  Inserte una columna en la tabla o matriz. Para obtener más información, vea [Insertar o eliminar una columna &#40;Generador de informes y SSRS&#41;](../../reporting-services/report-design/insert-or-delete-a-column-report-builder-and-ssrs.md).  
  
3.  En la pestaña **Insertar** , haga clic en **Minigráfico** o en **Barra de datos**y, a continuación, haga clic en una celda de la nueva columna.  
  
    > [!NOTE]  
    >  No se pueden colocar minigráficos en un grupo de detalles de una tabla. Deben estar en una celda asociada a un grupo.  
  
4.  En el cuadro de diálogo **Cambiar tipo de minigráfico o barra de datos** , haga clic en el tipo de minigráfico o barra de datos que prefiera y, después, haga clic en **Aceptar**.  
  
5.  Haga clic en el minigráfico o barra de datos.  
  
     El panel **Datos del gráfico** se abre.  
  
6.  En el área **Valores** , haga clic en el signo más ( **) de** Agregar campos**+**y, después, haga clic en el campo cuyos valores quiera incluir en el gráfico.  
  
7.  En el área **Grupos de categorías** , haga clic en el signo más ( **) de** Agregar campos**+**y, después, haga clic en el campo por cuyos valores quiera agrupar.  
  
     Normalmente, para los minigráficos y barras de datos, no se agregará un campo al área **Grupo de series** porque solo se desea una serie para cada fila.  
  
## <a name="see-also"></a>Vea también  
 [Gráficos &#40;Generador de informes y SSRS&#41;](../../reporting-services/report-design/charts-report-builder-and-ssrs.md)   
 [Alinear los datos en un gráfico en una tabla o una matriz &#40;Generador de informes y SSRS&#41;](../../reporting-services/report-design/align-the-data-in-a-chart-in-a-table-or-matrix-report-builder-and-ssrs.md)  
  
  