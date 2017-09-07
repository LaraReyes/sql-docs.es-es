---
title: Provocar y definir eventos en una tarea personalizada | Documentos de Microsoft
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SSIS events, custom
- status information [SQL Server], task events
- custom tasks [Integration Services], events
- SSIS custom tasks, events
- IDTSComponentEvents interface
- events [Integration Services], custom
- events [Integration Services], runtime
- custom events [Integration Services]
- SSIS events, runtime
- IDTSEvents interface
ms.assetid: e0898aa1-e90c-4c4e-99d4-708a76efddfd
caps.latest.revision: 53
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 44e27c1ff000046744aa78479b73cc8ef39d6f2e
ms.contentlocale: es-es
ms.lasthandoff: 08/03/2017

---
# <a name="raising-and-defining-events-in-a-custom-task"></a>Provocar y definir eventos en una tarea personalizada
  El motor en tiempo de ejecución de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] facilita una colección de eventos que proporciona el estado del progreso de una tarea cuando esta se valida y ejecuta. La interfaz <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> define estos eventos y se proporciona a las tareas como un parámetro para los métodos <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Validate%2A> y <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Execute%2A>.  
  
 Hay otro conjunto de eventos, que se definen en la interfaz <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents>, que produce <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> en nombre de la tarea. <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> provoca eventos que se producen antes y después de la validación y ejecución, mientras que la tarea provoca los eventos que se producen durante la ejecución y validación.  
  
## <a name="creating-custom-events"></a>Crear eventos personalizados  
 Los programadores de tareas personalizadas pueden definir eventos nuevos y personalizados creando un nuevo <xref:Microsoft.SqlServer.Dts.Runtime.EventInfo> en su implementación invalidada del método <xref:Microsoft.SqlServer.Dts.Runtime.Task.InitializeTask%2A>. Después de la <xref:Microsoft.SqlServer.Dts.Runtime.EventInfo> está creado, se agrega a la **EventInfos** colección utilizando la <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos.Add%2A> método. La firma de método del método <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos.Add%2A> es como sigue:  
  
 `public void Add(string eventName, string description, bool allowEventHandlers, string[] parameterNames, TypeCode[] parameterTypes, string[] parameterDescriptions);`  
  
 En el siguiente ejemplo de código se muestra el método **InitializeTask** de una tarea personalizada, donde se crean dos eventos personalizados y se establecen sus propiedades. Los nuevos eventos se agregan a la colección <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos>.  
  
 El primer evento personalizado tiene un *eventName* de "**OnBeforeIncrement**" y una *description* de "**Se activa una vez actualizado el valor inicial**". El parámetro siguiente, el valor **true**, indica que este evento debe permitir la creación de un contenedor de controladores de eventos para controlar el evento. El controlador de eventos es un contenedor que proporciona estructura en un paquete y sirve a las tareas, como otros contenedores tales como el paquete, Sequence, ForLoop y ForEachLoop. Cuando el *allowEventHandlers* parámetro es **true**, <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> se crean objetos para el evento. Cualquier parámetro definido para el evento está ahora disponible a <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> en la colección de variables de <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>.  
  
```csharp  
public override void InitializeTask(Connections connections,  
   VariableDispenser variables, IDTSInfoEvents events,  
   IDTSLogging log, EventInfos eventInfos,  
   LogEntryInfos logEntryInfos, ObjectReferenceTracker refTracker)  
{  
    this.eventInfos = eventInfos;  
    string[] paramNames = new string[1];  
    TypeCode[] paramTypes = new TypeCode[1]{TypeCode.Int32};  
    string[] paramDescriptions = new string[1];  
  
    paramNames[0] = "InitialValue";  
    paramDescriptions[0] = "The value before it is incremented.";  
  
    this.eventInfos.Add("OnBeforeIncrement",   
      "Fires before the task increments the value.",  
      true,paramNames,paramTypes,paramDescriptions);  
    this.onBeforeIncrement = this.eventInfos["OnBeforeIncrement"];  
  
    paramDescriptions[0] = "The value after it has been incremented.";  
    this.eventInfos.Add("OnAfterIncrement",  
      "Fires after the initial value is updated.",  
      true,paramNames, paramTypes,paramDescriptions);  
    this.onAfterIncrement = this.eventInfos["OnAfterIncrement"];  
}  
```  
  
