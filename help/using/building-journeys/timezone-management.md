---
title: Gerenciamento de fuso horário
description: Saiba mais sobre o gerenciamento de fuso horário
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
source-wordcount: '261'
ht-degree: 2%

---



# Gerenciamento de fuso horário {#timezone_management}

Você pode definir um fuso horário nas [propriedades](../building-journeys/changing-properties.md) de sua jornada.

Para acessar Propriedades, clique no ícone de lápis na parte superior direita da tela.

Este fuso horário será utilizado para cada atividade da viagem que contenha um elemento de tempo, como:

* [Condição de tempo](../building-journeys/condition-activity.md#time_condition)
* [Condição de data](../building-journeys/condition-activity.md#date_condition)
* [Espera personalizada](../building-journeys/wait-activity.md#custom)
* [Data de espera fixa](../building-journeys/wait-activity.md#fixed_date)

Você pode selecionar um fuso horário ou optar por usar o fuso horário definido no perfil do usuário.

## Definição de um fuso horário fixo {#fixed-timezone}

O fuso horário também pode ser fixo. Limpe o fuso horário predefinido e escolha um na lista suspensa. Se você usar um fuso horário fixo, ele será o mesmo para todos os indivíduos que entram na jornada.

Para fazer isso, em **[!UICONTROL Properties]**, selecione um fuso horário.

![](../assets/journey73.png)

## Uso de perfis para definir o fuso horário da jornada {#timezone-from-profiles}

Se o evento de entrada da viagem tiver uma namespace, o que significa que a viagem pode chegar ao serviço de Perfil do cliente em tempo real da Adobe Experience Platform, o fuso horário é pré-definido com o especificado no perfil do indivíduo que flui na viagem.

Se um fuso horário for definido no perfil Adobe Experience Platform, ele poderá ser recuperado na jornada.

Se o perfil do indivíduo não contiver um fuso horário, o fuso horário recuperado será aquele definido no campo de fuso horário.

Para fazer isso, faça **[!UICONTROL Properties]**, verifique **[!UICONTROL Use Profile timezone in timers and conditions]**.

![](../assets/journey72.png)

## Uso de fusos horários no expressão {#timezone-in-expressions}

As datas de start e de fim de uma viagem não podem estar ligadas a um fuso horário específico. Eles são associados automaticamente ao fuso horário da instância.
