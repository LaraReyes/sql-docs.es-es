---
title: Combinar condiciones cuando OR tiene prioridad (Visual Database Tools) | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- search conditions [SQL Server], combining
- precedence [SQL Server], Criteria pane
- search criteria [SQL Server], combining conditions
- combining search conditions
- OR operator
ms.assetid: b30f5ac9-25e7-4163-80ed-44e4bccb455d
caps.latest.revision: 4
author: stevestein
ms.author: sstein
manager: jhubbard
ms.translationtype: HT
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 01acb8eb71b820655cb6c77df1495099cd0e7f81
ms.contentlocale: es-es
ms.lasthandoff: 08/18/2017

---
# <a name="combine-conditions-when-or-has-precedence-visual-database-tools"></a>Combinar condiciones cuando OR tiene prioridad (Visual Database Tools)
Para vincular condiciones con OR y darle prioridad sobre condiciones vinculadas con AND, debe repetir la condición AND para cada condición OR.  
  
Imagine, por ejemplo, que desea buscar todos los empleados que han estado en la compañía más de cinco años y que tienen puestos de nivel bajo o están jubilados. Esta consulta requiere tres condiciones, una única condición vinculada a dos condiciones adicionales con AND:  
  
-   Empleados con una fecha de contratación anterior a cinco años y  
  
-   Empleados con un puesto de nivel 100 o cuyo estado sea "R" (jubilado).  
  
El siguiente procedimiento ilustra cómo crear este tipo de consulta en el panel Criterios.  
  
### <a name="to-combine-conditions-when-or-has-precedence"></a>Para combinar condiciones cuando OR tiene precedencia  
  
1.  En el [panel Criterios](../../ssms/visual-db-tools/criteria-pane-visual-database-tools.md), agregue las columnas de datos en las que desee realizar la búsqueda. Si desea buscar en la misma columna utilizando dos o más condiciones unidas con AND, debe agregar el nombre de la columna de datos una vez por cada valor que desee buscar.  
  
2.  Cree las condiciones que se van a vincular con OR especificando la primera de ellas en la columna de cuadrícula **Filtro** y la segunda (y siguientes) en columnas **O…** distintas. Por ejemplo, para vincular condiciones con OR que busquen en las columnas `job_lvl` y `status` , especifique `= 100` en la columna **Filtro** para `job_lvl` y `= 'R'` en la columna **O...** para `status`.  
  
    Al especificar estos valores en la cuadrícula, se genera la siguiente cláusula WHERE en la instrucción del panel SQL:  
  
    ```  
    WHERE (job_lvl = 100) OR (status = 'R')  
    ```  
  
3.  Cree la condición AND especificándola una vez para cada condición OR. Incluya todas las entradas en la misma columna de cuadrícula que la condición OR con la que se corresponden. Por ejemplo, para agregar una condición AND que busque en la columna `hire_date` y se aplique a ambas condiciones OR, especifique `< '1/1/91'` tanto en la columna Criterios como en la columna **O…** .  
  
    Al especificar estos valores en la cuadrícula, se genera la siguiente cláusula WHERE en la instrucción del panel SQL:  
  
    ```  
    WHERE (job_lvl = 100) AND   
      (hire_date < '01/01/91' ) OR  
      (status = 'R') AND   
      (hire_date < '01/01/91' )  
    ```  
  
    > [!TIP]  
    > Puede repetir una condición AND agregándola una vez y después utilizar los comandos **Cortar** y **Pegar** del menú **Editar** para repetirla en otras condiciones OR.  
  
La cláusula WHERE creada por el Diseñador de consultas y vistas es equivalente a la siguiente cláusula WHERE, en la que se utilizan paréntesis para especificar la prioridad de OR frente a AND:  
  
```  
WHERE (job_lvl = 100 OR status = 'R') AND  
   (hire_date < '01/01/91')  
```  
  
> [!NOTE]  
> Si especifica condiciones de búsqueda en el formato arriba mostrado en el [panel SQL](../../ssms/visual-db-tools/sql-pane-visual-database-tools.md), pero luego modifica la consulta en los paneles Diagrama o Criterios, el Diseñador de consultas y vistas volverá a crear la instrucción SQL para hacerla coincidir con la forma en que la condición AND se distribuye explícitamente a ambas condiciones OR.  
  
## <a name="see-also"></a>Vea también  
[Convenciones para combinar condiciones de búsqueda en el panel Criterios &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md)  
[Especificar criterios de búsqueda &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/specify-search-criteria-visual-database-tools.md)  
  
