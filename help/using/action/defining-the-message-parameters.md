---
product: adobe campaign
title: Definição dos parâmetros de ação
description: Saiba como definir os parâmetros de ação
feature: Journeys
role: User
level: Intermediate
exl-id: ea9cdb1d-dde6-4080-8f35-7f8cd3cf3644
source-git-commit: 7ce4ddec60f62662d67351b8ca70d7763e76b977
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 3%

---

# Definição dos parâmetros de ação {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

Na seção **[!UICONTROL Action parameters]**, cole um exemplo da carga JSON para enviar ao serviço externo.

![](../assets/customactionpayloadmessage.png)

>[!NOTE]
>
>Os nomes de campos na carga não podem conter &quot;.&quot; caractere. Eles não podem começar com um caractere &quot;$&quot;.

Você poderá definir o tipo de parâmetro (por exemplo: sequência, número inteiro etc.).

Você também terá uma escolha entre especificar se um parâmetro é uma constante ou uma variável:

* Constante significa que o valor do parâmetro é definido no painel de configuração da ação por um usuário técnico. O valor será sempre o mesmo nas jornadas. Ela não varia e o profissional de marketing não a verá ao usar a ação personalizada na jornada. Pode ser, por exemplo, uma ID que o sistema de terceiros espera. Nesse caso, o campo à direita da constante/variável de alternância é o valor transmitido.
* Variável significa que o valor do parâmetro varia. O profissional de marketing que usa essa ação personalizada em uma jornada poderá passar o valor desejado ou especificar onde recuperar o valor desse parâmetro (por exemplo, do evento, da Adobe Experience Platform etc.). Nesse caso, o campo à direita da constante/variável de alternância é o rótulo que o profissional de marketing verá na jornada para nomear esse parâmetro.

![](../assets/customactionpayloadmessage2.png)
