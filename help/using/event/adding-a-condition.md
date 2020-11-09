---
title: Adicionar uma condição
description: Saiba como adicionar uma condição
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: e353d593ab2710f50a88a3715378c86c2e37b4f6
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 4%

---



# Adicionar uma condição {#concept_rbg_gqt_52b}

A condição do evento permite que o sistema filtre o processamento de eventos. Se a condição for verdadeira, o evento será processado. Se a condição não for verdadeira, o evento será ignorado.

A condição nos eventos só pode ser baseada nos dados transmitidos na carga do evento. A condição definida no nível do evento não pode ser alterada na tela por um comerciante. O objetivo é endurecer essa condição quando esse evento for usado. Por exemplo, se você nunca quiser que os comerciantes usem eventos de abandono do carrinho se o valor do carrinho for muito pequeno, você pode criar uma condição no campo de evento &quot;valor do carrinho&quot; e impor um valor acima de 100 dólares.

Você pode usar o editor de expressões simples ou o editor de expressões avançado para configurar as condições nos eventos. Consulte [esta página](../expression/expressionadvanced.md).

Por exemplo, você pode definir uma condição para processar apenas os eventos de um tipo de evento específico e ignorar os outros tipos. Ou se seu evento for um abandono do carrinho e a carga incluir o campo de valor do carrinho, você poderá definir uma condição de evento para processar os eventos somente se o valor do carrinho for maior que 100 dólares.

![](../assets/journey78.png)