```vb  
Public Overrides Sub InitializeTask(ByVal connections As Connections, _  
ByVal variables As VariableDispenser, ByVal events As IDTSInfoEvents, _  
ByVal log As IDTSLogging, ByVal eventInfos As EventInfos, _  
ByVal logEntryInfos As LogEntryInfos, ByVal refTracker As ObjectReferenceTracker)   
  
    Dim paramNames(0) As String  
    Dim paramTypes(0) As TypeCode = {TypeCode.Int32}  
    Dim paramDescriptions(0) As String  
  
    Me.eventInfos = eventInfos  
  
    paramNames(0) = "InitialValue"  
    paramDescriptions(0) = "The value before it is incremented."  
  
    Me.eventInfos.Add("OnBeforeIncrement", _  
      "Fires before the task increments the value.", _  
      True, paramNames, paramTypes, paramDescriptions)  
    Me.onBeforeIncrement = Me.eventInfos("OnBeforeIncrement")  
  
    paramDescriptions(0) = "The value after it has been incremented."  
    Me.eventInfos.Add("OnAfterIncrement", _  
      "Fires after the initial value is updated.", True, _  
      paramNames, paramTypes, paramDescriptions)  
    Me.onAfterIncrement = Me.eventInfos("OnAfterIncrement")  
  
End Sub  
```  
  
## <a name="raising-custom-events"></a>Provocar eventos personalizados  
 Los eventos personalizados se generan llamando al método <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireCustomEvent%2A>. La siguiente línea de código provoca un evento personalizado.  
  
```csharp  
componentEvents.FireCustomEvent(this.onBeforeIncrement.Name,  
   this.onBeforeIncrement.Description, ref arguments,  
   null, ref bFireOnBeforeIncrement);  
```  
  
```vb  
componentEvents.FireCustomEvent(Me.onBeforeIncrement.Name, _  
Me.onBeforeIncrement.Description, arguments, _  
Nothing,  bFireOnBeforeIncrement)  
```  
  
## <a name="sample"></a>Ejemplo  
 En el ejemplo siguiente se muestra una tarea que define un evento personalizado en el **InitializeTask** método, agrega el evento personalizado a la <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos> colección y, a continuación, genera el evento personalizado durante su **Execute** método mediante una llamada a la <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireCustomEvent%2A> método.  
  
```csharp  
[DtsTask(DisplayName = "CustomEventTask")]  
    public class CustomEventTask : Task  
    {  
        public override DTSExecResult Execute(Connections connections,   
          VariableDispenser variableDispenser, IDTSComponentEvents componentEvents,  
           IDTSLogging log, object transaction)  
        {  
            bool fireAgain;  
            object[] args = new object[1] { "The value of the parameter." };  
            componentEvents.FireCustomEvent( "MyCustomEvent",   
              "Firing the custom event.", ref args,  
              "CustomEventTask" , ref fireAgain );  
            return DTSExecResult.Success;  
        }  
  
        public override void InitializeTask(Connections connections,  
          VariableDispenser variableDispenser, IDTSInfoEvents events,  
          IDTSLogging log, EventInfos eventInfos,  
          LogEntryInfos logEntryInfos, ObjectReferenceTracker refTracker)  
        {  
            string[] names = new string[1] {"Parameter1"};  
            TypeCode[] types = new TypeCode[1] {TypeCode.String};  
            string[] descriptions = new string[1] {"Parameter description." };  
  
            eventInfos.Add("MyCustomEvent",  
             "Fires when my interesting event happens.",  
             true, names, types, descriptions);  
  
        }  
   }  
```  
  
```vb  
<DtsTask(DisplayName = "CustomEventTask")> _   
    Public Class CustomEventTask  
     Inherits Task  
        Public Overrides Function Execute(ByVal connections As Connections, _  
          ByVal variableDispenser As VariableDispenser, _  
          ByVal componentEvents As IDTSComponentEvents, _  
          ByVal log As IDTSLogging, ByVal transaction As Object) _  
          As DTSExecResult  
  
            Dim fireAgain As Boolean  
            Dim args() As Object =  New Object(1) {"The value of the parameter."}  
  
            componentEvents.FireCustomEvent("MyCustomEvent", _  
              "Firing the custom event.", args, _  
              "CustomEventTask" ,  fireAgain)  
            Return DTSExecResult.Success  
        End Function  
  
        Public Overrides  Sub InitializeTask(ByVal connections As Connections, _  
          ByVal variableDispenser As VariableDispenser,  
          ByVal events As IDTSInfoEvents,  
          ByVal log As IDTSLogging, ByVal eventInfos As EventInfos, ByVal logEnTryInfos As LogEnTryInfos, ByVal refTracker As ObjectReferenceTracker)  
  
            Dim names() As String =  New String(1) {"Parameter1"}  
            Dim types() As TypeCode =  New TypeCode(1) {TypeCode.String}  
            Dim descriptions() As String =  New String(1) {"Parameter description."}  
  
            eventInfos.Add("MyCustomEvent", _  
              "Fires when my interesting event happens.", _  
              True, names, types, descriptions)  
  
        End Sub  
  
    End Class  
```  
  
## <a name="see-also"></a>Vea también  
 [Integration Services &#40; SSIS &#41; Controladores de eventos](../../../integration-services/integration-services-ssis-event-handlers.md)   
 [Agregar un controlador de eventos a un paquete](http://msdn.microsoft.com/library/5e56885d-8658-480a-bed9-3f2f8003fd78)  
  
  