---
title: Conecte tareas y contenedores mediante una restricción de precedencia predeterminada | Documentos de Microsoft
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tasks [Integration Services], precedence constraints
- precedence constraints [Integration Services], connecting tasks
- default precedence constraints
- containers [Integration Services], precedence constraints
ms.assetid: 8f31f15f-98ff-4c35-b41f-8b8cfd148d75
caps.latest.revision: 32
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: cf278d02e1c2eb523964ee07b039b46942c7e9de
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36104738"
---
# <a name="connect-tasks-and-containers-by-using-a-default-precedence-constraint"></a>Conectar tareas y contenedores mediante una restricción de precedencia predeterminada
  Las restricciones de precedencia conectan dos ejecutables. Un ejecutable puede ser cualquier tarea en un contenedor de bucles For, bucles Foreach o de secuencia. Este procedimiento describe cómo se configura el comportamiento predeterminado para las restricciones de precedencia y cómo se conectan los ejecutables mediante las restricciones de precedencia predeterminadas.  
  
## <a name="creating-default-precedence-constraints"></a>Crear restricciones de precedencia predeterminadas  
 Cuando usa [!INCLUDE[ssIS](../includes/ssis-md.md)] diseñador, el valor predeterminado de una restricción de precedencia es `Success`. Siga estos pasos para configurar el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] y usar un valor predeterminado diferente para las restricciones de precedencia.  
  
#### <a name="to-set-the-default-value-for-precedence-constraints"></a>Para establecer el valor predeterminado para las restricciones de precedencia  
  
1.  Abra [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].  
  
2.  En el menú **Herramientas** , haga clic en **Opciones**.  
  
3.  En el cuadro de diálogo **Opciones** , expanda **Diseñadores de Business Intelligence** y, a continuación, **Diseñadores de Integration Services**.  
  
4.  Haga clic en **Conexión automática de flujo de control** y seleccione **Conectar una nueva forma a la forma seleccionada de manera predeterminada**.  
  
5.  En la lista desplegable, elija **Usar una restricción de error en la operación para la nueva forma** o **Usar una restricción de operación completada para la nueva forma**.  
  
6.  Haga clic en **Aceptar**.  
  
#### <a name="to-create-a-default-precedence-constraint"></a>Para crear una restricción de precedencia predeterminada.  
  
1.  En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.  
  
2.  En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.  
  
3.  Haga clic en la pestaña **Flujo de control** .  
  
4.  En la superficie de diseño de la pestaña **Flujo de control** , haga clic en la tarea o contenedor y arrastre su conector al ejecutable al que desea aplicar la restricción de precedencia.  
  
5.  Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.  
  
## <a name="see-also"></a>Vea también  
 [Restricciones de precedencia](control-flow/precedence-constraints.md)   
 [Establecer el valor de una restricción de precedencia mediante el menú contextual](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md)   
 [Establecer las propiedades de una restricción de precedencia](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md)   
 [Utilizar una expresión en una restricción de precedencia](../../2014/integration-services/use-an-expression-in-a-precedence-constraint.md)  
  
  