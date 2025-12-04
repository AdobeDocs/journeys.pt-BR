---
product: adobe campaign
title: distinctWithNull
description: Saiba mais sobre a função distinctWithNull
feature: Journeys
role: Developer
level: Experienced
exl-id: 65a904c1-14ff-42b3-8f03-abb97ef47625
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 5%

---

# distinctWithNull {#distinctWithNull}

Retorna os valores ou objetos distintos de uma determinada lista. Se a lista tiver pelo menos uma entrada nula, uma entrada nula estará presente na lista retornada.

## Categoria

Lista

## Sintaxe da função

`distinctWithNull(<parameters>)`

## Parâmetros

| Parâmetro | Tipo | Descrição |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly ou listObject | Lista a processar. Para listObject, ele deve ser uma referência de campo. |
| keyAttributeName | sequência de caracteres | Este parâmetro é opcional e somente para listObject. Se o parâmetro não for fornecido, um objeto será considerado duplicado se todos os atributos tiverem os mesmos valores. Caso contrário, um objeto será considerado duplicado se o atributo em questão tiver o mesmo valor. |

## Assinaturas e tipos retornados

`distinctWithNull(<listInteger>)`

Retorna uma lista de inteiros.

`distinctWithNull(<listDecimal>)`

Retorna uma lista de decimais.

`distinctWithNull(<listString>)`

Retorna uma lista de strings.

`distinctWithNull(<listDateTimeOnly>)`

Retorna uma lista de datetimes sem considerar o fuso horário.

`distinctWithNull(<listDateTime>)`

Retorna uma lista de datetimes.

`distinctWithNull(<listDateOnly>)`

Retorna uma lista de datas.

`distinctWithNull(<listBoolean>)`

Retorna uma lista de booleanos.

`distinctWithNull(<listDuration>)`

Retorna uma lista de durações.

`distinctWithNull(<listObject>)`

`distinctWithNull(<listObject>,<string>)`

Retorna uma lista de objetos.

## Exemplos

`distinctWithNull([10,2,10,null])`

Retorna [10, 2, nulo]
