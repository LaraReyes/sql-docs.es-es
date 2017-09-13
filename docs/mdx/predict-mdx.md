---
title: Predecir (MDX) | Documentos de Microsoft
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- PREDICT
dev_langs:
- kbMDX
helpviewer_keywords:
- Predict function
ms.assetid: a82f3edd-249b-4559-98d3-6e10d81a095d
caps.latest.revision: 36
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 7bec1c96bd70b9b75c3a8c212cf1f6c04c27c73e
ms.contentlocale: es-es
ms.lasthandoff: 08/02/2017

---
# <a name="predict-mdx"></a>Predict (MDX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

    
> [!CAUTION]  
>  Esta función está en proceso de eliminación debido a incoherencias internas.  
>   
>  Revise la sección de ejemplo para encontrar una solución alternativa mediante una expresión DMX.  
  
 Devuelve un valor de una expresión numérica evaluada sobre un modelo de minería de datos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
Predict(Mining_Model_Name,String_Expression)   
```  
  
## <a name="arguments"></a>Argumentos  
 *Mining_Model_Name*  
 Expresión de cadena válida que representa el nombre de un modelo de minería de datos.  
  
 *String_Expression*  
 Expresión de cadena válida que se evalúa como una expresión DMX válida para el modelo de minería de datos especificado.  
  
## <a name="remarks"></a>Comentarios  
 El **Predict** función evalúa la expresión de cadena especificada en el contexto del modelo de minería de datos especificado.  
  
 La sintaxis y las funciones de minería de datos se documentan en la referencia de Expresiones de minería de datos (DMX).  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se predice nombre del clúster y la distancia desde él de un cliente determinado utilizando el modelo de minería de datos Customer Clusters:  
  
```  
WITH MEMBER MEASURES.CLNAME AS   
PREDICT("Customer Clusters", "Cluster()")  
MEMBER MEASURES.CLDISTANCE AS   
PREDICT("Customer Clusters", "ClusterDistance(Cluster())")  
SELECT {MEASURES.CLNAME, MEASURES.CLDISTANCE} ON 0   
FROM [Adventure Works]  
WHERE([Customer].[Customer Geography].[Customer].&[12012])  
```  
  
## <a name="see-also"></a>Vea también  
 [Referencia de funciones MDX &#40; MDX &#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
