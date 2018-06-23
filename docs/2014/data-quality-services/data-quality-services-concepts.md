---
title: Conceptos de Data Quality Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- data-quality-services
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 837c71ee-48fa-4044-8744-2be9119aaa04
caps.latest.revision: 15
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: b1f6eb37de996e8956468efb54fa74535e419f44
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36204468"
---
# <a name="data-quality-services-concepts"></a>Conceptos de Data Quality Services
  En este tema se proporciona un breve resumen de los conceptos de [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) en administración del conocimiento, proyectos de calidad de datos y administración de calidad de datos.  
  
##  <a name="Knowledge"></a> Conceptos de administración del conocimiento  
 La base de conocimientos de DQS es un repositorio de metadatos que crea el administrador de datos o el profesional de TI para usarlo en la mejora de la calidad de datos mediante la limpieza y la coincidencia de datos. La administración del conocimiento de DQS incluye los procesos usados para crear y administrar la base de conocimiento, tanto de un modo asistido por el equipo como de forma interactiva.  
  
 **Detección de conocimiento**  
  
 La detección de conocimiento es un proceso asistido por equipo que analiza las muestras de los datos de su organización para compilar el conocimiento acerca de los datos. Una vez que se tienen los resultados del análisis, se puede validar y mejorar el conocimiento; tras ello, se aplica para llevar a cabo la limpieza, coincidencia y generación de perfiles de los datos. Para obtener más información, consulte [DQS Knowledge Bases and Domains](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md).  
  
 **Administración de dominios**  
  
 El proceso de administración de dominios permite cambiar o aumentar el conocimiento que se ha generado mediante el proceso de detección de conocimiento. Puede modificar, actualizar y revisar interactivamente el conocimiento de una base de conocimiento. Una base de conocimiento consta de dominios de datos que contienen valores de dominio y su estado, reglas de dominio, relaciones basadas en términos y datos de referencia. En la administración de dominios, puede cambiar las propiedades de dominio, adjuntar datos de referencia a un dominio, administrar reglas de dominio, administrar valores de dominio y especificar relaciones de datos, así como crear, eliminar, importar o exportar dominios. También puede usar dominios compuestos que agregan varios dominios individuales. Para obtener más información, consulte [DQS Knowledge Bases and Domains](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md).  
  
 **Directiva de coincidencia**  
  
 Una directiva de coincidencia contiene las reglas de coincidencia empleadas para realizar la eliminación de datos duplicados. El proceso de la directiva de coincidencia permite crear reglas de coincidencia, optimizarla según los resultados de coincidencia y generar perfiles de datos, así como agregar la directiva a la base de conocimiento. Para más información, consulte [Data Matching](../../2014/data-quality-services/data-matching.md).  
  
 **Reference Data Services**  
  
 Puede usar los datos de referencia para validar, corregir y enriquecer los datos, aprovechando los servicios de compañías que garantizan la calidad de sus datos de referencia. Puede usar los servicios de Windows Azure MarketPlace para conectar con proveedores de datos de referencia o puede usar una conexión directa a un proveedor. Para más información, consulte [Reference Data Services in DQS](../../2014/data-quality-services/reference-data-services-in-dqs.md).  
  
 Para obtener más información acerca de la administración del conocimiento en DQS, vea [dominios y Bases de conocimiento de DQS](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md).  
  
##  <a name="Projects"></a> Conceptos de proyectos de calidad de los datos  
 El administrador de datos realiza las operaciones de calidad de los datos (limpiar y buscar coincidencias) mediante un proyecto de calidad de datos en la aplicación de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] .  
  
 **Limpieza de datos**  
  
 La limpieza de datos en DQS se realiza en función del conocimiento en una base de conocimiento de DQS. La limpieza de datos de DQS es un proceso de dos pasos:  
  
-   **Limpieza asistida por PC**: DQS utiliza el conocimiento de la base de conocimiento seleccionada para el proyecto de limpieza con el fin de proponer correcciones o sugerencias a los valores de un origen de datos.  
  
