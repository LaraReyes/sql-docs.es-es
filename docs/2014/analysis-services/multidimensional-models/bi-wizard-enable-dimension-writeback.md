---
title: Habilitar la reescritura de dimensiones | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying dimensions
- writeback [Analysis Services], setting up
- dimensions [Analysis Services], Business Intelligence enhancements
- Business Intelligence enhancements [Analysis Services], writeback
- dimensions [Analysis Services], writeback
- writeback [Analysis Services]
- dimensions [Analysis Services], modifying
- manual dimension structure modifications
ms.assetid: a4b5eb5a-366d-4fc8-ad0d-5bdb8e7b4163
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: e9236bfbd945386aa249291b490ad41680a3ff5d
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48171655"
---
# <a name="enable-dimension-writeback"></a>Habilitar reescritura en la dimensión
  Agregar la mejora de reescritura de dimensiones a un cubo o dimensión para permitir que los usuarios modifiquen manualmente la estructura y los miembros de la dimensión. Las actualizaciones de una dimensión habilitada para escritura se registran directamente en la tabla de dimensiones. Esta mejora cambia la configuración de la propiedad `WriteEnabled` para una dimensión.  
  
 Para agregar la reescritura de dimensiones, se usa el Asistente de Business Intelligence y se selecciona la opción **Habilitar reescritura en la dimensión** en la página **Elegir mejora** . Este asistente le guía por los pasos para seleccionar la dimensión a la que desee aplicar la reescritura de dimensiones y establecer esta opción para la dimensión seleccionada.  
  
> [!NOTE]  
>  La reescritura solo es compatible para bases de datos relacionales de SQL Server y data marts.  
  
## <a name="selecting-a-dimension"></a>Seleccionar una dimensión  
 En la primera página **Habilitar reescritura en la dimensión** del asistente, se especifica la dimensión a la que se desea aplicar la reescritura. La mejora de reescritura de dimensiones agregada a esta dimensión seleccionada produce cambios en la dimensión. Estos cambios son heredados por todos los cubos que incluyan la dimensión seleccionada.  
  
## <a name="setting-dimension-writeback-capability"></a>Establecer la capacidad de reescritura de dimensiones  
 En la segunda página **Habilitar reescritura en la dimensión** del asistente se establece la opción **Habilitar reescritura en la dimensión** . Al seleccionar esta opción establece automáticamente la `WriteEnabled` propiedad de la dimensión a `True`. Si se desactiva automáticamente esta opción establece la propiedad en `False`.  
  
## <a name="remarks"></a>Comentarios  
 Al crear un nuevo miembro, debe incluir todos los atributos en una dimensión. No puede insertar un miembro sin especificar un valor para el atributo clave de la dimensión. Por lo tanto, la creación de miembros está sujeta a las restricciones (como los valores de clave no nulos) definidas en la tabla de la dimensión. También debe considerar las columnas especificadas opcionalmente por las propiedades de dimensión, como las columnas especificadas en el `CustomRollupColumn`, `CustomRollupPropertiesColumn` o `UnaryOperatorColumn` propiedades de la dimensión.  
  
> [!WARNING]  
>  Si usa SQL Azure como origen de datos para realizar la reescritura en una base de datos de Analysis Services, se produce un error en la operación. Esto es así por cuestiones de diseño, porque la opción del proveedor que permite que haya varios conjuntos de resultados (MARS) activos no está activada de forma predeterminada.  
>   
>  La solución es agregar el valor siguiente en la cadena de conexión, para admitir MARS y habilitar la reescritura:  
>   
>  `"MultipleActiveResultSets=True"`  
>   
>  Para más información, vea [Utilizar conjuntos de resultados activos múltiples &#40;MARS&#41;](../../relational-databases/native-client/features/using-multiple-active-result-sets-mars.md).  
  
## <a name="see-also"></a>Vea también  
 [Dimensiones habilitadas para escritura](../multidimensional-models-olap-logical-dimension-objects/write-enabled-dimensions.md)  
  
  
