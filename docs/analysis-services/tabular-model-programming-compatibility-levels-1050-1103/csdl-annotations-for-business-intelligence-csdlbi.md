---
title: Anotaciones de CSDL para Business Intelligence (CSDLBI) | Microsoft Docs
ms.date: 05/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 3eac4057f8a4db818a02068f33cbc7b295353f0c
ms.sourcegitcommit: 7fe14c61083684dc576d88377e32e2fc315b7107
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2018
ms.locfileid: "50145870"
---
# <a name="csdl-annotations-for-business-intelligence-csdlbi"></a>Anotaciones de CSDL para Business Intelligence (CSDLBI)
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] admite la presentación de la definición de un modelo tabular en un formato XML denominado Lenguaje de definición de esquemas conceptuales con anotaciones Business Intelligence (CSDLBI). En este tema se proporciona información general sobre CSDLBI y su uso con los modelos de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].  
  
## <a name="understanding-the-role-of-csdl"></a>Descripción del propósito de CSDL  
 El Lenguaje de definición de esquemas conceptuales (CSDL) es un lenguaje basado en XML que describe las entidades, las relaciones y las funciones. CSDL forma parte de Entity Data Framework. Las anotaciones BI son una extensión diseñada para admitir el modelado de datos mediante [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].  
  
 Aunque CSDL es compatible con Entity Data Framework, no es necesario comprender el modelo entidad-relación ni tener ninguna herramienta especial para generar un modelo tabular o un informe basado en un modelo. Es posible generar modelos mediante herramientas cliente como [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] o una API como AMO, e implementarlos en un servidor.  
  
 El esquema CSDLBI lo genera el servidor de Analysis Services en respuesta a una solicitud de una definición de modelo realizada por un cliente como [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)]. La aplicación cliente envía una consulta XML al servidor de Analysis Services que hospeda los datos del modelo. En respuesta, el servidor envía un mensaje XML que contiene una definición de las entidades del modelo, utilizando las anotaciones CSDLBI. El cliente de informes usa la información para mostrar los campos, las agregaciones y las medidas disponibles en el modelo. Las anotaciones CSDLBI también proporcionan información sobre cómo agrupar, ordenar y dar formato a los datos.  
  
 Para obtener información general sobre CSDLBI, vea [conceptos de CSDLBI](https://docs.microsoft.com/bi-reference/csdl/csdlbi-concepts).  
  
### <a name="working-with-csdl"></a>Trabajar con CSDL  
 El conjunto de anotaciones CSDLBI que representa cualquier modelo tabular determinado es un documento XML que contiene una colección de entidades, tanto simples como complejas. Las entidades definen las tablas (o dimensiones), las columnas (atributos), las asociaciones (relaciones) y las fórmulas incluidas en las columnas calculadas, medidas o KPI.  
  
 No puede modificar estos objetos directamente, sino que debe utilizar las herramientas del cliente y las interfaces de programación de aplicaciones (API) proporcionadas para trabajar con modelos tabulares.  
  
 Puede obtener el CSDL para un modelo enviando una solicitud DISCOVER al servidor que hospeda el modelo. La solicitud se debe calificar especificando el servidor y el modelo y, opcionalmente, una vista o una perspectiva. El mensaje devuelto es una cadena XML. Algunos elementos dependen del lenguaje y pueden devolver valores diferentes en función del lenguaje de la conexión actual. Para obtener más información, consulte [conjunto de filas DISCOVER_CSDL_METADATA](https://docs.microsoft.com/bi-reference/schema-rowsets/xml/discover-csdl-metadata-rowset).  
  
### <a name="csdlbi-versions"></a>Versiones de CSDLBI  
 La especificación CSDL original (de Entity Data Framework) es suficiente para la mayor parte de las entidades y propiedades necesarias para el modelado. Las anotaciones BI admiten requisitos especiales de modelos tabulares, propiedades de informes requeridas por clientes como [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] y metadatos adicionales requeridos por modelos multidimensionales. En esta sección se describen las actualizaciones de cada versión.  
  
 **1.0 DE CSDLBI**  
  
 El conjunto inicial de adiciones al esquema CSDL para admitir los modelos tabulares de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] contenía anotaciones que permitían el uso del modelado de datos, los cálculos personalizados y las presentaciones mejoradas:  
  
-   Nuevos elementos y propiedades para admitir modelos tabulares. Por ejemplo, se agregó una propiedad para especificar el tipo de consulta de base de datos utilizada para rellenar el modelo.  
  
-   Nuevas propiedades y extensiones para las entidades existentes.  Por ejemplo, el elemento Association se extendió para admitir las relaciones.  
  
-   Propiedades de visualización y navegación. Por ejemplo, se agregaron propiedades para admitir campos de ordenación personalizados e imágenes predeterminadas.  
  
 **1.1 DE CSDLBI**  
  
 Esta versión del esquema CSDLBI incluye adiciones para admitir el uso de bases de datos multidimensionales (como los cubos OLAP). Los nuevos elementos y propiedades son los siguientes:  
  
-   Compatibilidad con las dimensiones como entidades.  
  
-   Compatibilidad con las jerarquías.  
  
-   Expone particiones ROLAP.  
  
-   Compatibilidad con las traducciones.  
  
-   Compatibilidad con las perspectivas.  
  
 Para obtener información detallada acerca de los elementos individuales de las anotaciones CSDLBI, vea [referencia técnica para las anotaciones de Business Intelligence en CSDL](https://docs.microsoft.com/bi-reference/csdl/technical-reference-for-bi-annotations-to-csdl). Para obtener información acerca de la especificación de CSDL del núcleo, consulte el [especificación de CSDL](http://go.microsoft.com/fwlink/?LinkId=205855) en MSDN.  
  
## <a name="see-also"></a>Vea también  
 [Descripción del modelo de objetos tabulares en la compatibilidad de los niveles de 1050 a 1103](../../analysis-services/tabular-model-programming-compatibility-levels-1050-1103/representation/understanding-tabular-object-model-at-levels-1050-through-1103.md)   
 [Conceptos de CSDLBI](https://docs.microsoft.com/bi-reference/csdl/csdlbi-concepts)   
 [Descripción del modelo de objetos tabulares en la compatibilidad de los niveles de 1050 a 1103](../../analysis-services/tabular-model-programming-compatibility-levels-1050-1103/representation/understanding-tabular-object-model-at-levels-1050-through-1103.md)  
  
  
