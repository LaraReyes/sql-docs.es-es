---
title: Metadatos (Master Data Services) | Documentos de Microsoft
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- user-defined metadata [Master Data Services], about user-defined metadata
- metadata [Master Data Services], about metadata
- metadata [Master Data Services]
- user-defined metadata [Master Data Services]
ms.assetid: ac1aabe3-d8d4-4d7a-8954-50ee3c185d81
caps.latest.revision: 7
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 25fa2078127816b2fd9d50bd7bd4c074c3577dae
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36106984"
---
# <a name="metadata-master-data-services"></a>Metadatos (Master Data Services)
  En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], los metadatos definidos por el usuario son la información que se usa para describir los objetos del modelo. Por ejemplo, puede que desee realizar el seguimiento de los propietarios de un modelo o entidad determinados, o realizar el seguimiento de los sistemas de origen que proporcionan los datos a una entidad.  
  
 Metadatos definidos por el usuario se administran mediante un modelo denominado **metadatos**. Este modelo se incluye automáticamente cuando [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] está instalado, y es similar a todos los modelos MDS, salvo que no se puede crear versiones de esta aplicación.  
  
 Después de rellenar el modelo de metadatos con los metadatos definidos por el usuario, puede incluirlo en las vistas de suscripciones, para que lo puedan usar los sistemas suscriptores.  
  
## <a name="metadata-entities"></a>Entidades de metadatos  
 El modelo de metadatos incluye cinco entidades, cada una de las cuales representa un tipo de objeto del modelo de datos maestros que admite los metadatos definidos por el usuario. Por ejemplo, el **definición de metadatos del modelo** entidad contiene miembros que representan los modelos y la **definición de metadatos de atributo** entidad tiene miembros que representan todos los atributos de todos los modelos.  
  
 Para definir los metadatos de un objeto del modelo, rellene uno de estos atributos del miembro. Por ejemplo, en la **definición de metadatos de la entidad** entidad, puede rellenar el atributo de descripción del miembro precio con el texto: **el precio del producto cuando se vende a un cliente**.  
  
 Los miembros del modelo de metadatos se actualizan automáticamente siempre que se agregan o se eliminan los objetos del modelo compatibles con los metadatos definidos por el usuario.  
  
 No se pueden crear versiones del modelo de metadatos, no se pueden agregar ni quitar marcas de versión, ni se puede guardar como un paquete de implementación del modelo. Sin embargo, todas sus demás funciones son las mismas que las de los otros modelos de datos maestros. Por ejemplo, podría implementar un conjunto de reglas de negocios en el modelo Metadatos para aplicar directivas de datos.  
  
## <a name="customizing-your-metadata-model"></a>Personalizar un modelo de metadatos  
 Cada entidad de definición de metadatos incluye los atributos Nombre, Código y Descripción. Puede ser conveniente crear atributos adicionales para describir de forma precisa los objetos de modelo.  
  
 Por ejemplo, podría crear:  
  
-   Un atributo basado en dominio denominado Propietario, que se utiliza para realizar el seguimiento del propietario de cada objeto de modelo.  
  
-   Un atributo de forma libre denominado Fecha de la última revisión, que se utiliza para realizar el seguimiento de la fecha en que el propietario de un objeto lo revisó por última vez.  
  
-   Un atributo basado en dominio denominado orígenes, que se utiliza para realizar un seguimiento y administrar los sistemas de origen que interactúan con el [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] instancia.  
  
## <a name="related-tasks"></a>Related Tasks  
  
|Descripción de la tarea|Tema|  
|----------------------|-----------|  
|Agregar metadatos a un objeto del modelo.|[Agregar metadatos &#40;Master Data Services&#41;](add-metadata-master-data-services.md)
)|  
  
## <a name="related-content"></a>Contenido relacionado  
  
-   [Exportar datos &#40;Master Data Services&#41;](overview-exporting-data-master-data-services.md)  
  
  