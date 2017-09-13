---
title: "Preparación para implementar una extensión de entrega | Documentos de Microsoft"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- interfaces [Reporting Services]
- delivery extensions [Reporting Services], implementing
ms.assetid: aee1608d-374f-4ad3-bc23-fe07fdaa52b7
caps.latest.revision: 34
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: a6aab5e722e732096e9e4ffdf458ac25088e09ae
ms.openlocfilehash: 7bbaf0976e9b145df33e04eea93a5d2ae0408c11
ms.contentlocale: es-es
ms.lasthandoff: 08/12/2017

---
# <a name="preparing-to-implement-a-delivery-extension"></a>Preparar la implementación de una extensión de entrega
  Antes de implementar la extensión de entrega de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], debería definir las interfaces que se van a implementar. Primero hay que decidir cómo se utilizará la extensión de entrega, qué valores requerirá y la funcionalidad concreta que tendrá que implementar para entregar las notificaciones de informes.  
  
 Cada extensión de entrega de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] debe proporcionar la funcionalidad siguiente:  
  
-   Una implementación de la interfaz <xref:Microsoft.ReportingServices.Interfaces.IExtension> que representa la extensión y un nombre de extensión traducido.  
  
-   Una implementación <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> que crea una extensión de entrega que se puede utilizar para entregar notificaciones de informe a los usuarios finales.  
  
-   La capacidad de procesar los datos de usuarios concretos para una suscripción.  
  
 Cada extensión de entrega puede mejorarse para incluir la funcionalidad siguiente:  
  
-   Una implementación del control de usuario de [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] que permite a los usuarios finales utilizar el Administrador de informes para crear suscripciones de informe que utilizan la extensión de entrega.  
  
 En la tabla siguiente se describen las interfaces y la clases disponibles para las extensiones de entrega.  
  
|Interfaz o clase|Description|  
|------------------------|-----------------|  
|<xref:Microsoft.ReportingServices.Interfaces.IExtension> Interfaz|Representa una extensión en [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].|  
|<xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> Interfaz|Representa una extensión de entrega en [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].|  
|<xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> Interfaz|Contiene información sobre el servidor de informes que requieren las extensiones de entrega (por ejemplo, una lista de las extensiones de representación disponibles).|  
|<xref:Microsoft.ReportingServices.Interfaces.Setting>Clase|Representa un valor para una extensión.|  
|<xref:Microsoft.ReportingServices.Interfaces.Notification>Clase|Contiene información de suscripción que las extensiones de entrega utilizan para entregar los informes.|  
|<xref:Microsoft.ReportingServices.Interfaces.Report>Clase|Representa la información específica del informe y los métodos que permiten a las extensiones de entrega entregar los informes a los usuarios.|  
|<xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile>Clase|Representa la salida de una extensión de representación. Un objeto <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> contiene el nombre de archivo asociado e información de tipo que requiere la extensión de entrega para procesar el flujo que devuelve la extensión de representación.|  
|<xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl> Interfaz|Un control de usuario que representa los medios para recuperar la información de la suscripción específica de la extensión de entrega del usuario en el Administrador de informes (por ejemplo, una dirección de correo electrónico o la ruta de acceso a un recurso compartido de archivos).|  
  
## <a name="see-also"></a>Vea también  
 [Extensiones de Reporting Services](../../../reporting-services/extensions/reporting-services-extensions.md)   
 [Implementar una extensión de entrega](../../../reporting-services/extensions/delivery-extension/implementing-a-delivery-extension.md)   
 [Biblioteca de extensión de Reporting Services](../../../reporting-services/extensions/reporting-services-extension-library.md)  
  
  