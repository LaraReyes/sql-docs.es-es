---
title: Agente de lectura de cola | Microsoft Docs
ms.custom: 
ms.date: 03/07/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.rep.monitor.queuereaderagent.f1
helpviewer_keywords:
- Queue Reader Agent dialog box
ms.assetid: f02d24b6-dcb5-4126-b56e-fab41cfe4337
caps.latest.revision: 18
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 25110b487226028d9d24c6709e59cd2643fb4aac
ms.contentlocale: es-es
ms.lasthandoff: 06/22/2017

---
# <a name="queue-reader-agent"></a>Agente de lectura de cola
  El cuadro de diálogo **Agente de lectura de cola** muestra información detallada sobre el Agente de lectura de cola, incluyendo mensajes de estado, históricos e informativos, así como mensajes de error.  
  
## <a name="options"></a>Opciones  
 Seleccione las sesiones del Agente de lectura de cola que deben mostrarse en el menú **Ver** y, a continuación, seleccione una sesión específica en la cuadrícula **Sesiones del Agente de lectura de cola**. En la cuadrícula con la etiqueta **Acciones en la sesión seleccionada**se muestra información detallada de la sesión. Si la sesión seleccionada finalizó con un error, también se muestra el área de texto con la etiqueta **Detalles del error o mensaje de la sesión seleccionada** .  
  
 **Ver**  
 Seleccione las sesiones del Agente de lectura de cola que deben mostrarse. Generalmente, el Agente de lectura de cola se ejecuta de forma continuada, por lo que es posible que solo haya una sesión para mostrar.  
  
 **Estado**  
 Estado del Agente de lectura de cola. En la lista siguiente se muestran los valores de estado posibles:  
  
-   Error  
  
-   Reintentando comandos con errores  
  
-   No está en ejecución  
  
-   En ejecución  
  
 **Start Time**  
 Muestra la hora de inicio de la sesión.  
  
 **Hora de finalización**  
 Muestra la hora de finalización de la sesión. Si no se ha detenido el agente, el campo se mostrará vacío.  
  
 **Duración**  
 Período de tiempo durante el que el Agente de lectura de cola se ha ejecutado en esta sesión. El tiempo representa el tiempo transcurrido si el agente se está ejecutando, y el tiempo total de la sesión si la sesión del agente ha finalizado.  
  
 **Mensaje de error**  
 Si una sesión finalizó con un error, este campo muestra el último mensaje de error registrado por el Agente de lectura de cola. Si la sesión no ha finalizado con error, el campo se mostrará vacío.  
  
 **Mensaje de la acción**  
 Muestra todos los mensajes informativos y los mensajes con error que el Agente de lectura de cola ha registrado durante la sesión seleccionada.  
  
 **Hora de la acción**  
 Muestra la hora de realización de la acción descrita en la columna **Mensaje de la acción** .  
  
 **Detalles del error o mensaje de la sesión seleccionada**  
 Solo se muestra si la sesión seleccionada presenta un valor de **Error** en la columna **Estado** . El área de texto muestra la información detallada del error y el comando que se intentaba ejecutar en el momento de producirse el error. También incluye vínculos a la información adicional relativa al error.  
  
## <a name="see-also"></a>Vea también  
 [Iniciar el Monitor de replicación](../../relational-databases/replication/monitor/start-the-replication-monitor.md)   
 [Ver información y realizar tareas para los agentes asociados a una publicación &#40;Monitor de replicación&#41;](../../relational-databases/replication/monitor/view-information-and-perform-tasks-for-publication-agents.md)   
 [Supervisar la replicación](../../relational-databases/replication/monitor/monitoring-replication-overview.md)   
 [Replication Agents Overview](../../relational-databases/replication/agents/replication-agents-overview.md)  
  
  