---
title: Instalar Integration Services en paralelo de versiones | Documentos de Microsoft
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interoperability and coexistence [Integration Services]
- Integration Services, interoperability and coexistence
ms.assetid: edfbcd56-012f-462e-a542-95491394fda9
caps.latest.revision: 41
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: d642d8d9d732a51c210e5d83cecf2b090ac2f426
ms.contentlocale: es-es
ms.lasthandoff: 08/03/2017

---
# <a name="installing-integration-services-versions-side-by-side"></a>Installing Integration Services Versions Side by Side (Instalación de versiones de Integration Services en paralelo)
  Puede instalar   
      [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]Integration Services (SSIS) side-by-side con versiones anteriores de SSIS. En este tema se describen algunas limitaciones de las instalaciones en paralelo.  
  
## <a name="designing-and-maintaining-packages"></a>Diseño y mantenimiento de paquetes  
 Para diseñar y mantener paquetes orientados a SQL Server 2016, SQL Server 2014 o SQL Server 2012, use SQL Server Data Tools (SSDT) para Visual Studio 2015. Para obtener SSDT, consulte [Descarga de las SQL Server Data Tools más recientes](https://msdn.microsoft.com/library/mt204009.aspx).  
  
 En las páginas de propiedades de un proyecto de Integration Services, en la pestaña **General** de **Propiedades de configuración**, seleccione la propiedad **TargetServerVersion** y elija SQL Server 2016, SQL Server 2014 o SQL Server 2012.  
  
|Versión de destino de SQL Server|Entorno de desarrollo para paquetes de SSIS|  
|----------------------------------|-----------------------------------------------|  
|2016|SQL Server Data Tools para Visual Studio 2015|  
|2014|SQL Server Data Tools para Visual Studio 2015<br /><br /> o bien<br /><br /> SQL Server Data Tools - Business Intelligence para Visual Studio 2013|  
|2012|SQL Server Data Tools para Visual Studio 2015<br /><br /> o bien<br /><br /> SQL Server Data Tools: inteligencia empresarial para Visual Studio 2012|  
|2008|Business Intelligence Development Studio desde SQL Server 2008|  
  
 Cuando se agrega un paquete existente a un proyecto existente, el paquete se convierte al formato al que se orienta el proyecto.  
  
## <a name="running-packages"></a>Ejecución de paquetes  
 Puede usar la versión [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] de la utilidad **dtexec** o del agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ejecutar paquetes de Integration Services que se crearon con las versiones anteriores de las herramientas de desarrollo. Cuando estas herramientas de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] cargan un paquete que se desarrolló en una versión anterior de las herramientas de desarrollo, la herramienta convierte, de forma temporal, el paquete en memoria en el formato de paquete que [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] usa. Si el paquete presenta problemas que impiden realizar una conversión correcta, la herramienta [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] no podrá ejecutar el paquete hasta que se resuelvan esos problemas. Para obtener más información, vea [Actualizar paquetes de Integration Services](../../integration-services/install-windows/upgrade-integration-services-packages.md).  
  
  