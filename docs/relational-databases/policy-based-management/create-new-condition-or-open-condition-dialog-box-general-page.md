---
title: "Cuadro de diálogo Crear nueva condición o Abrir condición, página General | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.swb.dmf.condition.f1
ms.assetid: 106954bf-e4ba-412b-9c1a-907d06153dcd
caps.latest.revision: 30
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: b90436634729185cf2703cc012aae3a4f0338cdb
ms.contentlocale: es-es
ms.lasthandoff: 06/22/2017

---
# <a name="create-new-condition-or-open-condition-dialog-box-general-page"></a>Cuadro de diálogo Crear nueva condición o Abrir condición, página General
  Utilice este cuadro de diálogo para crear o cambiar una condición de la administración basada en directivas. Una condición es una expresión booleana que especifica un conjunto de estados permitidos de un destino administrado mediante la administración basada en directivas con respecto a las facetas. Las propiedades que se pueden seleccionar en el cuadro **Expresión/Campo** dependen de la faceta que se use. Para obtener más información sobre cómo se relacionan las condiciones con las facetas y las directivas, vea [Administrar servidores mediante administración basada en directivas](../../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md).  
  
## <a name="options"></a>Opciones  
 **Nombre**  
 Si la condición es nueva, escriba un nombre para ella. Si la condición ya existe, se muestra el nombre.  
  
 **Faceta**  
 Faceta usada por esta condición.  
  
 **Y/O**  
 Al agregar varias expresiones, indica si las expresiones deben combinarse con **AND** u **OR**. Permanece en blanco cuando solo hay una expresión.  
  
 **Campo**  
 Cada faceta expone una o varias propiedades que se pueden establecer. En el cuadro de campo, seleccione una propiedad de la lista de propiedades disponibles para crear una expresión para esta condición.  
  
 **Operador**  
 Seleccione un operador de comparación para esta expresión. Los operadores son: =, !=, >, >=, <, <=, [NOT]LIKE, [NOT]IN. No todos los operadores están disponibles para algunas propiedades.  
  
 **Valor**  
 Configuración del valor para esta expresión. Los valores permitidos dependen de la faceta. Los valores pueden ser TRUE/FALSE, de tipo cadena o de tipo numérico. Los valores de tipo cadena se deben incluir entre comillas sencillas, por ejemplo: **'AdventureWorks'**. No todos los operadores están disponibles para algunas propiedades.  
  
## <a name="group-clauses"></a>Agrupar cláusulas  
 Las cláusulas se pueden agrupar para que operen como una sola unidad independiente del resto de la consulta; el resultado es similar al que se obtiene colocando unos paréntesis en torno a una expresión en una ecuación matemática o una instrucción lógica. La agrupación de cláusulas resulta útil cuando se crean consultas complejas.  
  
 **Para agrupar cláusulas**  
  
-   Presione la tecla Mayús o Ctrl, y a continuación haga clic en dos o más cláusulas para seleccionar un intervalo. Haga clic con el botón derecho en el área seleccionada y luego haga clic en **Agrupar cláusulas**.  
  
## <a name="see-also"></a>Vea también  
 [Administrar servidores mediante administración basada en directivas](../../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md)  
  
  