-   **Limpieza interactiva**: el administrador de datos puede realizar el proceso de limpieza interactiva para cambiar o aumentar las correcciones de datos que ha propuesto el proceso de limpieza de datos asistido por PC. El administrador de datos lleva a cabo esta operación mediante niveles de confianza y estadísticas que se han identificado mediante el proceso de limpieza de datos o bien especificando sus propios cambios en el proyecto.  
  
 Después de limpiar los datos, el administrador de datos puede exportar los datos procesados a una base de datos SQL Server, a un archivo .csv o un archivo de Excel. Para más información, consulte [Data Cleansing](../../2014/data-quality-services/data-cleansing.md).  
  
 **Coincidencia de datos**  
  
 El proceso de búsqueda de coincidencias permite al administrador de datos comparar los datos a fin de que los datos similares, pero ligeramente distintos, se puedan alinear mediante un proceso de eliminación de datos duplicados. DQS realiza la eliminación de datos duplicados basándose en reglas de coincidencia que están incluidas en la base de conocimiento. El administrador de datos especifica los parámetros para el proceso de búsqueda de coincidencias desde un proyecto de calidad de datos. Para más información, consulte [Data Matching](../../2014/data-quality-services/data-matching.md).  
  
 **Generación de perfiles y notificaciones**  
  
 La generación de perfiles de datos proporciona a los administradores de datos estadísticas en tiempo real e información sobre los datos que va a procesar DQS para las actividades de limpieza o búsqueda de coincidencias mientras se ejecuta un proyecto de calidad de datos. La generación de perfiles de datos ayuda a evaluar la eficacia de las actividades de limpieza y búsqueda de coincidencias en un proyecto de calidad de datos, y las notificaciones ayudan al usuario con las acciones que pueden realizar para mejorar estas actividades. Para obtener más información, consulte [Data Profiling and Notifications in DQS](../../2014/data-quality-services/data-profiling-and-notifications-in-dqs.md).  
  
 Para más información sobre los proyectos de calidad de datos de DQS, vea [Proyectos de calidad de datos &#40;DQS&#41;](../../2014/data-quality-services/data-quality-projects-dqs.md).  
  
##  <a name="Admin"></a> Conceptos de administración de calidad de datos  
 Un administrador de DQS puede realizar una serie de tareas administrativas mediante la aplicación de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] .  
  
 **Supervisión de actividades**  
  
 La supervisión de actividades muestra la situación y el estado de cada actividad realizada en un intervalo de datos, proporciona datos para cada actividad y permite a los administradores de DQS controlar una actividad. Para obtener más información, consulte [supervisar las actividades de DQS](../../2014/data-quality-services/monitor-dqs-activities.md).  
  
 **Configuración**  
  
 La opción de configuración le permite:  
  
-   Configurar los valores de servicio de datos de referencia. Para obtener más información, consulte [configurar DQS para utilizar datos de referencia](../../2014/data-quality-services/configure-dqs-to-use-reference-data.md).  
  
-   Configurar los valores de umbral para las actividades de limpieza y búsqueda de coincidencias. Para obtener más información, consulte [Configurar los valores de umbral para la limpieza y coincidencia](../../2014/data-quality-services/configure-threshold-values-for-cleansing-and-matching.md).  
  
-   Habilitar o deshabilitar las notificaciones de generación de perfiles. Para más información, vea [Habilitar o deshabilitar notificaciones de generación de perfiles en DQS](../../2014/data-quality-services/enable-or-disable-profiling-notifications-in-dqs.md).  
  
-   Configurar niveles de gravedad para los archivos de registro de DQS en el nivel basado en actividad o en el nivel basado en módulo más avanzado. Para obtener más información, consulte [configurar niveles de gravedad de los archivos de registro de DQS](../../2014/data-quality-services/configure-severity-levels-for-dqs-log-files.md).  
  
 **Seguridad de DQS**  
  
 En el mecanismo de seguridad de SQL Server se usan roles para proteger DQS. Hay tres roles de DQS que determinan el nivel de acceso de un usuario en la aplicación de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] : dqs_administrator, dqs_kb_editor y dqs_kb_operator. No puede conceder roles a los usuarios mediante la aplicación de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] ; esto se realiza mediante SQL Server Management Studio. Para obtener más información, consulte [DQS Security](../../2014/data-quality-services/dqs-security.md).  
  
 Para obtener más información sobre la administración de DQS, vea [administración de DQS](../../2014/data-quality-services/dqs-administration.md).  
  
## <a name="see-also"></a>Vea también  
 [Data Quality Services](../../2014/data-quality-services/data-quality-services.md)  
  
  