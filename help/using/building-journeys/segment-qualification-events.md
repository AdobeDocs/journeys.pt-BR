---
product: adobe campaign
solution: Journey Orchestration
title: Eventos de qualificação de segmento
description: Saiba mais sobre eventos de qualificação de segmento
translation-type: tm+mt
source-git-commit: 6ebedad2cb8e78b4dd953bc7a2993cebbeefabcc
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 1%

---


# Eventos de qualificação de segmento {#segment-qualification}

## Sobre eventos de qualificação de segmento{#about-segment-qualification}

Esta atividade permite que sua jornada escute as entradas e saídas dos perfis nos segmentos do Adobe Experience Platform, para que os indivíduos entrem ou avancem em uma jornada. Para obter mais informações sobre a criação de segmentos, consulte esta [seção](../segment/about-segments.md).

Digamos que você tenha um segmento de &quot;cliente prateado&quot;. Com essa atividade, todos os novos clientes de prata entram em uma jornada e enviam uma série de mensagens personalizadas.

Esse tipo de evento pode ser posicionado como o primeiro passo ou mais tarde na jornada.

>[!IMPORTANT]
>
>Lembre-se de que os segmentos do Adobe Experience Platform são calculados uma vez por dia (**segmentos de lote**) ou em tempo real (**segmentos transmitidos**, usando a opção Audiências de alta frequência do Adobe Experience Platform).
>
>Se o segmento selecionado for transmitido, os indivíduos que pertencem a esse segmento potencialmente entrarão na jornada em tempo real. Se o segmento for lote, as pessoas recém-qualificadas para esse segmento potencialmente entrarão na jornada quando o cálculo do segmento for executado no Adobe Experience Platform.


1. Desdobre a categoria **[!UICONTROL Events]** e solte uma atividade **[!UICONTROL Segment qualification]** na sua tela.

   ![](../assets/segment5.png)

1. Adicione um **[!UICONTROL Label]** à atividade. Esta etapa é opcional.

1. Clique no campo **[!UICONTROL Segment]** e selecione os segmentos que deseja aproveitar.

   >[!NOTE]
   >
   >Observe que você pode personalizar as colunas exibidas na lista e classificá-las.

   ![](../assets/segment6.png)

   Depois que o segmento é adicionado, o botão **[!UICONTROL Copy]** permite que você copie seu nome e ID:

   `{"name":"Loyalty membership“,”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](../assets/segment-copy.png)

1. No campo **[!UICONTROL Behavior]**, escolha se você deseja escutar as entradas do segmento, as saídas ou ambos.

1. Selecione uma namespace. Isso só é necessário se o evento for posicionado como o primeiro passo da jornada.

   ![](../assets/segment7.png)

A carga contém as seguintes informações de contexto, que podem ser usadas em condições e ações:

* o comportamento (entrada, saída)
* o carimbo de data e hora da qualificação
* a ID do segmento

Ao usar o editor de expressão em uma condição ou ação que segue uma atividade **[!UICONTROL Segment qualification]**, você tem acesso ao nó **[!UICONTROL SegmentQualification]**. Você pode escolher entre **[!UICONTROL Last qualification time]** e **[!UICONTROL status]** (entrar ou sair).

Consulte [atividade de condição](../building-journeys/condition-activity.md#about_condition).

![](../assets/segment8.png)

## Práticas recomendadas {#best-practices-segments}

A atividade **[!UICONTROL Segment Qualification]** permite a entrada imediata em viagens de indivíduos qualificados ou desqualificados de um segmento Adobe Experience Platform.

A velocidade de recepção desta informação é elevada. As medições efetuadas mostram uma velocidade de 10 000 eventos recebidos por segundo. Como resultado, você deve se certificar de entender como os picos de entrada podem acontecer, como evitá-los e como fazer sua jornada pronta para eles.

### Segmentos em lote{#batch-speed-segment-qualification}

Ao usar a qualificação de segmento para um segmento de lote, observe que um pico de entrada acontecerá no momento do cálculo diário. O tamanho do pico dependerá do número de indivíduos que entram (ou saem) no segmento diariamente.

Além disso, se o segmento do lote for recém-criado e imediatamente utilizado numa viagem, o primeiro lote de cálculo poderá fazer com que um número muito grande de indivíduos entre na viagem.

### Segmentos transmitidos{#streamed-speed-segment-qualification}

Ao usar a qualificação de segmento para segmentos dinamizados, há menos risco de obter grandes picos de entradas/saídas devido à avaliação contínua do segmento. Mesmo assim, se a definição do segmento levar a tornar um grande volume de clientes qualificados ao mesmo tempo, também pode haver um pico.

Para obter mais informações sobre a segmentação de streaming, consulte esta [página](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/streaming-segmentation.html#api)

### Como evitar sobrecargas{#overloads-speed-segment-qualification}

Estas são algumas práticas recomendadas que ajudarão a evitar o sobrecarregamento de sistemas aproveitados em viagens (fontes de dados, ações personalizadas, ações do Adobe Campaign Standard).

Não use, em uma atividade **[!UICONTROL Segment Qualification]**, um segmento de lote imediatamente após sua criação. Ele evitará o primeiro pico de cálculo. Observe que haverá um aviso amarelo na tela de viagem se você estiver prestes a usar um segmento que nunca foi calculado.

![](../assets/segment-error.png)

Coloque uma regra de limite para as fontes de dados e ações usadas em viagens para evitar sobrecarregá-las (consulte esta [seção](../api/capping.md)). Observe que a regra de limitação não tem nenhuma nova tentativa. Se precisar tentar novamente, você deve usar um caminho alternativo na jornada marcando a caixa **[!UICONTROL Add an alternative path in case of a timeout or an error]** em condições ou ações.

Antes de usar o segmento em uma jornada de produção, sempre avalie primeiro o volume de indivíduos qualificados para esse segmento a cada dia. Para fazer isso, você pode verificar a seção **[!UICONTROL Segments]** no Adobe Experience Platform e observar o gráfico no lado direito.

![](../assets/segment-overload.png)
