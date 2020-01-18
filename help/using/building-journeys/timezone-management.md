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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f57cc43d8f2a223c04cc4ccccb3b3c3e0bcadfc1

---



# Gerenciamento de fuso horário {#timezone_management}

A definição de fuso horário está disponível nas seguintes atividades:

* [](../building-journeys/condition-activity.md#time_condition)
* [](../building-journeys/condition-activity.md#date_condition)
* [](../building-journeys/wait-activity.md#custom)
* [](../building-journeys/wait-activity.md#fixed_date)

Se o evento de entrada da jornada tiver um namespace, o que significa que a jornada pode chegar ao serviço de Perfil do cliente em tempo real da Plataforma de dados, o fuso horário será pré-definido com o especificado no perfil do indivíduo que flui na jornada. Se o perfil do indivíduo não contiver um fuso horário, o fuso horário da instância será usado. Você pode entrar em contato com o administrador para saber o fuso horário da instância.

![](../assets/journey73.png)

O fuso horário também pode ser fixo. Limpe o fuso horário predefinido e escolha um na lista suspensa. Se você usar um fuso horário fixo, ele será o mesmo para todos os indivíduos que entram na jornada.

![](../assets/journey72.png)

Por fim, o fuso horário pode ser dinâmico para cada pessoa que entrar na etapa. Nesse caso, você usará o editor de expressões para selecionar onde deseja que o sistema obtenha essas informações (elas podem ser de um evento ou de uma fonte de dados). Consulte [](../expression/expressionadvanced.md).


As datas de início e de fim de uma viagem não podem estar ligadas a um fuso horário específico. Eles são associados automaticamente ao fuso horário da instância.
