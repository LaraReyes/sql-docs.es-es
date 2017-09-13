---
title: Editar modelo (Master Data Services) | Documentos de Microsoft
ms.custom:
- SQL2016_New_Updated
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- master-data-services
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- models [Master Data Services], changing name
ms.assetid: 399eed32-7c61-4239-9c06-996a65219518
caps.latest.revision: 9
author: sabotta
ms.author: carlasab
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 08291f09ed7bc172fe22534e82b79ecc47ce55e1
ms.contentlocale: es-es
ms.lasthandoff: 08/02/2017

---
# <a name="edit-model-master-data-services"></a>Editar modelo (Master Data Services)
  En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], puede cambiar el nombre y la descripción de un modelo e indicar el número de días que desea conservar los registros de transacciones.  
  
 Para obtener más información, consulte [Transacciones &#40;Master Data Services&#41;](../master-data-services/transactions-master-data-services.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar este procedimiento:  
  
-   Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .  
  
-   Debe ser administrador de modelo. Para obtener más información, vea [Administradores &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md).  
  
### <a name="to-change-a-model"></a>Para cambiar un modelo  
  
1.  En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.  
  
2.  En la página **Vista de modelo** , en la barra de menús, seleccione **Administrar** y haga clic en **Modelos**.  
  
3.  En la cuadrícula de la página **Administrar modelos** , seleccione la fila correspondiente al modelo con el nombre o la descripción que quiere cambiar.  
  
4.  Haga clic en **Editar**.  
  
5.  En el cuadro **Nombre** , escriba el nombre actualizado del modelo.  
  
6.  En el campo **Descripción** , escriba la descripción del modelo actualizada.  
  
7.  En el campo **Log Retention Days** (Días de retención del registro), seleccione una de las opciones de retención de datos de registro. El valor predeterminado es **Configuración del sistema**, lo que indica que el valor se hereda de la configuración del sistema del [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)]. Para obtener más información, vea [Configuración del sistema &#40;Master Data Services&#41;](../master-data-services/system-settings-master-data-services.md).  
  
     Para reemplazar la configuración del sistema sin quitar los datos del registro de transacciones, seleccione **NO**. Para conservar solo los datos de registro de hoy y truncar los datos de registro de todos los días anteriores, seleccione **SÍ** y establezca el campo **Días** en 0. Para conservar los datos de registro durante un número especificado de días, seleccione **Sí** y establezca el campo **Días** en el número de días.  
  
8.  Haga clic en **Guardar modelo**.  
  
 La columna **Estado** de la cuadrícula muestra el estado de la operación en el modelo. Al hacer clic en el **Guardar modelo** botón, el ![actualizar](../master-data-services/media/mds-model-status-updating.png "actualizar") imagen se muestra, lo que indica que se está actualizando el modelo. Si hay errores al crear o editar un modelo, el ![Error](../master-data-services/media/mds-model-status-error.png "Error") se muestra la imagen. De lo contrario, el estado es correcto y se muestra la imagen ![Aceptar](../master-data-services/media/mds-model-status-ok.png "Aceptar") .  
  
## <a name="see-also"></a>Vea también  
 [Crear un modelo de &#40; Master Data Services &#41;](../master-data-services/create-a-model-master-data-services.md)   
 [Eliminar un modelo de &#40; Master Data Services &#41;](../master-data-services/delete-a-model-master-data-services.md)   
 [Modelos &#40;Master Data Services&#41;](../master-data-services/models-master-data-services.md)  
  
  