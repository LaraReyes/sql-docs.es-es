---
title: Cuadro de diálogo Expresión | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- "10040"
- sql12.rtp.rptdesigner.expression.f1
helpviewer_keywords:
- Expression dialog box [Reporting Services]
ms.assetid: e6c74ccb-4594-4d4f-b958-618d710e34eb
caps.latest.revision: 63
author: maggiesmsft
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 747943591907b1025250e3554270e9dda14d3e51
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2018
ms.locfileid: "37325645"
---
# <a name="expression-dialog-box"></a>Expresión (cuadro de diálogo)
  Use la **expresión** cuadro de diálogo para escribir [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] expresiones para informe de propiedades de los elementos. Puede usar expresiones para establecer muchas propiedades, como el color, la fuente y los bordes. En tiempo de ejecución, el procesador de informes evalúa las expresiones y usa el resultado como valor de la propiedad.  
  
 Una expresión puede ser sencilla o compleja. Puede escribir directamente las expresiones simples en un cuadro de texto en la superficie de diseño o en un cuadro de diálogo. Para crear expresiones complejas, use el **expresión** cuadro de diálogo. Puede crear una expresión cada vez. Para más información, vea [Expresiones &#40;Generador de informes y SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md).  
  
 Para abrir el cuadro de diálogo **Expresión** , haga clic en el botón Expresión (**fx**) de los cuadros de diálogo o seleccione **Expresión** en el menú contextual o en las listas desplegables del panel de propiedades. Para obtener más información, consulte [usar expresiones en informes &#40;generador de informes y SSRS&#41;](report-design/expression-uses-in-reports-report-builder-and-ssrs.md).  
  
 El cuadro de diálogo **Expresión** incluye una ventana de código, un árbol de categorías, elementos de categoría, un panel de descripción y un panel de ejemplo.  
  
 El cuadro de diálogo **Expresión** depende del contexto; los elementos y las descripciones de categorías cambian de acuerdo con la categoría de expresiones con la que se está trabajando. Admite IntelliSense, la finalización de instrucciones, ejemplos de llamadas a funciones y colores de sintaxis que ayudan a detectar errores de sintaxis.  
  
## <a name="expression-constructs"></a>Construcciones de expresiones  
 Las expresiones comienzan por un signo igual (=) y pueden incluir constantes, literales, operadores y referencias a campos integrados, colecciones integradas, funciones integradas, funciones de la biblioteca en tiempo de ejecución de [!INCLUDE[vbprvb](../includes/vbprvb-md.md)], clases de Common Language Runtime de [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] y funciones personalizadas. En la lista siguiente se describen las categorías y los valores que puede agregar a una expresión.  
  
 **Establecer expresión para:***\<PropertyName >  *  
 Nombre de la propiedad cuya expresión está definiendo. También puede establecer esta propiedad, por nombre, en el panel de propiedades.  
  
 **Constantes**  
 Proporciona una lista de valores predefinidos válidos para esta propiedad (para las propiedades que están basadas en constantes). Por ejemplo, una propiedad basada en colores muestra los nombres de los colores válidos. Para una propiedad que es un tipo de datos booleanos, los valores son `True` y `False`.  
  
 No todos los elementos que admiten expresiones pueden establecerse en una constante. Si una propiedad no se puede establecer en un valor constante, el panel de descripciones proporciona esta información.  
  
 **Campos integrados**  
 Proporciona una lista de los elementos de la colección global que puede utilizar en una expresión. Algunas colecciones solo se admiten una vez publicado el informe en el servidor. Para obtener más información, vea [Referencias a campos globales y de usuario integrados &#40;Generador de informes y SSRS&#41;](report-design/built-in-collections-built-in-globals-and-users-references-report-builder.md).  
  
 **Parámetros**  
 Proporciona una lista de parámetros de informe.  
  
 **Campos (** * \<conjunto de datos seleccionado >* **)**  
 Muestra la lista de campos para el conjunto de datos seleccionado en la categoría Conjuntos de datos. Haga doble clic en un campo para copiarlo en el cuadro **Expresión** .  
  
 **Conjuntos de datos**  
 Proporciona una lista de conjuntos de datos disponibles y muestra los campos miembros del conjunto de datos.  
  
 **Variables**  
 Muestra una lista de variables de informe. Para más información, vea [Referencias a las colecciones de variables de informe y de grupo &#40;Generador de informes y SSRS&#41;](report-design/built-in-collections-report-and-group-variables-references-report-builder.md).  
  
 **Operadores**  
 Muestra los operadores que puede incluir en un cálculo o manipulación de cadena. Para obtener más información, vea [Usar operadores en expresiones &#40;Generador de informes y SSRS&#41;](report-design/operators-in-expressions-report-builder-and-ssrs.md).  
  
 **Funciones comunes**  
 Muestra funciones comunes, agrupadas por tipos. Al seleccionar una función en el panel Elemento, aparecen una descripción y un ejemplo.  
  
 Entre las funciones comunes se incluyen funciones integradas de informe y de agregado, funciones de la biblioteca en tiempo de ejecución de [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] y clases de Common Language Runtime (CLR) de [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] en los espacios de nombres <xref:System.Math> y <xref:System.Convert>. También puede agregar referencias a clases de CLR y ensamblados externos que no aparecen en la lista de categorías. Para obtener más información, vea [Referencias a ensamblados y código personalizado en expresiones en el Diseñador de informes &#40;SSRS&#41;](report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).  
  
## <a name="options"></a>Opciones  
 Ventana de código  
 Utilice la ventana de código del panel superior para escribir una expresión. Cuando se abre el cuadro de diálogo **Expresión** , la ventana de código contiene la expresión. Puede reemplazar o revisar la expresión. Puede agregar llamadas a funciones, operadores, constantes, campos, parámetros, elementos de las colecciones globales y referencias a código personalizado. La ventana de código muestra los cambios a medida que se realizan.  
  
 Los subrayados ondulados en rojo indican un error de sintaxis. Mantenga el mouse sobre el texto subrayado para ver el mensaje de error.  
  
 Si escribe elementos de las colecciones globales seguidos por un separador de puntuación, verá una lista desplegable de los miembros o las propiedades disponibles. En la lista desplegable, puede escribir los primeros caracteres seguidos de un tabulador para rellenar la selección automáticamente.  
  
 Al escribir un nombre de función seguido por un paréntesis izquierdo, verá una información sobre herramientas que proporciona información sobre los parámetros y valores devueltos por la función.  
  
 **Categoría**  
 Muestra categorías de expresiones. Si se elige una categoría, se establece un contexto para crear una expresión y se cambia la lista de valores válidos en el panel Elemento. Por ejemplo, para una expresión para un valor del cuadro de texto, expanda funciones comunes y seleccione funciones de agregado para mostrar `Avg`, `Count`y otras funciones en el **elemento** panel.  
  
 **Elemento**  
 Muestra la lista de valores válidos para la categoría seleccionada. Haga doble clic en un elemento para agregar el texto de la expresión para este elemento en el punto de inserción en la ventana de código.  
  
 **Valores**  
 En función de la categoría y el elemento que seleccione, el tercer panel contiene una descripción, una expresión de ejemplo o una lista de valores válidos. Arrastre el borde del cuadro de diálogo para ampliar el área de ejemplo.  
  
## <a name="see-also"></a>Vea también  
 [Expresiones &#40;Generador de informes y SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md)   
 [Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md)   
 [Usar expresiones en informes &#40;generador de informes y SSRS&#41;](report-design/expression-uses-in-reports-report-builder-and-ssrs.md)   
 [Aplicar formato a números y fechas &#40;generador de informes y SSRS&#41;](report-design/formatting-numbers-and-dates-report-builder-and-ssrs.md)   
 [Usar referencias a la colección de parámetros &#40;generador de informes y SSRS&#41;](report-design/built-in-collections-parameters-collection-references-report-builder.md)   
 [Ejemplos de expresión de grupo &#40;Generador de informes y SSRS&#41;](report-design/group-expression-examples-report-builder-and-ssrs.md)   
 [Ejemplos de ecuaciones de filtro &#40;generador de informes y SSRS&#41;](report-design/filter-equation-examples-report-builder-and-ssrs.md)   
 [Tipos de datos en expresiones &#40;Generador de informes y SSRS&#41;](report-design/data-types-in-expressions-report-builder-and-ssrs.md)   
 [Colecciones integradas en expresiones &#40;generador de informes y SSRS&#41;](report-design/built-in-collections-in-expressions-report-builder.md)   
 [Agregar una expresión &#40;Generador de informes y SSRS&#41;](report-design/add-an-expression-report-builder-and-ssrs.md)  
  
  