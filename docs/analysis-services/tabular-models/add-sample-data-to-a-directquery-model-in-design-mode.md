---
title: "Agregar datos de ejemplo a un modelo de DirectQuery en el modo de dise&#241;o | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "analysis-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1af1e823-85aa-4319-a93f-98b35f7c7322
caps.latest.revision: 9
author: "Minewiskan"
ms.author: "owend"
manager: "erikre"
caps.handback.revision: 9
---
# Agregar datos de ejemplo a un modelo de DirectQuery en el modo de dise&#241;o
 En el modo DirectQuery, las particiones de tablas se usan para crear subconjuntos de datos de ejemplo usados durante el diseño de modelos, o bien para crear alternativas de una vista de datos completa.
 
 Al implementar un modelo tabular de DirectQuery, solo se permite una partición por tabla y, de forma obligatoria, esa partición tiene que ser de vista de datos completa. El resto de las particiones son sustituciones de la vista de datos completa o son datos de ejemplo. En este tema, vamos a describir cómo se crea una partición de ejemplo con un subconjunto de datos.
 
 De forma predeterminada, al diseñar un modelo tabular en el modo DirectQuery en SSDT, la base de datos de trabajo del modelo no contiene ningún dato. Existe una partición predeterminada para cada tabla, que dirige todas las consultas al origen de datos. 
  
Pero se puede agregar una cantidad más pequeña de datos de ejemplo a la base de datos de trabajo del modelo para usarla en el tiempo de diseño. Los datos de ejemplo se especifican con una consulta en una partición de ejemplo que solo se usa durante el diseño. Se almacena en la memoria caché con el modelo. Esto le ayudará a validar las decisiones de modelado al instante sin afectar al origen de datos. Puede probar las decisiones de modelado con el conjunto de datos de ejemplo al usar **Analizar en Excel** en SQL Server Data Tools (SSDT) o desde otras aplicaciones cliente que se conectan a la base de datos del área de trabajo.  
  
> [!TIP]  
>  Incluso en el modo DirectQuery de un modelo vacío, siempre se puede ver un pequeño conjunto de filas integrado para cada tabla. En [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], haga clic en **Tabla** > **Propiedades de tabla** para ver el conjunto de datos de 50 filas.  
  
## Crear una partición de ejemplo
 Estas instrucciones son para los modelos tabulares creados o actualizados en el nivel de compatibilidad 1200. Los modelos en niveles de compatibilidad inferiores usan otras propiedades para obtener los datos almacenados en caché. Vea las descripciones de las propiedades en [Habilitar el modo DirectQuery en SSMS](../../analysis-services/tabular-models/enable-directquery-mode-in-ssms.md).  
  
1.  En la vista Diagrama o la vista de datos de SQL Server Data Tools, haga clic en una tabla de hechos para abrir su página de propiedades. En las tablas de hechos se proporcionan las medidas y los datos numéricos agregados del modelo. Puede tener más de una.  
  
2.  Haga clic en **Tabla** > **Propiedades** para abrir el cuadro de diálogo Administración de particiones.  
  
    Como puede ver, la partición predeterminada es **(DirectQuery) \<nombre de tabla>**. Esta es la vista de datos completa. No elimine esta partición. Esta partición se usará cuando se implemente el modelo.  
  
4.  Seleccione la partición y haga clic en **Copiar**.  

    Esto crea una copia de la partición predeterminada, aunque esta copia contendrá datos de ejemplo que especifique en una consulta. Por ejemplo:
  
     ![ssas_tabularproject_copypartition](../../analysis-services/tabular-models/media/ssas-tabularproject-copypartition.jpg "ssas_tabularproject_copypartition")  
  
5.  Seleccione la partición copiada y, después, haga clic en el botón **Editor de consultas de SQL** para agregar un filtro. Reduzca el tamaño de los datos de ejemplo al crear el modelo. Por ejemplo, si ha seleccionado **FactInternetSales** de AdventureWorksDW, el filtro podría parecerse al siguiente:  
  
    ```  
    SELECT [dbo].[FactInternetSales].* FROM [dbo].[FactInternetSales]  
    JOIN DimSalesTerritory as ST  
    ON ST.SalesTerritoryKey = FactInternetSales.SalesTerritoryKey  
    WHERE ST.SalesTerritoryGroup='North America';  
    ```  
  
6.  Haga clic en **Validar** para ver si hay errores de sintaxis.  
  
     Tenga en cuenta que, en el modo DirectQuery, además de los botones **Nuevo**, **Copiar**y **Eliminar** del cuadro de diálogo Particiones, también hay un botón de alternancia que puede mostrarse como **Establecer como Ejemplo** o como **Establecer como DirectQuery**.  
  
     Solo una partición puede ser la partición de DirectQuery. Para controlar esto, seleccione cualquier partición definida para la tabla y haga clic en **Establecer como Ejemplo**.  
  
7.  Procese la tabla.  
  


  
  