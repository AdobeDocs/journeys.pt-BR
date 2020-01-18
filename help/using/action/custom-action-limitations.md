---
title: Limitações de ação personalizada
description: Saiba mais sobre limitações de ações personalizadas
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


# Limitações de ação personalizada {#concept_lh2_df1_2gb}

Estas são algumas limitações relacionadas ao uso de ações personalizadas:

* Não há limite ou envio de buffering/suavização de volume.
* Duas tentativas são executadas sistematicamente em caso de erro. Não é possível ajustar o número de tentativas de acordo com a mensagem de erro recebida.
* O **[!UICONTROL Reaction]**evento integrado permite que você reaja a ações inovadoras (consulte[](../building-journeys/event-activities.md). Se quiser reagir a uma mensagem enviada por meio de uma ação personalizada, é necessário configurar um evento dedicado.
* O URL de ação personalizado não suporta parâmetros dinâmicos.
* Somente métodos de chamada POST e PUT são suportados.
* O nome do parâmetro de consulta ou cabeçalho não deve começar com &quot;.&quot; ou &quot;$&quot;.
* Endereços IP não são permitidos.
* Endereços internos da Adobe (.adobe.) não são permitidas.
