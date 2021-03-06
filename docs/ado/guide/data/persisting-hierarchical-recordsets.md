---
title: Almacenar conjuntos de registros jerárquicos | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- hierarchical Recordsets [ADO], persisting
- persisting hierarchical Recordsets [ADO]
- data shaping [ADO], hierarchical Recordsets
ms.assetid: 43798bb5-98a6-4ad6-9bf8-78154b3a1827
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 3382e222a03f7538d3c666c3b85527b487d499f7
ms.sourcegitcommit: 63b4f62c13ccdc2c097570fe8ed07263b4dc4df0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "51599790"
---
# <a name="persisting-hierarchical-recordsets"></a>Almacenar conjuntos de registros jerárquicos
Puede guardar un jerárquica **Recordset** en un archivo en formato ADTG o XML mediante una llamada a la [guardar](../../../ado/reference/ado-api/save-method.md) método. Sin embargo, existen dos limitaciones cuando se guarde jerárquica **Recordset**s en formato XML: no se puede guardar en XML si el jerárquica **Recordset** contiene las actualizaciones pendientes, y no se puede guardar un con parámetros jerárquica **Recordset**.  
  
 Para obtener más información acerca del proveedor de la forma de datos, vea [servicio de forma de datos de Microsoft para OLE DB](../../../ado/guide/appendixes/microsoft-data-shaping-service-for-ole-db-ado-service-provider.md) (ADO) y [información general del servicio de forma de datos para OLE DB](https://msdn.microsoft.com/9f51e471-8e85-448e-9fb8-b64bbf767bf3).  
  
## <a name="see-also"></a>Vea también  
 [Ejemplo de la forma de datos](../../../ado/guide/data/data-shaping-example.md)   
 [Gramática formal de forma](../../../ado/guide/data/formal-shape-grammar.md)   
 [Comandos Shape en General](../../../ado/guide/data/shape-commands-in-general.md)
