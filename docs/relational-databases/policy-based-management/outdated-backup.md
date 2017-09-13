---
title: Copia de seguridad no actualizada | Microsoft Docs
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 307a4ad0-675a-4f97-9a3c-cedd61bdfae5
caps.latest.revision: 11
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 94f220565078ceddac2aa43eb8e88f9895c27e9d
ms.contentlocale: es-es
ms.lasthandoff: 06/22/2017

---
# <a name="outdated-backup"></a>Copia de seguridad no actualizada
  Esta regla comprueba que una base de datos tiene copias de seguridad recientes. Programar copias de seguridad regulares es importante para proteger las bases de datos contra la pérdida de datos que provocan numerosos errores diferentes. La frecuencia adecuada para la copia de seguridad de los datos depende del modelo de recuperación de la base de datos, de los requisitos comerciales sobre la pérdida de datos potencial y de la frecuencia con que se actualiza la base de datos. En una base de datos actualizada frecuentemente, el riesgo de perder parte del trabajo aumenta con bastante rapidez entre las copias de seguridad.  
  
## <a name="best-practices-recommendations"></a>Prácticas recomendadas  
 Recomendamos que realice frecuentemente suficientes copias de seguridad para proteger las bases de datos contra la pérdida de datos.  
  
 El modelo de recuperación simple y el modelo de recuperación completa requieren ambos copias de seguridad de los datos. En cualquier modelo de recuperación puede complementar las copias de seguridad completas con copias de seguridad diferenciales para reducir eficazmente el riesgo de pérdida de datos.  
  
 En una base de datos que use el modelo de recuperación completa, recomendamos que realice copias de seguridad del registro con frecuencia. En una base de datos de producción que contiene datos muy importantes, las copias de seguridad del registro normalmente se realizarían en intervalos de entre uno y quince minutos.  
  
> [!NOTE]  
>  El método recomendado para programar las copias de seguridad es un plan de mantenimiento de bases de datos.  
  
## <a name="for-more-information"></a>Para obtener más información  
 [Realizar copias de seguridad y restaurar bases de datos del sistema &#40;SQL Server&#41;](../../relational-databases/backup-restore/back-up-and-restore-of-system-databases-sql-server.md)  
  
 [Modelos de recuperación &#40;SQL Server&#41;](../../relational-databases/backup-restore/recovery-models-sql-server.md)  
  
 [Crear una copia de seguridad diferencial de una base de datos &#40;SQL Server&#41;](../../relational-databases/backup-restore/create-a-differential-database-backup-sql-server.md)  
  
 [Crear una copia de seguridad completa de base de datos &#40;SQL Server&#41;](../../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md)  
  
 [Planes de mantenimiento](../../relational-databases/maintenance-plans/maintenance-plans.md)  
  
 [Copias de seguridad del registro de transacciones &#40;SQL Server&#41;](../../relational-databases/backup-restore/transaction-log-backups-sql-server.md)  
  
## <a name="see-also"></a>Vea también  
 [Supervisar y aplicar las prácticas recomendadas usando la administración basada en directivas](../../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  