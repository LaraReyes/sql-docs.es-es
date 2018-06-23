---
title: Actualizar datos (complemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58dbe99a-288d-4f1c-9cd5-704d6836c945
caps.latest.revision: 9
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 126c696da22e2b3e483ae7fb4692469d617f125a
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36108976"
---
# <a name="refreshing-data-mds-add-in-for-excel"></a>Actualizar datos (complemento MDS para Excel)
  En [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], actualice los datos si desea obtener la información más reciente del repositorio MDS sin abrir una nueva hoja de cálculo. Puede actualizar todas las celdas o una selección de ellas. Esto puede resultar útil si ha insertado columnas con fórmulas personalizadas u otros datos que no se administran en MDS y desea mantenerlos.  
  
## <a name="when-you-can-refresh-mds-managed-data"></a>Cuándo se pueden actualizar datos administrados por MDS  
 Puede actualizar los datos administrados por MDS en una hoja de cálculo activa si esta ya contiene datos administrados por MDS. Si ha cambiado los valores de atributo o ha agregado miembros a la hoja de cálculo, debe publicar los cambios para poder actualizar.  
  
## <a name="refreshing-a-selection"></a>Actualizar una selección  
 Puede tener la opción de actualizar todas las celdas o solo las seleccionadas. Las celdas seleccionadas deben ser contiguas. Si se selecciona un conjunto de celdas contiguas, todas las celdas administradas de MDS de ese conjunto se actualizarán para que muestren los valores actualmente almacenados en el servidor. Las filas y columnas sin cambios que no administre MDS no se ven afectadas de ningún modo.  
  
## <a name="what-happens-when-you-refresh-mds-managed-data"></a>Lo que sucede al actualizar datos administrados por MDS  
 Al actualizar datos en el [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], lo que ocurre en los datos administrados por MDS de la hoja depende de lo que ha cambiado en el repositorio MDS desde que se cargaron los datos por última vez.  
  
-   Si se han agregado nuevos miembros al repositorio, se agregan al final de la hoja de cálculo y están resaltados en verde.  
  
-   Si se eliminaron miembros del repositorio, se eliminan de la hoja de cálculo.  
  
-   Si un valor de atributo ha cambiado en el repositorio MDS, el valor de la hoja de cálculo se actualiza con el valor del repositorio MDS. El color de la celda no cambia.  
  
> [!WARNING]  
>  -   En la hoja de cálculo activa, si existen datos no administrados en las filas situadas bajo los datos administrados por MDS, los datos no administrados pueden sobrescribirse. Esto ocurre cuando se actualiza la hoja y se agregan nuevas filas de datos administrados por MDS, que se superponen a los datos no administrados.  
> -   Al actualizar, se eliminan los comentarios de las celdas administradas por MDS.  
  
## <a name="how-to-refresh-mds-managed-data"></a>Cómo actualizar los datos administrados por MDS  
 En el grupo de **Conectar y cargar** en la cinta de opciones, el botón **Actualizar** tiene dos opciones, **Actualizar todo** y **Actualizar selección**. La acción predeterminada del botón de la cinta de opciones es **Actualizar todo**. Para actualizar la hoja completa con valores desde el servidor, haga clic en el botón de **Actualizar** o elija la opción **Actualizar todo** . Para actualizar solo algunas de las celdas de una hoja, seleccione las celdas (debe ser una selección contigua) y elija la opción **Actualizar selección** .  
  
## <a name="related-tasks"></a>Related Tasks  
  
|Descripción de la tarea|Tema|  
|----------------------|-----------|  
|Crear una conexión a una base de datos de [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .|[Conectarse a un repositorio MDS &#40;complemento MDS para Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md)|  
|Cargar datos MDS en Excel.|[Cargar datos de MDS en Excel](export-data-to-excel-from-master-data-services.md)|  
  
## <a name="related-content"></a>Contenido relacionado  
  
-   [Conexiones &#40;complemento MDS para Excel&#41;](connections-mds-add-in-for-excel.md)  
  
-   [Cargar datos &#40;complemento MDS para Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md)  
  
-   [Complemento de Master Data Services para Microsoft Excel](master-data-services-add-in-for-microsoft-excel.md)  
  
  