---
title: Usar SQL Server Profiler para supervisar Analysis Services | Documentos de Microsoft
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- analysis-services/multidimensional-tabular
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQL Server Profiler, Analysis Services
- monitoring Analysis Services [SQL Server]
- performance [Analysis Services], SQL Server Profiler
- Profiler [SQL Server Profiler], Analysis Services
ms.assetid: 8b77dafc-4584-4e93-8ad7-299304391bfd
caps.latest.revision: 35
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 338f49e4ee261ff1f17e25e4781f717a86418363
ms.contentlocale: es-es
ms.lasthandoff: 09/01/2017

---
# <a name="use-sql-server-profiler-to-monitor-analysis-services"></a>Usar SQL Server Profiler para supervisar Analysis Services
  [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] realiza un seguimiento de los eventos de procesos del motor, como el inicio de un lote o una transacción, y captura datos sobre estos eventos, lo que permite supervisar la actividad del servidor y de la base de datos (por ejemplo, consultas del usuario o actividad de inicio de sesión). Puede capturar datos del [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] en un archivo o una tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para su análisis posterior y también reproducir los eventos capturados en la misma instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] o en otra, para ver qué sucedió exactamente. Puede reproducir eventos en tiempo real o paso a paso. También resulta útil ejecutar los eventos de seguimiento junto con los contadores de Rendimiento en el mismo equipo. El analizador puede correlacionar los dos basándose en el tiempo y mostrarlos juntos en una misma línea temporal. Los eventos de seguimiento proporcionan más detalles, mientras que los contadores de Rendimiento ofrecen una vista agregada. Para obtener información sobre cómo crear y ejecutar seguimientos, vea [Crear seguimientos del generador de perfiles para su reproducción &#40;Analysis Services&#41;](../../analysis-services/instances/create-profiler-traces-for-replay-analysis-services.md).  
  
 En la tabla siguiente se describen los temas de esta sección.  
  
## <a name="in-this-section"></a>En esta sección  
  
|Tema|Description|  
|-----------|-----------------|  
|[Introducción a Supervisar Analysis Services con SQL Server Profiler](../../analysis-services/instances/introduction-to-monitoring-analysis-services-with-sql-server-profiler.md)|Describe cómo utilizar el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] para supervisar una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .|  
|[Crear seguimientos del generador de perfiles para su reproducción &#40;Analysis Services&#41;](../../analysis-services/instances/create-profiler-traces-for-replay-analysis-services.md)|Describe los requisitos para crear un seguimiento para la reproducción mediante el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].|  
|[Eventos de seguimiento de Analysis Services](../../analysis-services/trace-events/analysis-services-trace-events.md)|Describe las clases de evento de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] . Estas clases de evento se asignan a las acciones generadas por [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] y se utilizan para las reproducciones de seguimientos.|  
  
## <a name="see-also"></a>Vea también  
 [Supervisar una instancia de Analysis Services](../../analysis-services/instances/monitor-an-analysis-services-instance.md)  
  
  