---
title: MSSQL_ENG014160 | Microsoft Docs
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSSQL_ENG014160 error
ms.assetid: d0f3855e-d095-4a81-a5bd-9d7ad51f2c77
caps.latest.revision: 11
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 50fe0fe90d2e64586a3736cd8da5a038564edbef
ms.contentlocale: es-es
ms.lasthandoff: 06/22/2017

---
# <a name="mssqleng014160"></a>MSSQL_ENG014160
    
## <a name="message-details"></a>Detalles del mensaje  
  
|||  
|-|-|  
|Nombre del producto|SQL Server|  
|Identificador del evento|14160|  
|Origen del evento|MSSQLSERVER|  
|Componente|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|Nombre simbólico||  
|Texto del mensaje|Se ha establecido el umbral [%s:%s] para la publicación [%s]. Han expirado una o más suscripciones a esta publicación.|  
  
## <a name="explanation"></a>Explicación  
 La replicación le permite habilitar advertencias para varias condiciones. Esto incluye la expiración inminente de la suscripción. Las suscripciones pueden expirar si no se sincronizan en un *período de retención*especificado. Para más información, consulte [Subscription Expiration and Deactivation](../../relational-databases/replication/subscription-expiration-and-deactivation.md).  
  
 Al habilitar una advertencia mediante el Monitor de replicación o [sp_replmonitorchangepublicationthreshold](../../relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql.md), especifica un umbral que determina cuándo se desencadena una advertencia. Cuando se alcanza o se supera un umbral, aparece una advertencia en el Monitor de replicación y se escribe un evento en el registro de eventos de Windows. Alcanzar un umbral también puede desencadenar una alerta del Agente SQL Server. Para obtener más información, vea [Establecer umbrales y advertencias en el Monitor de replicación](../../relational-databases/replication/monitor/set-thresholds-and-warnings-in-replication-monitor.md) y [Cómo supervisar la replicación mediante programación (programación con RMO)](../../relational-databases/replication/monitor/programmatically-monitor-replication.md).  
  
## <a name="user-action"></a>Acción del usuario  
 La resolución de este problema depende del motivo por el que se produjo la advertencia:  
  
-   Si se ha sobrepasado el umbral, pero la suscripción no ha expirado todavía, sincronice la suscripción. Para obtener más información, vea [Sincronizar datos](../../relational-databases/replication/synchronize-data.md).  
  
-   Si el agente se ha estado ejecutando, pero no ha estado replicando los cambios correctamente, puede provocar que la suscripción expire. En la replicación transaccional, asegúrese de que se están ejecutando el Agente de distribución o el Agente de registro del LOG. En la replicación de mezcla, asegúrese de que se está ejecutando el Agente de mezcla. Para obtener información sobre cómo ejecutar estos agentes, vea [Iniciar y detener un agente de replicación &#40;SQL Server Management Studio&#41;](../../relational-databases/replication/agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) y [Conceptos de los ejecutables del Agente de replicación](../../relational-databases/replication/concepts/replication-agent-executables-concepts.md).  
  
-   Si la suscripción ha expirado, debe ser reinicializada o bien quitada y creada nuevamente, dependiendo del tipo de suscripción y durante cuanto tiempo ha expirado. Para más información, consulte [Subscription Expiration and Deactivation](../../relational-databases/replication/subscription-expiration-and-deactivation.md).  
  
## <a name="see-also"></a>Vea también  
 [Referencia de errores y eventos &#40;replicación&#41;](../../relational-databases/replication/errors-and-events-reference-replication.md)  
  
  