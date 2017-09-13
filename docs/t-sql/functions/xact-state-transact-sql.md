---
title: XACT_STATE (Transact-SQL) | Documentos de Microsoft
ms.custom: 
ms.date: 03/16/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- XACT_STATE
- XACT_STATE_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- states [SQL Server], transactions
- uncommittable transactions
- sessions [SQL Server], active transactions
- XACT_STATE function
- transactions [SQL Server], state
- active transactions
ms.assetid: e9300827-e793-4eb6-9042-ffa0204aeb50
caps.latest.revision: 41
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: d5760cf8b2da0abea5505245681ae5164cbc9aca
ms.contentlocale: es-es
ms.lasthandoff: 09/01/2017

---
# <a name="xactstate-transact-sql"></a>XACT_STATE (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Función escalar que notifica el estado de la transacción de usuario de una solicitud que se está ejecutando actualmente. XACT_STATE indica si la solicitud tiene una transacción de usuario activa y si se puede confirmar la transacción.  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-- Syntax for SQL Server, Azure SQL Database, Azure SQL Data Warehouse, Parallel Data Warehouse  
  
XACT_STATE()  
```  
  
## <a name="return-type"></a>Tipo devuelto  
 **smallint**  
  
## <a name="remarks"></a>Comentarios  
 XACT_STATE devuelve los siguientes valores.  
  
|Valor devuelto|Significado|  
|------------------|-------------|  
|1|La solicitud actual tiene una transacción de usuario activa. La solicitud puede realizar cualquier acción, incluida la escritura de datos y la confirmación de la transacción.|  
|0|No hay ninguna transacción de usuario activa para la solicitud actual.|  
|-1|La solicitud actual tiene una transacción de usuario activa, pero se ha producido un error por el cual la transacción se clasificó como no confirmable. La solicitud no puede confirmar la transacción o revertirla a un punto de retorno; solo puede solicitar que la transacción se revierta completamente. Tampoco puede realizar operaciones de escritura hasta que se revierta la transacción. Mientras tanto, solo puede realizar operaciones de lectura. Una vez que la transacción se ha revertido, la solicitud puede realizar operaciones de lectura y escritura, y puede iniciar transacciones nuevas.<br /><br /> Cuando finalice la ejecución de un lote, el [!INCLUDE[ssDE](../../includes/ssde-md.md)] revertirá automáticamente todas las transacciones no confirmables activas. Si no se envió ningún mensaje de error cuando la transacción entró en un estado no confirmable, cuando finalice la ejecución del lote se enviará un mensaje de error a la aplicación cliente. Este mensaje indica que se detectó y revirtió una transacción no confirmable.|  
  
 Tanto el XACT_STATE y @@TRANCOUNT funciones pueden utilizarse para detectar si la solicitud actual tiene una transacción de usuario activa. @@TRANCOUNT no se puede usar para determinar si esa transacción se ha clasificado como una transacción no confirmable. No se puede utilizar XACT_STATE para determinar si hay transacciones anidadas.  
  
## <a name="examples"></a>Ejemplos  
 En el ejemplo siguiente se utiliza `XACT_STATE` en el bloque `CATCH` de una construcción `TRY…CATCH` para determinar si se debe confirmar o revertir una transacción. Como `SET XACT_ABORT` está en el estado `ON`, el error de infracción de restricción hace que la transacción pase a un estado no  confirmable.  
  
```  
USE AdventureWorks2012;  
GO  
  
-- SET XACT_ABORT ON will render the transaction uncommittable  
-- when the constraint violation occurs.  
SET XACT_ABORT ON;  
  
BEGIN TRY  
    BEGIN TRANSACTION;  
        -- A FOREIGN KEY constraint exists on this table. This   
        -- statement will generate a constraint violation error.  
        DELETE FROM Production.Product  
            WHERE ProductID = 980;  
  
    -- If the delete operation succeeds, commit the transaction. The CATCH  
    -- block will not execute.  
    COMMIT TRANSACTION;  
END TRY  
BEGIN CATCH  
    -- Test XACT_STATE for 0, 1, or -1.  
    -- If 1, the transaction is committable.  
    -- If -1, the transaction is uncommittable and should   
    --     be rolled back.  
    -- XACT_STATE = 0 means there is no transaction and  
    --     a commit or rollback operation would generate an error.  
  
    -- Test whether the transaction is uncommittable.  
    IF (XACT_STATE()) = -1  
    BEGIN  
        PRINT 'The transaction is in an uncommittable state.' +  
              ' Rolling back transaction.'  
        ROLLBACK TRANSACTION;  
    END;  
  
    -- Test whether the transaction is active and valid.  
    IF (XACT_STATE()) = 1  
    BEGIN  
        PRINT 'The transaction is committable.' +   
              ' Committing transaction.'  
        COMMIT TRANSACTION;     
    END;  
END CATCH;  
GO  
```  
  
## <a name="see-also"></a>Vea también  
 [@@TRANCOUNT &#40;Transact-SQL&#41;](../../t-sql/functions/trancount-transact-sql.md)   
 [BEGIN TRANSACTION &#40;Transact-SQL&#41;](../../t-sql/language-elements/begin-transaction-transact-sql.md)   
 [COMMIT TRANSACTION &#40;Transact-SQL&#41;](../../t-sql/language-elements/commit-transaction-transact-sql.md)   
 [ROLLBACK TRANSACTION &#40;Transact-SQL&#41;](../../t-sql/language-elements/rollback-transaction-transact-sql.md)   
 [SAVE TRANSACTION &#40;Transact-SQL&#41;](../../t-sql/language-elements/save-transaction-transact-sql.md)   
 [TRY...CATCH &#40;Transact-SQL&#41;](../../t-sql/language-elements/try-catch-transact-sql.md)  
  
  