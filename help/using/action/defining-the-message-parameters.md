---
product: adobe campaign
title: Definir os parâmetros da mensagem
description: Saiba como definir os parâmetros da mensagem
feature: Jornadas
role: Business Practitioner
level: Intermediate
exl-id: ea9cdb1d-dde6-4080-8f35-7f8cd3cf3644
source-git-commit: 1251eafcfe7487c3df01b412f17706f5ed6c6836
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 4%

---

# Definir os parâmetros da mensagem {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

Na seção **[!UICONTROL Message parameters]**, cole um exemplo da carga JSON para enviar ao serviço externo.

![](../assets/customactionpayloadmessage.png)

>[!NOTE]
>
>Os nomes de campo no payload não podem conter um &quot;.&quot; caractere.

Você poderá definir o tipo de parâmetro (por exemplo: string, número inteiro, etc.).

Você também terá uma escolha entre especificar se um parâmetro é uma constante ou variável:

* Constante significa que o valor do parâmetro é definido no painel de configuração da ação por uma pessoa técnica. O valor será sempre o mesmo em jornadas. Ele não variará e o profissional de marketing não a verá ao usar a ação personalizada na jornada. Pode ser, por exemplo, uma ID que o sistema de terceiros espera. Nesse caso, o campo à direita da constante/variável de alternância é o valor transmitido.
* Variável significa que o valor do parâmetro varia. O profissional de marketing que usa essa ação personalizada em uma jornada poderá transmitir o valor desejado ou especificar onde recuperar o valor desse parâmetro (por exemplo, do evento, da Adobe Experience Platform etc.). Nesse caso, o campo à direita da constante/variável de alternância é o rótulo que o profissional de marketing verá na jornada para nomear esse parâmetro.

![](../assets/customactionpayloadmessage2.png)
