---
title: GetPermissions (método, ADOX) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- _User25::GetPermissions
- _Group25::raw_GetPermissions
- _Group25::GetPermissions
- _User25::raw_GetPermissions
helpviewer_keywords:
- GetPermissions method [ADOX]
ms.assetid: df201c1f-c76a-465d-98f0-83b7fc36e6e3
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 6517b09e682853492cd129e0c43abfd7164ed2e7
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47648999"
---
# <a name="getpermissions-method-adox"></a>GetPermissions (método, ADOX)
Devuelve los permisos para un [grupo](../../../ado/reference/adox-api/group-object-adox.md) o [usuario](../../../ado/reference/adox-api/user-object-adox.md) en un objeto o un contenedor de objetos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
ReturnValue=GroupOrUser.GetPermissions(Name, ObjectType    [,ObjectTypeId])  
```  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve un **largo** valor que especifica una máscara de bits que contiene los permisos que tiene el usuario o grupo en el objeto. Este valor puede ser uno o varios de los [RightsEnum](../../../ado/reference/adox-api/rightsenum.md) constantes.  
  
#### <a name="parameters"></a>Parámetros  
 *Nombre*  
 Un **Variant** valor que especifica el nombre del objeto que se va a establecer permisos. Establecer *nombre* en un valor nulo si desea obtener los permisos para el contenedor de objetos.  
  
 *ObjectType*  
 Un **largo** valor puede ser uno de los [ObjectTypeEnum](../../../ado/reference/adox-api/objecttypeenum.md) constantes, que especifica el tipo del objeto que se va a obtener los permisos.  
  
 *Valor de ObjectTypeId*  
 Opcional. Un **Variant** valor que especifica el GUID para un tipo de objeto de proveedor no definido por la especificación de OLE DB. Este parámetro es obligatorio si *ObjectType* está establecido en **adPermObjProviderSpecific**; en caso contrario, no se utiliza.  
  
## <a name="applies-to"></a>Se aplica a  
  
|||  
|-|-|  
|[Objeto Group (ADOX)](../../../ado/reference/adox-api/group-object-adox.md)|[Objeto User (ADOX)](../../../ado/reference/adox-api/user-object-adox.md)|  
  
## <a name="see-also"></a>Vea también  
 [GetPermissions y SetPermissions métodos ejemplo (VB)](../../../ado/reference/adox-api/getpermissions-and-setpermissions-methods-example-vb.md)   
 [Nombre (propiedad, ADOX)](../../../ado/reference/adox-api/name-property-adox.md)   
 [SetPermissions (método, ADOX)](../../../ado/reference/adox-api/setpermissions-method-adox.md)
