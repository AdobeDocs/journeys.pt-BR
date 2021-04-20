---
product: adobe campaign
solution: Journey Orchestration
title: Definir os parâmetros da mensagem
description: Saiba como definir os parâmetros da mensagem
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 3%

---


# Definir os parâmetros da mensagem {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

Na seção **[!UICONTROL Message parameters]**, cole um exemplo da carga JSON para enviar ao serviço externo.

![](../assets/customactionpayloadmessage.png)

Você poderá definir o tipo de parâmetro (por exemplo: string, número inteiro, etc.).

Você também terá uma escolha entre especificar se um parâmetro é uma constante ou variável:

* Constante significa que o valor do parâmetro é definido no painel de configuração da ação por uma pessoa técnica. O valor será sempre o mesmo em jornadas. Ele não variará e o profissional de marketing não a verá ao usar a ação personalizada na jornada. Pode ser, por exemplo, uma ID que o sistema de terceiros espera. Nesse caso, o campo à direita da constante/variável de alternância é o valor transmitido.
* Variável significa que o valor do parâmetro varia. O profissional de marketing que usa essa ação personalizada em uma jornada poderá transmitir o valor desejado ou especificar onde recuperar o valor desse parâmetro (por exemplo, do evento, da Adobe Experience Platform etc.). Nesse caso, o campo à direita da constante/variável de alternância é o rótulo que o profissional de marketing verá na jornada para nomear esse parâmetro.

![](../assets/customactionpayloadmessage2.png)
