---
title: Importar HTML en un informe (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dd0410ea-8839-4e8c-9944-8cdfe5465591
caps.latest.revision: 10
author: douglaslM
ms.author: douglasl
manager: mblythe
ms.openlocfilehash: bf60290c4946ef6f45bccba32632ed81dfaf650b
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36105771"
---
# <a name="importing-html-into-a-report-report-builder-and-ssrs"></a>Importar HTML en un informe (Generador de informes y SSRS)
  Se puede usar un cuadro de texto para insertar en un informe texto con formato HTML recuperado de un campo de conjunto de datos. El texto puede proceder de cualquier expresión simple o compleja que se evalúe como HTML con un formato correcto. El texto con formato se puede representar en todos los formatos de salida compatibles, incluso PDF.  
  
 ![rs_HTMLFormatting](../media/rs-htmlformatting.gif "rs_HTMLFormatting")  
  
 Esta ilustración se muestra texto con formato HTML en la vista de diseño de informe y el mismo texto como se representa cuando se ejecuta el informe.  
  
> [!NOTE]  
>  Cuando se importa texto que contiene marcado HTML, el cuadro de texto siempre debe analizar los datos en primer lugar. Dado que solo se admite un subconjunto de etiquetas HTML, el HTML que se muestra en el informe representado puede diferir del HTML original.  
  
 Para más información, vea [Tutorial: Dar formato a texto &#40;Generador de informes&#41;](../tutorial-format-text-report-builder.md).  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="supported-html-tags"></a>Etiquetas HTML compatibles  
 La lista siguiente es una lista completa de las etiquetas que se representarán como HTML cuando se definan como texto de marcador de posición:  
  
-   Encabezado, estilo y elementos de bloque: \<H {n} >, \<DIV >, \<intervalo >,\<P >, \<LI >  
  
 Cualquier otra etiqueta de marcado HTML se omitirá durante el procesamiento del informe. Si el HTML representado por la expresión en el texto del marcador de posición no está bien formado, el marcador de posición se representa como texto simple. Todas las etiquetas HTML distinguen entre mayúsculas y minúsculas.  
  
 Si el texto del cuadro de texto contiene solo un bloque de texto, cualquier HTML del marcador de posición que defina elementos de bloque se representará correctamente. Sin embargo, si el cuadro de texto tiene varios bloques de texto, se omitirán las etiquetas HTML y los bloques de texto definirán la estructura del texto.  
  
 Si se definen varias etiquetas para el texto, y [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] detecta un conflicto entre las restricciones del HTML y del informe existente, solo se considerará HTML la etiqueta HTML más interna.  
  
 Cuando se utilizan las etiquetas de gestión de listas, la fuente y el estilo de todos los prefijos de números y viñetas se fija en Arial negro.  
  
 Para más información, vea [Agregar HTML a un informe &#40;Generador de informes y SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md).  
  
## <a name="limitations-of-cascading-style-sheet-attributes"></a>Limitaciones de los atributos de las hojas de estilos en cascada  
 Cuando se usan atributos de hoja de estilos en cascada (CSS), solo se define un conjunto básico de etiquetas. La lista siguiente es una lista de los atributos admitidos:  
  
-   text-align, text-indent  
  
-   font-family  
  
-   tamaño de fuente  
  
    -   Solo se admiten valores válidos de tamaño RDL, en unidades de longitud CSS absolutas. Las unidades admitidas son: pda, cm, mm, pt y pc.  
  
    -   Las unidades de longitud de CSS relativas se pasan por algo y no se admiten. Las unidades no admitidas son em, ex, px,%,rem.  
  
     Para más información sobre unidades de CSS, consulte: [CSS Values and Units Reference](http://msdn.microsoft.com/en-us/library/ms531211\(VS.85\).aspx) (http://msdn.microsoft.com/library/ms531211(VS.85).aspx) (Valores de CSS y unidades de referencia).  
  
-   color  
  
-   padding, padding-bottom, padding-top, padding-right, padding-left  
  
-   font-weight  
  
 Estas son algunas consideraciones sobre el uso de CSS:  
  
-   Los valores de CSS incorrectos se omiten de la misma manera que se omite el HTML incorrecto.  
  
-   Cuando en una misma etiqueta hay un atributo y atributos de estilo CSS, la propiedad de CSS tiene una prioridad más alta. Por ejemplo, si el texto es **\<p style="text-align: right" align="left">**, solo se aplicará el atributo text-align y el texto estará alineado a la derecha.  
  
-   Para los atributos y los estilos CSS, si una propiedad se especifica más de una vez, solo se aplica la última instancia de la propiedad. Por ejemplo, si el texto es **\<p align="left" align="right">**, el texto estará alineado a la derecha.  
  
## <a name="see-also"></a>Vea también  
 [Representación en HTML &#40;el generador de informes SSRS&#41;](../report-builder/rendering-to-html-report-builder-and-ssrs.md)  
  
  