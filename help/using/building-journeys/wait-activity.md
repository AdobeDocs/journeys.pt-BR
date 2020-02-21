---
title: Atividade de espera
description: Saiba mais sobre a atividade de espera
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
source-git-commit: 6274426ec04315149fb430b847498c0e20164bae

---


# Atividade de espera{#section_rlm_nft_dgb}

Se desejar aguardar antes de executar a próxima atividade no caminho, você pode usar uma **[!UICONTROL Wait]** atividade. Permite definir o momento em que a próxima atividade será executada. Quatro opções estão disponíveis:

* [Duração](#duration)
* [Data fixa](#fixed_date)
* [Personalizado](#custom)
* [Otimização do tempo de envio de email](#email_send_time_optimization)

## Sobre a atividade Espera{#about_wait}

Veja como as esperas são priorizadas quando você usa várias esperas em paralelo. Se eles tiverem a mesma configuração de tempo e uma condição diferente, mas sobreposta, a espera posicionada acima será a priorizada. Por exemplo, a condição da primeira espera é &quot;ser mulher&quot; e a condição da segunda espera em paralelo é &quot;ser um VIP&quot;. A primeira atividade de espera será priorizada

Observe também que se duas esperas diferentes estiverem em paralelo, a que ocorrer primeiro será priorizada, independentemente de sua posição vertical. Por exemplo, se uma espera de 1 hora estiver acima e uma espera de 30 minutos estiver abaixo, após 30 minutos, a espera de 30 minutos será processada.

Você pode definir uma condição se desejar restringir a espera a uma determinada população.

>[!NOTE]
>
>A duração máxima de espera é de 30 dias.
>
>No modo de teste, o tempo de **espera no parâmetro de teste** permite definir o tempo que cada atividade de espera durará. O tempo padrão é de 10 segundos. Isso garantirá que você obtenha os resultados do teste rapidamente. Consulte [](../building-journeys/testing-the-journey.md)

## Duração da espera{#duration}

Selecione a duração da espera antes da execução da próxima atividade.

![](../assets/journey55.png)

## Data de espera fixa{#fixed_date}

Selecione a data para a execução da próxima atividade. Ao definir uma data fixa, você deve especificar um fuso horário. Consulte [](../building-journeys/timezone-management.md).

![](../assets/journey56.png)

## Espera personalizada{#custom}

Essa opção permite definir uma data personalizada, por exemplo, 12 de julho de 2020 às 17 horas, usando uma expressão avançada com base em um campo proveniente de um evento ou de uma fonte de dados. Isso não permite definir uma duração personalizada, por exemplo, 7 dias. A expressão no editor de expressões deve fornecer um formato dateTimeOnly. Consulte [](../expression/expressionadvanced.md). Para obter mais informações sobre o formato dateTimeOnly, consulte [](../expression/data-types.md)

>[!NOTE]
>
>Você pode aproveitar uma expressão dateTimeOnly ou usar uma função para converter em dateTimeOnly. Por exemplo: toDateTimeOnly(@{Event.offerOpened.activity.endTime}), o campo no evento é do formulário 2016-08-12T09:46:06.
>
>O fuso **horário** é esperado em outro local no painel de configuração de espera personalizado. Como resultado, atualmente não é possível da interface para apontar diretamente para um tempo completo ISO-8601 de mistura de carimbo de data e hora e deslocamento de fuso horário como 2016-08-12T09:46:06.982-05. Consulte [](../building-journeys/timezone-management.md).

![](../assets/journey57.png)

## Otimização do tempo de envio de email{#email_send_time_optimization}

>[!CAUTION]
>
>O recurso de otimização do tempo de envio de email só está disponível para clientes que usam o recurso Adobe Campaign Standard Data Service.

Esse tipo de espera usa uma pontuação calculada na Plataforma. A pontuação calcula a propensão de clicar ou abrir um email no futuro com base no comportamento anterior. Observe que o algoritmo que calcula a pontuação precisa de uma certa quantidade de dados para funcionar. Como resultado, quando não tem dados suficientes, o tempo de espera padrão será aplicado. No momento da publicação, você será notificado de que o horário padrão se aplica.

>[!NOTE]
>
>O primeiro evento de sua jornada deve ter um namespace.
>
>Esse recurso está disponível somente após uma **[!UICONTROL Email]** atividade. Você precisa ter o Adobe Campaign Standard.

1. No **[!UICONTROL Amount of time]** campo, defina o número de horas a serem consideradas para otimizar o envio de email.
1. No **[!UICONTROL Optimization type]** campo, escolha se a otimização deve aumentar os cliques ou abrir.
1. No campo Tempo **** padrão, defina o tempo padrão para esperar se a pontuação de tempo de envio preditiva não estiver disponível.

   >[!NOTE]
   >
   >Observe que a pontuação de tempo de envio pode estar indisponível porque não há dados suficientes para executar o cálculo. Nesse caso, você será informado, no momento da publicação, que o horário padrão se aplica.

![](../assets/journey57bis.png)
