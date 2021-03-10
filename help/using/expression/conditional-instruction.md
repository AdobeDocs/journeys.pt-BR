---
product: adobe campaign
solution: Journey Orchestration
title: Instrução condicional (if, then, else)
description: Saiba mais sobre instrução condicional
feature: Jornada
role: Engenheiro de dados
level: Experienciado
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 0%

---


# Instrução condicional (if, then, else) {#section_cdz_lsk_w3b}

A instrução condicional (if, then, else) é compatível no editor avançado. Ela permite definir expressões mais complexas. Ele é composto pelos seguintes elementos:

* **[!UICONTROL if]**: a condição a ser avaliada primeiro.
* **[!UICONTROL then]**: a expressão a ser avaliada caso o resultado da avaliação de condição seja true.
* **[!UICONTROL else]**: a expressão a ser avaliada caso o resultado da avaliação de condição seja false.

>[!NOTE]
>
>Os parênteses são necessários em todas as expressões.

```
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>` deve retornar um  **booleano**.

`<expression2>` e  `<expression3>` devem ter o mesmo tipo ou tipos compatíveis. As assinaturas compatíveis e os tipos retornados são:

```
boolean,boolean : boolean
dateTime,dateTime : dateTime
dateTimeOnly,dateTimeOnly : dateTimeOnly
decimal,integer : decimal
integer,decimal : integer
integer,decimal : decimal
duration,duration : duration
string,string : string
listBoolean,listBoolean : listBoolean
listDateTime,listDateTime : listDateTime
listDateTimeOnly,listDateTimeOnly : listDateTimeOnly
listDecimal,listDecimal : listDecimal
listInteger,listInteger : listInteger
listString,listString : listString
```

**Uso**

A instrução condicional permite otimizar o workflow do jornada, reduzindo o número de atividades de condição. Por exemplo, na mesma atividade de ação, é possível especificar duas alternativas para uma definição de campo usando apenas uma expressão de condição.

Exemplo para uma atividade de ação (para um campo que espera uma string como resultado da instrução condicional):

```
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
