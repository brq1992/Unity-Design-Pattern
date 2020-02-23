# Command Pattern 命令模式
## Definition
Encapsulate a request as an object, thereby letting you parameterize clients with different requests, queue or log requests, and support undoable operations.
<br>命令模式将“请求”封装成对象，以便使用不同的请求、队列或者日志来参数化其他对象，同时支持可撤消的操作。

![](https://github.com/QianMo/Unity-Design-Pattern/blob/master/UML_Picture/command.gif) 

## Applicability

Use the Command pattern when you want ot

* parameterize objects by an action to perform.
<br>通过抽象出待执行的行为来参数化某对象。

* specify, queue and excute requests at different times.
<br>在不同的时刻指定、排列以及执行请求。

*support undo.
<br>支持撤销操作

* supporting logging changes so that these changes can be reapplied in case of a system crash.
<br>支持记录日志，当系统崩溃时可以恢复命令

* structure a system around high-level operations built on primitives operations.
<br>用构建在原始操作的基础上的高层次操作构造一个系统。

## Participants
The classes and objects participating in this pattern are:

### Command
* declares an interface for executing an operation

### ConcreteCommand
* defines a binding between a Receiver object and an action
* implements Execute by invoking the corresponding operation(s) on Receiver

### Client 
* creates a ConcreteCommand object and sets its receiver

### Invoker
* asks the command to carry out the request

### Receiver
* knows how to perform the operations associated with carrying out the request.

## Collabrations

* the client creates a concrete comand  object and specifies its receiver.
* an invoker object stores the concrete command object.
* the invoker issues a request by calling execute on the command. When commands are undoable, concrete command stores state for undoing the command prior to invoking execute.
* the concrete command object invokes operations on its receiver to carry out the request.

The following diagram shows the interactions between these objects. it illustrates how command decouples the invoker from the receiver (and the request it carry out).



 
