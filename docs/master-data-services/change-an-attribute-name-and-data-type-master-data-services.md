---
title: Cambiar el nombre de atributo y un tipo de datos (Master Data Services) | Documentos de Microsoft
ms.custom:
- SQL2016_New_Updated
ms.date: 03/15/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- master-data-services
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- attributes [Master Data Services], changing name
ms.assetid: d348f238-f59d-41c7-ad20-3ccd55bfd9e5
caps.latest.revision: 9
author: sabotta
ms.author: carlasab
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: a1c9e79f7485db3577a17147e2d187d2acc6c521
ms.contentlocale: es-es
ms.lasthandoff: 08/02/2017

---
# <a name="change-an-attribute-name-and-data-type-master-data-services"></a>Cambiar el nombre y el tipo de datos de un atributo (Master Data Services)
  En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], puede cambiar el nombre de un atributo.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar este procedimiento:  
  
-   Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .  
  
-   Debe ser administrador de modelo. Para obtener más información, vea [Administradores &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md).  
  
### <a name="to-change-an-attribute-name-and-type"></a>Cambio del nombre y del tipo de un atributo  
  
1.  En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.  
  
2.  En la página **Manage Model** (Administrar modelo), seleccione un modelo de la cuadrícula y después haga clic en **Entidades**.  
  
3.  En la página **Manage Entity** (Administrar entidad), seleccione la fila de la entidad para la que desea crear un atributo.  
  
4.  Haga clic en **Atributos**.  
  
5.  En la página **Administrar atributos** , realice una de las siguientes acciones.  
  
    -   Si el atributo es para miembros hoja, seleccione **Hoja** en el cuadro de lista **Member Types** (Tipos de miembro).  
  
    -   Si el atributo es para miembros consolidados, seleccione **Consolidado** en el cuadro de lista **Member Types** (Tipos de miembro).  
  
    -   Si el atributo es para colecciones, seleccione **Colección** en el cuadro de lista **Member Types** (Tipos de miembro).  
  
6.  Seleccione la fila del atributo que desea editar y después haga clic en **Editar**.  
  
7.  En el cuadro **Nombre** , escriba el nombre actualizado del atributo. Para ver una lista de palabras que no se deben usar como nombres de atributo, consulte [Palabras reservadas &#40;Master Data Services&#41;](../master-data-services/reserved-words-master-data-services.md).  
  
8.  En la lista **Tipo de atributo** , seleccione otro tipo.  
  
9. Haga clic en **Guardar**.  
  
## <a name="see-also"></a>Vea también  
 [Crear un atributo de texto &#40; Master Data Services &#41;](../master-data-services/create-a-text-attribute-master-data-services.md)   
 [Eliminar un atributo &#40; Master Data Services &#41;](../master-data-services/delete-an-attribute-master-data-services.md)   
 [Atributos &#40; Master Data Services &#41;](../master-data-services/attributes-master-data-services.md)  
  
  