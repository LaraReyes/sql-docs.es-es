---
title: Sys.spatial_reference_systems (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- spatial_reference_systems_TSQL
- sys.spatial_reference_systems_TSQL
- sys.spatial_reference_systems
- spatial_reference_systems
dev_langs:
- TSQL
helpviewer_keywords:
- sys.spatial_reference_systems catalog view
- spatial_reference_systems
ms.assetid: 3c9bc120-67c3-463f-9e24-29fd623f25a0
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: c2ab77dbaf90edf1421a0d15073258c370de4c7d
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47643443"
---
# <a name="sysspatialreferencesystems-transact-sql"></a>sys.spatial_reference_systems (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Enumera los sistemas de referencia espacial (SRID) que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] admite.  

  
|Nombre de columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|spatial_reference_id|**int**|SRID que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] admite.|  
|authority_name|**nvarchar(128)**|Autoridad del SRID.|  
|authorized_spatial_reference_id|**int**|SRID proporcionado por la autoridad denominada **authority_name**.|  
|well_known_text|**nvarchar(4000)**|Representación WKT del SRID.|  
|unit_of_measure|**nvarchar(128)**|Nombre de la unidad de medida.|  
|unit_conversion_factor|**float**|Longitud de la unidad de medida en metros.|  
  
## <a name="permissions"></a>Permisos  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)]  
  
  
