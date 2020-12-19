---
product: adobe campaign
solution: Journey Orchestration
title: Definir os parâmetros da mensagem
description: Saiba como definir os parâmetros da mensagem
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 3%

---


# Definir os parâmetros da mensagem {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

Na seção **[!UICONTROL Message parameters]**, cole um exemplo da carga JSON para enviar ao serviço externo.

![](../assets/customactionpayloadmessage.png)

Você poderá definir o tipo de parâmetro (por exemplo: string, integer etc.).

Você também terá uma opção entre especificar se um parâmetro é uma constante ou uma variável:

* Constante significa que o valor do parâmetro é definido no painel de configuração da ação por uma pessoa técnica. O valor será sempre o mesmo entre as viagens. Ele não variará e o profissional de marketing não o verá ao usar a ação personalizada na jornada. Por exemplo, pode ser uma ID que o sistema de terceiros espera. Nesse caso, o campo à direita da variável/constante de alternância é o valor transmitido.
* Variável significa que o valor do parâmetro variará. O comerciante que usa essa ação personalizada em uma jornada será livre para passar o valor que ele deseja ou para especificar onde recuperar o valor desse parâmetro (por exemplo, do evento, da Adobe Experience Platform etc.). Nesse caso, o campo à direita da variável/constante de alternância é o rótulo que o comerciante verá na jornada para nomear esse parâmetro.

![](../assets/customactionpayloadmessage2.png)
