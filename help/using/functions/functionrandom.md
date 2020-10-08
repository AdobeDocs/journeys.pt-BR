---
title: random
description: Saiba mais sobre a função aleatória
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 5%

---


# random {#random}

Gera um número aleatório entre 0 e 1.

## Categoria

Matemática

## Sintaxe da função

`random(<parameters>)`

## Assinatura e tipo retornado

`random()`

Retorna um decimal.

## Exemplo

`#{MarltonReservation.statistics.successRatio, defaultValue : random() * 100}`

Explicação: se a taxa de sucesso não tiver valor/for nulo, o valor padrão será aplicado e será um valor aleatório entre 0 e 1 * 100 (ou seja, de 0 a 100).
