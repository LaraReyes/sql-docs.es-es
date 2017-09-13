---
title: DROP TRIGGER (Transact-SQL) | Documentos de Microsoft
ms.custom:
- SQL2016_New_Updated
ms.date: 05/12/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- DROP TRIGGER
- DROP_TRIGGER_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- renaming triggers
- triggers [SQL Server], removing
- DDL triggers, removing
- DROP TRIGGER statement
- deleting triggers
- dropping triggers
- removing triggers
- DML triggers, removing
ms.assetid: 092d0d71-9f1e-4e38-a1c4-2487adfa5b4e
caps.latest.revision: 53
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: e3ca35b2b33a60d0af5dd31467f1381402f8f99b
ms.contentlocale: es-es
ms.lasthandoff: 09/01/2017

---
# <a name="drop-trigger-transact-sql"></a>DROP TRIGGER (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Quita uno o varios desencadenadores DML o DDL de la base de datos actual.  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-- Trigger on an INSERT, UPDATE, or DELETE statement to a table or view (DML Trigger)  
  
DROP TRIGGER [ IF EXISTS ] [schema_name.]trigger_name [ ,...n ] [ ; ]  
  
-- Trigger on a CREATE, ALTER, DROP, GRANT, DENY, REVOKE or UPDATE statement (DDL Trigger)  
  
DROP TRIGGER [ IF EXISTS ] trigger_name [ ,...n ]   
ON { DATABASE | ALL SERVER }   
[ ; ]  
  
-- Trigger on a LOGON event (Logon Trigger)  
  
DROP TRIGGER [ IF EXISTS ] trigger_name [ ,...n ]   
ON ALL SERVER  
```  

  
## <a name="arguments"></a>Argumentos  
 *IF EXISTE*  
 **Se aplica a**: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ([!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] a través de [versión actual](http://go.microsoft.com/fwlink/p/?LinkId=299658), [!INCLUDE[sssds](../../includes/sssds-md.md)]).  
  
 Quita condicionalmente el desencadenador solo si ya existe.  
  
 *schema_name*  
 Es el nombre del esquema al que pertenece un desencadenador DML. Los desencadenadores DML tienen como ámbito el esquema de la tabla o la vista donde se crean. *schema_name* no se puede especificar para desencadenadores DDL o logon.  
  
 *trigger_name*  
 Es el nombre del desencadenador que se va a quitar. Para ver una lista de los desencadenadores creados actualmente, use [sys.server_assembly_modules](../../relational-databases/system-catalog-views/sys-triggers-transact-sql.md) o [sys.server_triggers](../../relational-databases/system-catalog-views/sys-server-triggers-transact-sql.md).  
  
 DATABASE  
 Indica que el ámbito del desencadenador DDL se aplica a la base de datos actual. Debe especificarse DATABASE si también se especificó al crear o modificar el desencadenador.  
  
 ALL SERVER  
 **Se aplica a**: desde [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] hasta [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
 Indica que el ámbito del desencadenador DDL se aplica al servidor actual. Debe especificarse ALL SERVER si también se especificó al crear o modificar el desencadenador. ALL SERVER también se aplica a los desencadenadores de inicio de sesión.  
  
> [!NOTE]  
>  Esta opción no está disponible en las bases de datos independientes.  
  
## <a name="remarks"></a>Comentarios  
 Puede eliminar un desencadenador DML si quita éste o quita la tabla del desencadenador. Cuando se quita una tabla, también se quitan todos los desencadenadores asociados.  
  
 Cuando se quita un desencadenador, información acerca del desencadenador se quita de la **sys.objects**, **sys.triggers** y **sys.sql_modules** vistas de catálogo.  
  
 Se pueden quitar varios desencadenadores DDL por instrucción DROP TRIGGER solo si todos los desencadenadores se crearon utilizando las mismas cláusulas ON.  
  
 Para cambiar el nombre de un desencadenador, utilice DROP TRIGGER y CREATE TRIGGER. Para cambiar la definición de un desencadenador, utilice ALTER TRIGGER.  
  
 Para obtener más información acerca de cómo determinar las dependencias de un desencadenador específico, consulte [sys.sql_expression_dependencies](../../relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql.md), [sys.dm_sql_referenced_entities &#40; Transact-SQL &#41; ](../../relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql.md), y [sys.dm_sql_referencing_entities &#40; Transact-SQL &#41; ](../../relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql.md).  
  
 Para obtener más información acerca de cómo ver el texto del desencadenador, consulte [sp_helptext &#40; Transact-SQL &#41; ](../../relational-databases/system-stored-procedures/sp-helptext-transact-sql.md) y [sys.sql_modules &#40; Transact-SQL &#41; ](../../relational-databases/system-catalog-views/sys-sql-modules-transact-sql.md).  
  
 Para obtener más información acerca de cómo ver una lista de los desencadenadores existentes, consulte [sys.triggers &#40; Transact-SQL &#41; ](../../relational-databases/system-catalog-views/sys-triggers-transact-sql.md) y [sys.server_triggers &#40; Transact-SQL &#41; ](../../relational-databases/system-catalog-views/sys-server-triggers-transact-sql.md).  
  
## <a name="permissions"></a>Permissions  
 Para quitar un desencadenador DML se requiere el permiso ALTER en la tabla o vista en la que está definido el desencadenador.  
  
 Para anular un desencadenador DDL definido con ámbito de servidor (ON ALL SERVER) o un desencadenador logon se requiere el permiso CONTROL SERVER en el servidor. Para quitar un desencadenador DDL definido con el ámbito de base de datos (ON DATABASE) se requiere el permiso ALTER ANY DATABASE DDL TRIGGER en la base de datos actual.  
  
## <a name="examples"></a>Ejemplos  
  
### <a name="a-dropping-a-dml-trigger"></a>A. Quitar un desencadenador DML  
 En el siguiente ejemplo se quita el desencadenador `employee_insupd` de la base de datos [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)]. (A partir de [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] puede utilizar la sintaxis de DROP TRIGGER IF EXISTS.)  
  
```  
IF OBJECT_ID ('employee_insupd', 'TR') IS NOT NULL  
   DROP TRIGGER employee_insupd;  
