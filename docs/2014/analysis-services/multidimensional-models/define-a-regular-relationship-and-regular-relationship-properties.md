---
title: Definir una relación normal y las propiedades de relación normal | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
ms.topic: conceptual
helpviewer_keywords:
- granularity attribute
- relationships [Analysis Services], regular relationships
ms.assetid: 840280d8-20c3-46c0-99ea-62479469c36b
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: e0f8c491696ea0ee8c8f8b613fa15110ffb7df69
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48054877"
---
# <a name="define-a-regular-relationship-and-regular-relationship-properties"></a>Definir relaciones normales y propiedades de las relaciones normales
  Al definir una nueva dimensión de cubo o un nuevo grupo de medida, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] intentará detectar si existe una relación normal y, a continuación, establecerá la configuración de uso de la dimensión en `Regular`. Puede ver o modificar una relación de dimensión normal en la pestaña **Uso de dimensiones** del Diseñador de cubos.  
  
 Al definir la relación de una dimensión de cubo con un grupo de medida, también se especifica el atributo de granularidad de esa relación. El atributo de granularidad define el nivel mínimo de detalle disponible en el cubo para dicha dimensión, que suele ser el atributo clave de la dimensión. Sin embargo, en algunos casos, quizás desee establecer la granularidad de determinada dimensión de cubo de determinado grupo de medida en otra granularidad. Por ejemplo, si utiliza un grupo de medida Sales Quotas o Budget, quizás desee establecer el atributo de granularidad de la dimensión Time en el atributo Month, no en el atributo Day. Al especificar que el atributo de granularidad sea distinto del atributo clave, se debe garantizar que los demás atributos de la dimensión estén directa o indirectamente vinculados a este otro atributo por medio de relaciones de atributo. De lo contrario, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] no podrá agregar los datos correctamente.  
  
  
