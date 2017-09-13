---
title: ENTRE (Transact-SQL) | Documentos de Microsoft
ms.custom: 
ms.date: 08/28/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- BETWEEN
- BETWEEN_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- inclusive ranges
- testing range
- exclusive ranges
- NOT BETWEEN operator
- BETWEEN operator
- range to test [SQL Server]
ms.assetid: a5d5b050-203e-4355-ac85-e08ef5ca7823
caps.latest.revision: 34
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 71bc6e3bee0176f895dac6037219294acdab52d0
ms.contentlocale: es-es
ms.lasthandoff: 09/01/2017

---
# <a name="between-transact-sql"></a>BETWEEN (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Especifica un intervalo que se va a probar.  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
test_expression [ NOT ] BETWEEN begin_expression AND end_expression  
```  
  
## <a name="arguments"></a>Argumentos  
 *test_expression*  
 Es el [expresión](../../t-sql/language-elements/expressions-transact-sql.md) para la prueba en el intervalo definido por *begin_expression*y *end_expression*. *test_expression* debe ser el mismo tipo de datos que *begin_expression* y *end_expression*.  
  
 NOT  
 Especifica que se niega el resultado del predicado.  
  
 *begin_expression*  
 Es cualquier expresión válida. *begin_expression* debe ser el mismo tipo de datos que *test_expression* y *end_expression*.  
  
 *end_expression*  
 Es cualquier expresión válida. *end_expression* debe ser el mismo tipo de datos que *test_expression*y *begin_expression*.  
  
 y  
 Actúa como un marcador de posición que indica *test_expression* debe estar dentro del intervalo indicado por *begin_expression* y *end_expression*.  
  
## <a name="result-types"></a>Tipos de resultado  
 **Boolean**  
  
## <a name="result-value"></a>Valor de resultado  
 BETWEEN devuelve **TRUE** si el valor de *test_expression* es mayor o igual que el valor de *begin_expression* y menor o igual que el valor de *end_expression*.  
  
 NOT BETWEEN devuelve **TRUE** si el valor de *test_expression* es menor que el valor de *begin_expression* o mayor que el valor de *end_expression* .  
  
## <a name="remarks"></a>Comentarios  
 Para especificar un intervalo exclusivo, utilice los operadores mayor que (>) y menor que (<). Si alguna entrada del predicado BETWEEN o NOT BETWEEN es NULL, el resultado es UNKNOWN.  
  
## <a name="examples"></a>Ejemplos  
  
### <a name="a-using-between"></a>A. Utilizar BETWEEN  
 En el ejemplo siguiente se devuelve información acerca de los roles de base de datos en una base de datos. La primera consulta devuelve todos los roles. El segundo ejemplo se usa el `BETWEEN` cláusula para limitar los roles a los especificados `database_id` valores.  
  
```sql  
SELECT principal_id, name 
FROM sys.database_principals
WHERE type = 'R';

SELECT principal_id, name 
FROM sys.database_principals
WHERE type = 'R'
AND principal_id BETWEEN 16385 AND 16390;
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]   
```  
principal_id    name
------------  ---- 
0               public
16384           db_owner
16385           db_accessadmin
16386           db_securityadmin
16387           db_ddladmin
16389           db_backupoperator
16390           db_datareader
16391           db_datawriter
16392           db_denydatareader
16393           db_denydatawriter
```  
```  
principal_id    name
------------  ---- 
16385           db_accessadmin
16386           db_securityadmin
16387           db_ddladmin
16389           db_backupoperator
16390           db_datareader
```  
  
### <a name="b-using--and--instead-of-between"></a>B. Utilizar > y < en lugar de BETWEEN  
 En el siguiente ejemplo se utilizan los operadores mayor que (`>`) y menor que (`<`) y, puesto que dichos operadores no son inclusivos, se devuelven nueve filas en lugar de las diez devueltas en el ejemplo anterior.  
  
```sql  
-- Uses AdventureWorks  
  
SELECT e.FirstName, e.LastName, ep.Rate  
FROM HumanResources.vEmployee e   
JOIN HumanResources.EmployeePayHistory ep   
    ON e.BusinessEntityID = ep.BusinessEntityID  
WHERE ep.Rate > 27 AND ep.Rate < 30  
ORDER BY ep.Rate;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 ```  
 FirstName   LastName             Rate  
 ---------   -------------------  ---------  
 Paula       Barreto de Mattos    27.1394  
 Janaina     Bueno                27.4038  
 Dan         Bacon                27.4038  
 Ramesh      Meyyappan            27.4038  
 Karen       Berg                 27.4038  
 David       Bradley              28.7500  
 Hazem       Abolrous             28.8462  
 Ovidiu      Cracium              28.8462  
 Rob         Walters              29.8462  
 ```    
  
### <a name="c-using-not-between"></a>C. Utilizar NOT BETWEEN  
 En el siguiente ejemplo se buscan todas las filas que no están incluidas en un intervalo especificado de `27` a `30`.  
  
```sql  
-- Uses AdventureWorks  
  
SELECT e.FirstName, e.LastName, ep.Rate  
FROM HumanResources.vEmployee e   
JOIN HumanResources.EmployeePayHistory ep   
    ON e.BusinessEntityID = ep.BusinessEntityID  
WHERE ep.Rate NOT BETWEEN 27 AND 30  
ORDER BY ep.Rate;  
GO  
```  
  
### <a name="d-using-between-with-datetime-values"></a>D. Utilizar BETWEEN con valores datetime  
 En el ejemplo siguiente se recuperan filas en las que **datetime** valores están comprendidos entre `'20011212'` y `'20020105'`, ambos inclusive.  
  
```sql  
-- Uses AdventureWorks  
  
SELECT BusinessEntityID, RateChangeDate  
FROM HumanResources.EmployeePayHistory  
WHERE RateChangeDate BETWEEN '20011212' AND '20020105';  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 ```  
 BusinessEntityID RateChangeDate  
 ----------- -----------------------  
 3           2001-12-12 00:00:00.000  
 4           2002-01-05 00:00:00.000  
 ```  
 
 La consulta recupera las filas previstas porque los valores de fecha en la consulta y la **datetime** valores almacenados en la `RateChangeDate` columna se han especificado sin la parte de hora de la fecha. Si no se especifica la parte de hora, toma el valor predeterminado 12:00 a.m. Tenga en cuenta que esta consulta no devolverá una fila que contenga una parte de hora posterior a 12:00 a.m. del 05-01-2002, ya que está fuera del rango.  
  
  
## <a name="see-also"></a>Vea también  
 [&#62; &#40; Mayor &#41; &#40; Transact-SQL &#41;](../../t-sql/language-elements/greater-than-transact-sql.md)   
 [&#60; &#40; Menor &#41; &#40; Transact-SQL &#41;](../../t-sql/language-elements/less-than-transact-sql.md)   
 [Expresiones &#40; Transact-SQL &#41;](../../t-sql/language-elements/expressions-transact-sql.md)   
 [Funciones integradas &#40;Transact-SQL&#41;](~/t-sql/functions/functions.md)   
 [Operadores &#40; Transact-SQL &#41;](../../t-sql/language-elements/operators-transact-sql.md)   
 [SELECT &#40;Transact-SQL&#41;](../../t-sql/queries/select-transact-sql.md)   
 [DONDE &#40; Transact-SQL &#41;](../../t-sql/queries/where-transact-sql.md)  
  
  


