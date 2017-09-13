---
title: "Aplicar formato a números y fechas (generador de informes y SSRS) | Documentos de Microsoft"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.rtp.rptdesigner.placeholderproperties.number.f1
- "10127"
- sql13.rtp.rptdesigner.textboxproperties.number.f1
- "10130"
- "10286"
- sql13.rtp.rptdesigner.serieslabelproperties.number.f1
- "10285"
- sql13.rtp.rptdesigner.axisproperties.number.f1
ms.assetid: 6de1a725-9f06-4708-be26-2d55e442e344
caps.latest.revision: 6
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 186bb0bab4abac91ea95d397f379986cac9d2f0f
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2017

---
# <a name="formatting-numbers-and-dates-report-builder-and-ssrs"></a>Aplicar formato a números y fechas (Generador de informes y SSRS)
  Para dar formato a los números y fechas de las regiones de datos, seleccione un formato en la página **Número** del cuadro de diálogo **Propiedades** de la región de datos correspondiente.  
  
 Para especificar las cadenas de formato dentro de un elemento de informe de cuadro de texto, debe seleccionar el elemento al que quiere dar formato, hacer clic con el botón derecho, seleccionar **Propiedades de cuadro de texto**y, después, hacer clic en **Número**. Puede dar formato de la misma manera a las celdas individuales de una tabla o región de datos de la matriz, porque las celdas de una tabla o la matriz son cuadros de texto individuales.  
  
 Normalmente, una región de datos de gráfico muestra las fechas a lo largo del eje de categorías (x) y los valores a lo largo del eje de valores (y). Para especificar el formato en un gráfico, haga clic con el botón derecho en un eje y seleccione **Propiedades del eje**. En el eje de valores solo se pueden especificar formatos para los números. Para más información, vea [Aplicar formato a las etiquetas de los ejes de un gráfico &#40;Generador de informes y SSRS&#41;](../../reporting-services/report-design/formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md).  
  
 Para especificar el formato en una región de datos Medidor, haga clic con el botón derecho en la escala del medidor y seleccione **Propiedades de escala radial** o **Propiedades de escala lineal**.  
  
> [!NOTE]  
>  Si observa que algunas opciones de formato que desea usar aparecen deshabilitadas, significa que esas opciones de formato no son compatibles con el tipo de datos del campo, que está establecido en el origen de datos. Por ejemplo, si el campo contiene valores numéricos pero el tipo de datos del campo es String, las opciones de formato de los datos numéricos, como moneda o decimales, no se puede aplicar.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="considerations-for-formatting-numbers-and-dates"></a>Consideraciones sobre la aplicación de formato a los números y las fechas  
 Antes de dar formato a los números y las fechas del informe, debería tener en cuenta lo siguiente:  
  
-   De forma predeterminada, se da formato a los números de acuerdo con la configuración de referencia cultural del equipo cliente. Use cadenas de formato para especificar cómo se muestran los números y hacer que el formato sea coherente, independientemente de dónde se encuentre la persona que está viendo el informe.  
  
-   Los formatos proporcionados en la página **Número** son un subconjunto de las cadenas de formato numérico estándar de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] . Para dar formato a un número o una fecha mediante un formato personalizado que no se muestra en el cuadro de diálogo, puede usar cualquier cadena de formato de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] para números o fechas. Para obtener más información sobre las cadenas de formato personalizado, vea el tema [Aplicar formato a tipos](http://go.microsoft.com/fwlink/?LinkId=112024) en MSDN.  
  
-   Si se especifica una cadena de formato personalizado, ésta tiene una prioridad más alta que la configuración predeterminada específica de la referencia cultural. Por ejemplo, imagine que establece una cadena con formato personalizado de "#, ###" para mostrar el número 1234 como 1,234. Esto puede tener un significado diferente para los usuarios de los Estados Unidos y para los usuarios de Europa. Antes de especificar un formato personalizado, tenga en cuenta cómo afectará el formato que elija a los usuarios de diferentes culturas que vean el informe.  
  
-   Si especifica una cadena de formato no válida, el texto con formato se interpreta como una cadena literal que invalida el formato.  
  
-   Si va a dar formato a una mezcla de números y caracteres en el mismo cuadro de texto, considere la posibilidad de usar un marcador de posición para dar formato al número de forma independiente del resto del texto. Para obtener más información, vea [Aplicar formato a texto y a marcadores de posición &#40;Generador de informes y SSRS&#41;](../../reporting-services/report-design/formatting-text-and-placeholders-report-builder-and-ssrs.md). Si se especifica una cadena de formato no válida para la propiedad Format en el cuadro de texto, dicha cadena no se tendrá en cuenta. Si se especifica una cadena de formato no válida para la propiedad Format en el gráfico o en el medidor, dicha cadena de formato se interpreta como una cadena y no se aplicará el formato.  
  
-   Si selecciona **Moneda** en **Categoría** y activa **Mostrar valores en**, puede seleccionar **Miles**, **Millones**o **Miles de millones** para mostrar los números mediante formatos financieros. Por ejemplo, si el valor del campo es 1.789.905.394, y selecciona **Miles de millones** y especifica 2 decimales, el valor mostrado en el informe será 1,78.  
  
## <a name="see-also"></a>Vea también  
 [Aplicar formato a texto y a marcadores de posición &#40;Generador de informes y SSRS&#41;](../../reporting-services/report-design/formatting-text-and-placeholders-report-builder-and-ssrs.md)   
 [Aplicar formato a líneas, colores y las imágenes &#40; El generador de informes y SSRS &#41;](../../reporting-services/report-design/formatting-lines-colors-and-images-report-builder-and-ssrs.md)   
 [Aplicar formato a un gráfico de &#40; El generador de informes y SSRS &#41;](../../reporting-services/report-design/formatting-a-chart-report-builder-and-ssrs.md)   
 [Etiquetas del eje de formato como fechas o monedas &#40; El generador de informes y SSRS &#41;](../../reporting-services/report-design/format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md)   
 [Aplicar formato a las escalas en un medidor &#40; El generador de informes y SSRS &#41;](../../reporting-services/report-design/formatting-scales-on-a-gauge-report-builder-and-ssrs.md)  
  
  