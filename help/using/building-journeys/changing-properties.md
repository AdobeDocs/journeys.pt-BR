---
title: Alterar propriedades
description: Saiba mais sobre como alterar propriedades
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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---



# Alterar propriedades {#concept_prq_wqt_52b}

Clique no ícone de lápis, na parte superior direita, para acessar as propriedades da jornada.

Você pode alterar o nome da jornada, adicionar uma descrição, permitir a reentrada, escolher datas de início e término e definir uma **[!UICONTROL Timeout and error]**duração se você for administrador.

![](../assets/journey32.png)

## Entrada{#entrance}

Por padrão, novas viagens permitem a reentrada. Você pode desmarcar a opção para viagens de &quot;uma foto&quot;, por exemplo, se quiser oferecer um presente único quando uma pessoa entrar em uma loja. Nesse caso, você não quer que o cliente possa entrar novamente na viagem e receber a oferta novamente.

Quando uma viagem &quot;termina&quot;, ela terá status **[!UICONTROL Finished]**. A viagem deixará de deixar novos indivíduos entrarem na viagem. As pessoas que já se encontram na viagem terminarão a viagem normalmente.

## Tempo limite e erro nas atividades de viagem {#timeout_and_error}

Ao editar uma ação ou atividade de condição, você pode definir um caminho alternativo em caso de erro ou tempo limite. Se o processamento da atividade que interroga um sistema de terceiros exceder a duração do tempo limite definida nas propriedades da viagem (**[!UICONTROL Timeout and  error]**campo), o segundo caminho será escolhido para executar uma potencial ação de fallback.

Os valores autorizados estão entre 1 e 30 segundos.

Recomendamos que você defina um **[!UICONTROL Timeout and error]**valor muito curto se sua jornada for sensível ao tempo (por exemplo: reação ao local em tempo real de uma pessoa) porque não é possível atrasar a ação por mais de alguns segundos. Se sua jornada for menos sensível ao tempo, você poderá usar um valor maior para dar mais tempo ao sistema chamado para enviar uma resposta válida.

A Journey Orchestration também utiliza um tempo limite global. Consulte a [próxima seção](#global_timeout).

## Tempo limite de jornada global {#global_timeout}

Além do [tempo limite](#timeout_and_error) utilizado nas atividades de viagem, existe também um tempo limite de viagem global que não é apresentado na interface e não pode ser alterado. Este tempo limite interromperá o progresso dos indivíduos na viagem 30 dias após a sua entrada. Isto significa que a viagem de um indivíduo não pode durar mais de 30 dias. Após o período de tempo limite de 30 dias, os dados do indivíduo são excluídos. As pessoas que continuam a fluir na viagem no final do período de tempo limite serão interrompidas e serão tidas em conta como erros na comunicação.

>[!NOTE]
>
>O Journey Orchestration não reage diretamente às solicitações de cancelamento, acesso ou exclusão da privacidade. No entanto, o tempo limite global garante que os indivíduos nunca permaneçam mais de 30 dias em qualquer jornada.

Devido ao tempo limite de 30 dias de viagem, quando a reentrada da viagem não é permitida, não podemos garantir que o bloqueio de reentrada funcione mais de 30 dias. Com efeito, à medida que retiramos todas as informações sobre as pessoas que entraram na viagem 30 dias após a sua entrada, não podemos conhecer a pessoa que entrou anteriormente, há mais de 30 dias.
