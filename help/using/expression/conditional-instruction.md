---
product: adobe campaign
title: Instrução condicional (if, then, else)
description: Saiba mais sobre instrução condicional
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 48fb4944-5b78-4ccd-9b9b-ffe0719e7c21
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 0%

---

# Instrução condicional (if, then, else) {#section_cdz_lsk_w3b}


>[!CAUTION]
>
>**Procurando Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para obter a documentação do Journey Optimizer.
>
>
>_Esta documentação se refere ao material herdado do Journey Orchestration que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de conta em caso de dúvidas sobre o acesso ao Journey Orchestration ou Journey Optimizer._


A instrução condicional (if, then, else) é compatível com o editor avançado. Ele permite definir expressões mais complexas. Ele é composto pelos seguintes elementos:

* **[!UICONTROL if]**: a condição a ser avaliada primeiro.
* **[!UICONTROL then]**: a expressão a ser avaliada caso o resultado da avaliação da condição seja verdadeiro.
* **[!UICONTROL else]**: a expressão a ser avaliada caso o resultado da avaliação da condição seja falso.

>[!NOTE]
>
>São necessários parênteses em todas as expressões.

```json
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>` deve retornar um **booleano**.

`<expression2>` e `<expression3>` devem ter o mesmo tipo ou tipos compatíveis. As assinaturas compatíveis e os tipos retornados são:

```json
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
listDateOnly,listDateOnly : listDateOnly
listDecimal,listDecimal : listDecimal
listInteger,listInteger : listInteger
listString,listString : listString
```

**Uso**

A instrução condicional permite otimizar o workflow de jornada reduzindo o número de atividades de condição. Por exemplo, na mesma atividade de ação, é possível especificar duas alternativas para uma definição de campo usando apenas uma expressão de condição.

Exemplo de uma atividade de ação (para um campo que espera uma string como o resultado da instrução condicional):

```json
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
