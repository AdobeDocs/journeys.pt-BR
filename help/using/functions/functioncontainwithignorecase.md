---
product: adobe campaign
title: containWithIgnoreCase
description: Saiba mais sobre a função containWithIgnoreCase
feature: Jornadas
role: Data Engineer
level: Experienced
exl-id: ebec646e-9dbb-4432-a430-ab69fb7d75cf
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 24%

---

# containWithIgnoreCase {#containWithIgnoreCase}

Verifica se a segunda string de argumento está contida na primeira string de argumento, sem considerar o caso.

## Categoria

String

## Sintaxe da função

`containWithIgnoreCase(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| string | string |
| string pesquisada | string |

## Assinatura e tipo retornado

`containWithIgnoreCase(<string>,<string>)`

Retorna um booleano.

## Exemplo

`containWithIgnoreCase("rowing is great', "GREAT")`

Retorna true.
