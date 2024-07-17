---
product: adobe campaign
title: Eventos de qualificação de segmento
description: Saiba mais sobre eventos de qualificação de segmento
feature: Journeys
role: User
level: Intermediate
exl-id: e8e54dbd-8178-4c70-907c-68eb4dc54da7
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 1%

---

# Eventos de qualificação de segmento {#segment-qualification}

## Sobre eventos de qualificação de segmento{#about-segment-qualification}

Essa atividade permite que sua jornada acompanhe as entradas e saídas dos perfis nos segmentos do Adobe Experience Platform para que os indivíduos entrem ou avancem em uma jornada. Para obter mais informações sobre a criação de segmentos, consulte esta [seção](../segment/about-segments.md).

Digamos que você tenha um segmento de &quot;cliente prata&quot;. Com essa atividade, você pode fazer com que todos os novos clientes Silver insiram uma jornada e enviem a eles uma série de mensagens personalizadas.

Esse tipo de evento pode ser posicionado como a primeira etapa ou posteriormente na jornada.

>[!IMPORTANT]
>
>Lembre-se de que os segmentos do Adobe Experience Platform são calculados uma vez por dia (**batch** segmentos) ou em tempo real (**streaming** segmentos, usando a opção Públicos-alvo de alta frequência do Adobe Experience Platform).
>
>Se o segmento selecionado for transmitido, os indivíduos pertencentes a esse segmento potencialmente entrarão na jornada em tempo real. Se o segmento for em lote, as pessoas recém-qualificadas para esse segmento potencialmente inserirão a jornada quando o cálculo do segmento for executado no Adobe Experience Platform.


1. Expanda a categoria **[!UICONTROL Events]** e solte uma atividade **[!UICONTROL Segment qualification]** na tela.

   ![](../assets/segment5.png)

1. Adicione um **[!UICONTROL Label]** à atividade. Esta etapa é opcional.

1. Clique no campo **[!UICONTROL Segment]** e selecione os segmentos que deseja aproveitar.

   >[!NOTE]
   >
   >Observe que é possível personalizar as colunas exibidas na lista e classificá-las.

   ![](../assets/segment6.png)

   Depois que o segmento é adicionado, o botão **[!UICONTROL Copy]** permite copiar seu nome e ID:

   `{"name":"Loyalty membership“,”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](../assets/segment-copy.png)

1. No campo **[!UICONTROL Behaviour]**, escolha se deseja escutar entradas de segmento, saídas ou ambas.

   >[!NOTE]
   >
   >Observe que **[!UICONTROL Enter]** e **[!UICONTROL Exit]** correspondem aos status de participação de segmento **Realizado** e **Encerrado** da Adobe Experience Platform. Para obter mais informações sobre como avaliar um segmento, consulte a [documentação do Serviço de segmentação](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

1. Selecione um namespace. Isso só será necessário se o evento for posicionado como a primeira etapa da jornada.

   ![](../assets/segment7.png)

A carga contém as seguintes informações de contexto, que podem ser usadas em condições e ações:

* o comportamento (entrada, saída)
* o carimbo de data e hora da qualificação
* a id do segmento

Ao usar o editor de expressão em uma condição ou ação que segue uma atividade **[!UICONTROL Segment qualification]**, você tem acesso ao nó **[!UICONTROL SegmentQualification]**. Você pode escolher entre **[!UICONTROL Last qualification time]** e **[!UICONTROL status]** (entrar ou sair).

Consulte [Atividade de condição](../building-journeys/condition-activity.md#about_condition).

![](../assets/segment8.png)

Uma nova jornada que inclui um evento de qualificação de segmento fica operacional dez minutos após a sua publicação. Esse intervalo corresponde ao intervalo de atualização do cache do serviço dedicado. Portanto, é necessário aguardar dez minutos antes de usar essa jornada.

## Práticas recomendadas {#best-practices-segments}

A atividade **[!UICONTROL Segment Qualification]** permite a entrada imediata em jornadas de indivíduos que estão sendo qualificados ou desqualificados de um segmento do Adobe Experience Platform.

A velocidade de recepção dessas informações é alta. As medições efetuadas mostram uma velocidade de 10 000 eventos recebidos por segundos. Como resultado, você deve entender como os picos de entrada podem acontecer, como evitá-los e como preparar sua jornada para eles.

### Segmentos em lote{#batch-speed-segment-qualification}

Ao usar a qualificação de segmento para um segmento em lote, observe que um pico de entrada ocorrerá no momento do cálculo diário. O tamanho do pico dependerá do número de indivíduos entrando (ou saindo) do segmento diariamente.

Além disso, se o segmento em lote for recém-criado e usado imediatamente em uma jornada, o primeiro lote de cálculo pode fazer com que um número muito grande de indivíduos entre na jornada.

### Segmentos transmitidos{#streamed-speed-segment-qualification}

Ao usar a qualificação de segmento para segmentos transmitidos, há menos risco de obter grandes picos de entradas/saídas devido à avaliação contínua do segmento. Ainda assim, se a definição do segmento levar a fazer com que um grande volume de clientes se qualifiquem ao mesmo tempo, também poderá haver um pico.

Para obter mais informações sobre segmentação por transmissão, consulte esta [página](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/streaming-segmentation.html#api)

### Como evitar sobrecargas{#overloads-speed-segment-qualification}

Estas são algumas das práticas recomendadas que ajudarão a evitar sobrecarga dos sistemas aproveitados no jornada (fontes de dados, ações personalizadas, ações do Adobe Campaign Standard).

Não use, em uma atividade **[!UICONTROL Segment Qualification]**, um segmento em lote imediatamente após a sua criação. Evitará o primeiro pico de cálculo. Observe que haverá um aviso amarelo na tela de jornada se você estiver prestes a usar um segmento que nunca foi calculado.

![](../assets/segment-error.png)

Coloque uma regra de limitação para fontes de dados e ações usadas no jornada para evitar sobrecarga (consulte esta [seção](../api/capping.md)). Observe que a regra de limitação não tem repetição. Se você precisar tentar novamente, deverá usar um caminho alternativo na jornada marcando a caixa **[!UICONTROL Add an alternative path in case of a timeout or an error]** em condições ou ações.

Antes de usar o segmento em uma jornada de produção, sempre avalie primeiro o volume de indivíduos qualificados para esse segmento todos os dias. Para fazer isso, verifique a seção **[!UICONTROL Segments]** no Adobe Experience Platform e veja o gráfico no lado direito.

![](../assets/segment-overload.png)