```  
  
### <a name="b-dropping-a-ddl-trigger"></a>B. Quitar un desencadenador DDL  
 En el siguiente ejemplo se quita el desencadenador DDL `safety`.  
  
> [!IMPORTANT]  
>  Dado que los desencadenadores DDL no tienen el ámbito de esquema y, por lo tanto, no aparecen en la **sys.objects** vista de catálogo no se puede usar la función OBJECT_ID para consultar si existen en la base de datos. Los objetos que no están en el ámbito del esquema deben consultarse utilizando la vista de catálogo apropiada. Para los desencadenadores DDL, use **sys.triggers**.  
  
```  
DROP TRIGGER safety  
ON DATABASE;  
```  
  
## <a name="see-also"></a>Vea también  
 [ALTER TRIGGER &#40;Transact-SQL&#41;](../../t-sql/statements/alter-trigger-transact-sql.md)   
 [CREATE TRIGGER &#40;Transact-SQL&#41;](../../t-sql/statements/create-trigger-transact-sql.md)   
 [ENABLE TRIGGER &#40;Transact-SQL&#41;](../../t-sql/statements/enable-trigger-transact-sql.md)   
 [DISABLE TRIGGER &#40;Transact-SQL&#41;](../../t-sql/statements/disable-trigger-transact-sql.md)   
 [EVENTDATA &#40;Transact-SQL&#41;](../../t-sql/functions/eventdata-transact-sql.md)   
 [Obtener información acerca de los desencadenadores DML](../../relational-databases/triggers/get-information-about-dml-triggers.md)   
 [sp_help &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-help-transact-sql.md)   
 [sp_helptrigger &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-helptrigger-transact-sql.md)   
 [sys.triggers &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-triggers-transact-sql.md)   
 [sys.trigger_events &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-trigger-events-transact-sql.md)   
 [sys.sql_modules &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-sql-modules-transact-sql.md)   
 [sys.assembly_modules &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-assembly-modules-transact-sql.md)   
 [sys.server_triggers &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-server-triggers-transact-sql.md)   
 [sys.server_trigger_events &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql.md)   
 [sys.server_sql_modules &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql.md)   
 [sys.server_assembly_modules &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql.md)  
  
  
