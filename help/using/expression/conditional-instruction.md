---
product: adobe campaign
solution: Journey Orchestration
title: Instrução condicional (if, then, else)
description: Saiba mais sobre instruções condicionais
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 0%

---


# Instrução condicional (if, then, else) {#section_cdz_lsk_w3b}

A instrução condicional (if, then, else) é suportada no editor avançado. Permite definir expressões mais complexas. É composto pelos seguintes elementos:

* **[!UICONTROL if]**: a condição a avaliar primeiro.
* **[!UICONTROL then]**: a expressão a avaliar caso o resultado da avaliação da condição seja verdadeiro.
* **[!UICONTROL else]**: a expressão a ser avaliada caso o resultado da avaliação da condição seja falso.

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

`<expression2>` e  `<expression3>` devem ter o mesmo tipo ou tipos compatíveis. As assinaturas suportadas e os tipos retornados são:

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

A instrução condicional permite otimizar o fluxo de trabalho da jornada reduzindo o número de atividades de condição. Por exemplo, na mesma atividade de ação, é possível especificar duas alternativas para uma definição de campo usando apenas uma expressão de condição.

Exemplo de uma atividade de ação (para um campo que espera uma string como resultado da instrução condicional):

```
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
