---
title: "Dirigir el flujo CDC según el tipo de cambio | Documentos de Microsoft"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3afa531e-f425-40a4-a1bf-1c3e1727287e
caps.latest.revision: 8
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 4c520920a94c6c53a577953b313837aee0f7d584
ms.contentlocale: es-es
ms.lasthandoff: 08/03/2017

---
# <a name="direct-the-cdc-stream-according-to-the-type-of-change"></a>Dirigir el flujo CDC según el tipo de cambio
  Para agregar y configurar una transformación Divisor CDC, el paquete debe contener por lo menos una tarea Flujo de datos y un origen de CDC.  
  
 El origen de CDC agregado al paquete debe tener seleccionado un modo de procesamiento de NetCDC. Para obtener más información sobre cómo seleccionar los modos de procesamiento, vea [Editor de origen de CDC &#40;página Administrador de conexiones&#41;](../../integration-services/data-flow/cdc-source-editor-connection-manager-page.md).  
  
### <a name="to-direct-the-cdc-stream-according-to-the-type-of-change"></a>Para dirigir el flujo CDC según el tipo de cambio  
  
1.  En [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], abra el proyecto de [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] que contiene el paquete que desea.  
  
2.  En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.  
  
3.  Haga clic en la pestaña **Flujo de datos** y, a continuación, desde el **cuadro de herramientas**, arrastre el divisor CDC a la superficie de diseño.  
  
4.  Conéctese al origen de CDC que se incluye en el paquete al divisor CDC.  
  
5.  Conecte el divisor CDC a uno o varios destinos. Puede conectarse hasta a tres salidas diferentes.  
  
6.  Seleccione una de las siguientes salidas:  
  
    -   Salida Delete: la salida donde se dirigen las filas de cambios DELETE.  
  
    -   Salida Insert: la salida donde se dirigen las filas de cambios INSERT.  
  
    -   Salida Update: la salida donde se dirigen las filas de cambios UPDATE antes o después y las filas de cambios Merge.  
  
7.  Opcionalmente, puede configurar las propiedades avanzadas mediante el cuadro de diálogo **Editor avanzado** .  
  
     El cuadro de diálogo **Editor avanzado** contiene las propiedades que se pueden establecer mediante programación.  
  
     Para abrir el cuadro de diálogo **Editor avanzado** :  
  
    -   En la pantalla **Flujo de datos** del proyecto de [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] , haga clic con el botón secundario en el divisor CDC y seleccione **Mostrar editor avanzado**.  
  
     Para obtener más información sobre cómo usar el divisor CDC, vea Componentes CDC para Microsoft SQL Server Integration Services.  
  
## <a name="see-also"></a>Vea también  
 [Divisor CDC](../../integration-services/data-flow/cdc-splitter.md)  
  
  