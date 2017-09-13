---
title: "Supervisión de los registros de errores | Documentos de Microsoft"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- logs [SQL Server]
- database performance [SQL Server], errors
- Windows application logs [SQL Server]
- monitoring performance [SQL Server], errors
- server performance [SQL Server], errors
- comparing error and application log output
- errors [SQL Server], logs
- tuning databases [SQL Server], errors
- database monitoring [SQL Server], errors
- SQL Server error log
- logs [SQL Server], SQL Server error logs
- error logs [SQL Server]
- logs [SQL Server], Windows application logs
ms.assetid: e250336b-0695-44f6-a42f-23222f94e377
caps.latest.revision: 23
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 9edd8e852a1e4272d7c9f94af442a7e9e5cd7016
ms.contentlocale: es-es
ms.lasthandoff: 08/02/2017

---
# <a name="monitoring-the-error-logs"></a>Supervisar los registros de errores
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] registra ciertos eventos del sistema y definidos por el usuario en el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y en el registro de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows. Ambos registros marcan automáticamente el tiempo de todos los eventos registrados. Utilice la información del registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para solucionar problemas relacionados con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 El registro de aplicación Windows proporciona una visión global de los eventos que tienen lugar en el sistema operativo Windows, así como de los eventos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Utilice el Visor de eventos de Windows para ver el registro de aplicación Windows y filtrar la información. Por ejemplo, puede filtrar eventos, como información, advertencia, error, auditoría de éxito y auditoría de error.  
  
## <a name="comparing-error-and-application-log-output"></a>comparar los resultados del registro de errores y del registro de aplicación  
 Puede utilizar tanto el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como el registro de aplicación Windows para identificar la causa de los problemas. Por ejemplo, mientras supervisa el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , puede encontrar mensajes de error que no contienen información de la causa. Se puede acotar la lista de causas probables si se comparan las fechas y horas de los eventos en ambos registros. El Visor del archivo de registros de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] permite integrar los registros de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y Windows en una sola lista, facilitando así la comprensión de eventos de servidor y eventos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] relacionados. Para obtener más información, consulte el tema "Visor del archivo de registros" en los Libros en pantalla de SQL Server.  
  
## <a name="in-this-section"></a>En esta sección  
  
|Tema|Description|  
|-----------|-----------------|  
|[Ver el registro de errores SQL Server](../../tools/configuration-manager/viewing-the-sql-server-error-log.md)|Contiene información acerca del registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y cómo verlo.|  
|[Ver el registro de aplicación de Windows](../../tools/configuration-manager/viewing-the-windows-application-log.md)|Contiene información acerca del registro de aplicación Windows y cómo verlo.|  
  
  