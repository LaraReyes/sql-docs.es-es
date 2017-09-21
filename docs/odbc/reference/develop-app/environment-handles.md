---
title: Identificadores de entorno | Documentos de Microsoft
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- environment handles [ODBC]
- handles [ODBC], environment
ms.assetid: 917f1b0c-272b-4e37-a1f5-87cd24b9fa21
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 1f563e798c985ebb8ea8ab7925ed39f3d154d144
ms.contentlocale: es-es
ms.lasthandoff: 09/09/2017

---
# <a name="environment-handles"></a>Identificadores de entorno
Un *entorno* es un contexto global en el que se va a obtener acceso a datos; asociado a un entorno es toda la información que es global por naturaleza, como:  
  
-   Estado del entorno  
  
-   Los diagnósticos de nivel del entorno actuales  
  
-   Los identificadores de conexiones actualmente asignados en el entorno  
  
-   La configuración actual de cada atributo de entorno  
  
 Dentro de un fragmento de código que implementa ODBC (el Administrador de controladores o un controlador), un identificador de entorno identifica una estructura para que contenga esta información.  
  
 Identificadores de entorno no se usan con frecuencia en aplicaciones de ODBC. Siempre se utilizan en las llamadas a **SQLDataSources** y **SQLDrivers** y a veces se usan en las llamadas a **SQLAllocHandle**, **SQLEndTran**, **SQLFreeHandle**, **SQLGetDiagField**, y **SQLGetDiagRec**.  
  
 Cada fragmento de código que implementa ODBC (el Administrador de controladores o un controlador) contiene uno o varios identificadores de entorno. Por ejemplo, el Administrador de controladores mantiene un identificador de entorno independiente para cada aplicación que está conectado a ella. Se asignan a identificadores de entorno **SQLAllocHandle** y liberado con **SQLFreeHandle**.