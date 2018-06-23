---
title: Movimiento de un grupo de cargas de trabajo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql12.swb.rg.properties_moveworkloadgroup.f1
helpviewer_keywords:
- workload groups [SQL Server], move
- Resource Governor, workload group move
ms.assetid: f2068636-6e53-486a-a6fc-c12de2a38424
caps.latest.revision: 12
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 82a54da113251ada7dea4b5ee2be8661b66e7d91
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36204146"
---
# <a name="move-a-workload-group"></a>Mover un grupo de cargas de trabajo
  Puede mover un grupo de cargas de trabajo del regulador de recursos a un grupo de recursos de servidor diferente utilizando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o Transact-SQL.  
  
-   **Antes de empezar:**  [Limitaciones y restricciones](#LimitationsRestrictions), [Permisos](#Permissions)  
  
-   **Para mover un grupo de cargas de trabajo, use:**  [SQL Server Management Studio](#MoveWGSSMS), [Transact-SQL](#MoveWGTSQL)  
  
##  <a name="BeforeYouBegin"></a> Antes de empezar  
 No puede mover un grupo de cargas de trabajo si hay una operación de configuración del regulador de recursos pendiente.  
  
###  <a name="LimitationsRestrictions"></a> Limitaciones y restricciones  
 No puede mover un grupo de cargas de trabajo si hay una operación de configuración del regulador de recursos pendiente. Es posible determinar si existe una configuración pendiente consultando la vista de administración dinámica [sys.dm_resource_governor_configuration &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-configuration-transact-sql) para obtener el estado actual de is_configuration_pending.  
  
###  <a name="Permissions"></a> Permissions  
 Mover un grupo de cargas de trabajo requiere un permiso CONTROL SERVER.  
  
##  <a name="MoveWGSSMS"></a> Mover un grupo de cargas de trabajo mediante SQL Server Management  
 **Para mover un grupo de cargas de trabajo utilizando [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]**  
  
1.  En el Explorador de objetos, expanda de forma recursiva el nodo **Administración** hasta el nodo **Regulador de recursos**.  
  
2.  Haga clic con el botón derecho en **Regulador de recursos** y, luego, haga clic en **Propiedades**. De este modo se abre la página **Propiedades del regulador de recursos** .  
  
3.  En la ventana **Grupos de recursos** , haga clic en el grupo de recursos de servidor que contiene el grupo de cargas de trabajo que se va a mover. La ventana **Grupos de cargas de trabajo** enumera ahora los grupos de cargas de trabajo que contiene ese grupo de recursos de servidor.  
  
4.  En la ventana **Grupos de cargas de trabajo** , haga clic con el botón derecho en la flecha derecha situada a la izquierda del grupo de cargas de trabajo que se va a mover y haga clic en **Mover a**. Esto muestra una ventana **Mover grupo de cargas de trabajo** .  
  
5.  Los grupos de recursos de servidor disponibles se muestran en la ventana. Haga clic en el nombre del grupo de recursos de servidor al que desea mover el grupo de cargas de trabajo y, a continuación, haga clic en **Aceptar** para llevar a cabo esta acción.  
  
6.  Esta acción no se completa hasta que se hace clic en **Aceptar**. Al hacer clic en **Aceptar**, se ejecutará la instrucción ALTER RESOURCE GOVERNOR RECONFIGURE.  
  
7.  Si la operación de creación o cambio de configuración sobre el grupo de recursos de servidor o el grupo de cargas de trabajo produce un error, aparecerá un informe de error debajo del título de la página de propiedades. Para ver un mensaje de error más detallado, haga clic en la flecha abajo que aparece en el mensaje de error.  
  
##  <a name="MoveWGTSQL"></a> Mover un grupo de cargas de trabajo mediante Transact-SQL  
 **Para mover un grupo de cargas de trabajo utilizando Transact-SQL**  
  
1.  Ejecute la instrucción `ALTER WORKLOAD GROUP` especificando el nombre del grupo de cargas de trabajo que se va a mover y el grupo de recursos de servidor al que se debería mover.  
  
2.  Ejecute la instrucción **ALTER RESOURCE GOVERNOR RECONFIGURE** .  
  
### <a name="example-transact-sql"></a>Ejemplo (Transact-SQL)  
 El siguiente ejemplo mueve un grupo de cargas de trabajo denominado `groupAdhoc` al grupo de recursos de servidor predeterminado.  
  
```  
ALTER WORKLOAD GROUP groupAdhoc  
USING [default];  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a>Vea también  
 [Regulador de recursos](resource-governor.md)   
 [Habilitar el regulador de recursos](enable-resource-governor.md)   
 [Crear un grupo de recursos de servidor](create-a-resource-pool.md)   
 [Crear un grupo de cargas de trabajo](create-a-workload-group.md)   
 [ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql)   
 [ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  