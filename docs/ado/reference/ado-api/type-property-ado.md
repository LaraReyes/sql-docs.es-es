---
title: Type (propiedad) (ADO) | Documentos de Microsoft
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
f1_keywords:
- _Parameter::Type
- Field20::Type
helpviewer_keywords:
- Type property [ADO]
ms.assetid: 8a4c079f-9f4f-4545-801d-85983b8db71e
caps.latest.revision: 7
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 663a17993b9bd614efd2436ae3050d78d7fd9e73
ms.contentlocale: es-es
ms.lasthandoff: 09/09/2017

---
# <a name="type-property-ado"></a>Tipo (propiedad, ADO)
Indica el tipo de datos o tipo operativo de un [parámetro](../../../ado/reference/ado-api/parameter-object.md), [campo](../../../ado/reference/ado-api/field-object.md), o [propiedad](../../../ado/reference/ado-api/property-object-ado.md) objeto.  
  
## <a name="settings-and-return-values"></a>Configuración y valores devueltos  
 Establece o devuelve un [DataTypeEnum](../../../ado/reference/ado-api/datatypeenum.md) valor.  
  
## <a name="remarks"></a>Comentarios  
 Para **parámetro** objetos, el **tipo** propiedad es de lectura/escritura. Para obtener nuevos **campo** objetos que se han anexado a la [campos](../../../ado/reference/ado-api/fields-collection-ado.md) colección de un [registro](../../../ado/reference/ado-api/record-object-ado.md), **tipo** es lectura/escritura después de la [ Valor](../../../ado/reference/ado-api/value-property-ado.md) propiedad para la **campo** se ha especificado y el proveedor de datos ha agregado correctamente el nuevo **campo** mediante una llamada a la [actualizar](../../../ado/reference/ado-api/update-method.md)método de la **campos** colección.  
  
 Para todos los demás objetos, la **tipo** propiedad es de solo lectura.  
  
## <a name="applies-to"></a>Se aplica a  
  
||||  
|-|-|-|  
|[Objeto Field](../../../ado/reference/ado-api/field-object.md)|[Objeto de parámetro](../../../ado/reference/ado-api/parameter-object.md)|[Objeto Property (ADO)](../../../ado/reference/ado-api/property-object-ado.md)|  
  
## <a name="see-also"></a>Vea también  
 [Ejemplo de la propiedad de tipo (campo) (VB)](../../../ado/reference/ado-api/type-property-example-field-vb.md)   
 [Ejemplo de la propiedad de tipo (propiedad) (VC ++)](../../../ado/reference/ado-api/type-property-example-property-vc.md)   
 [Propiedad Tiporegistro (ADO)](../../../ado/reference/ado-api/recordtype-property-ado.md)   
 [Propiedad Type (objeto Stream de ADO)](../../../ado/reference/ado-api/type-property-ado-stream.md)
