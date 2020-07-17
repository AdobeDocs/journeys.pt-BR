---
title: Definir os parâmetros da mensagem
description: Saiba como definir os parâmetros da mensagem
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
source-wordcount: '214'
ht-degree: 3%

---


# Definir os parâmetros da mensagem {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

Na **[!UICONTROL Message parameters]** seção, cole um exemplo da carga JSON para enviar ao serviço externo.


![](../assets/customactionpayloadmessage.png)

Você poderá definir se o tipo de parâmetro é correto (por exemplo: string, integer etc.).

Você também terá uma opção entre especificar que um parâmetro é uma constante ou uma variável:

* Constante significa que o valor do parâmetro é definido no painel de configuração da ação por uma pessoa técnica. O valor será sempre o mesmo entre as viagens. Ele não variará e o profissional de marketing não o verá ao usar a ação personalizada na jornada. Por exemplo, pode ser uma ID que o sistema de terceiros espera. Nesse caso, o campo à direita da variável/constante de alternância é o valor transmitido.
* Variável significa que o valor do parâmetro variará. O comerciante que usa essa ação personalizada em uma jornada será livre para passar o valor que ele deseja ou para especificar onde recuperar o valor desse parâmetro (por exemplo, do evento, do Adobe Experience Platform etc.). Nesse caso, o campo à direita da variável/constante de alternância é o rótulo que o comerciante verá na jornada para nomear esse parâmetro.
