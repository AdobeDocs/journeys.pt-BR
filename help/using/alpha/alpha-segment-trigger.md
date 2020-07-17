---
title: atividade do acionador do segmento
description: Saiba mais sobre o xxxx
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 0%

---


# atividade do acionador do segmento {#segment-trigger-activity}

## Sobre a atividade do acionador de segmento {#about-segment-trigger-actvitiy}

A atividade do Acionador de segmento permite que todos os indivíduos que pertencem a um segmento de Adobe Experience Platform entrem em uma jornada. A entrada numa viagem pode ser efetuada uma vez ou numa base regular.

Digamos que você tenha um segmento de cliente Gold no Adobe Experience Platform. Com a atividade do Acionador de segmento, é possível fazer com que todos os indivíduos pertencentes ao segmento do cliente Gold entrem em uma jornada e façam com que eles fluam em jornadas individualizadas que aproveitarão todas as funcionalidades de viagem: condições, temporizadores, eventos, ações.

>[!NOTE]
>
>Devido às latências de exportação de segmento, não é possível acionar uma jornada baseada em segmento em um período de tempo mais curto que uma hora.

## Configuring the activity {#configuring-segment-trigger-activity}

1. Desdobre a **[!UICONTROL Orchestration]** categoria e solte uma **[!UICONTROL Segment Trigger]** atividade na tela.

   A atividade deve ser posicionada como o primeiro passo de uma viagem.

1. Configure the activity **[!UICONTROL Scheduler type]**.

   Por padrão, o segmento entra na jornada **[!UICONTROL As soon as possible]**, o que significa 1 hora após a publicação da jornada. Se desejar que o segmento entre na jornada em uma data/hora específica ou de forma recorrente, selecione a opção desejada na lista.

   No caso de viagens recorrentes, você também pode definir o start e o final da jornada.

   ![](../assets/segment-trigger-schedule.png)

1. No **[!UICONTROL Segment]** campo, escolha o segmento Adobe Experience Platform que irá entrar na jornada e clique em **[!UICONTROL Save]**.

   ![](../assets/segment-trigger-segment-selection.png)

1. No **[!UICONTROL Namespace]** campo, escolha a namespace a ser usada para identificar os indivíduos. For more on namespaces, refer to [this section](../event/selecting-the-namespace.md).

   >[!NOTE]
   >
   >Os indivíduos que pertencem a um segmento que não tem a identidade (namespace) selecionada entre suas diferentes identidades não podem entrar na jornada.

1. Clique em **[!UICONTROL Ok]** para confirmar. Você pode então aproveitar as atividades disponíveis para construir sua jornada.

1. Quando a viagem estiver pronta, você poderá testá-la (consulte [Testando a jornada](../building-journeys/testing-the-journey.md)).

   Quando o modo de teste é ativado em uma jornada que começa com uma **[!UICONTROL Segment Trigger]** atividade, 100 perfis de teste serão selecionados aleatoriamente entre os perfis qualificados para o segmento selecionado. Os registros de teste permitirão que você veja o caminho dos indivíduos na jornada e os possíveis erros encontrados (consulte [Visualização dos registros](../building-journeys/testing-the-journey.md#viewing_logs)).

   >[!NOTE]
   >
   >Observe que você não poderá ver as 100 pessoas após a viagem usando o recurso de fluxo visual existente em viagens unitárias.

1. Em seguida, você pode publicar sua jornada (consulte [Publicação da jornada](../building-journeys/publishing-the-journey.md)). Os indivíduos que pertencem ao segmento inserirão a jornada na data/hora especificada no scheduler de atividade do Acionador de segmentos.

   >[!IMPORTANT]
   >
   >Lembre-se de que os segmentos de Adobe Experience Platform são calculados uma vez por dia (segmentos de **lote** ) ou em tempo real (segmentos **transmitidos** ).
   >
   >Se o segmento selecionado for transmitido em tempo real, os indivíduos que pertencem a esse segmento poderão entrar na jornada em tempo real. Se o segmento for lote, as pessoas recém-qualificadas para esse segmento potencialmente entrarão na jornada quando o cálculo do segmento for executado no Adobe Experience Platform.
