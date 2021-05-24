---
product: adobe campaign
solution: Journey Orchestration
title: Integração com sistemas externos
description: Conheça as práticas recomendadas ao integrar sistemas externos
feature: Jornadas
role: Business Practitioner
level: Beginner
exl-id: 27859689-dc61-4f7a-b942-431cdf244455
source-git-commit: a25ff95e0b74d3a0693310179670c7fe7b0de51c
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 0%

---

# Integração com sistemas externos {#external-systems}

Esta página apresenta as diferentes medidas de proteção fornecidas pelo Journey Orchestration ao integrar um sistema externo, bem como as práticas recomendadas: como otimizar a proteção do sistema externo com a API de limitação, como configurar o tempo limite da jornada e como as tentativas funcionam.

O Journey Orchestration permite configurar conexões com sistemas externos por meio de fontes de dados personalizadas e ações personalizadas. Isso permite, por exemplo, enriquecer suas jornadas com dados provenientes de um sistema de reservas externo ou enviar mensagens usando sistemas de terceiros, como Epsilon ou Facebook.

Ao integrar um sistema externo, você pode encontrar vários problemas, o sistema pode estar lento, pode parar de responder ou pode não ser capaz de lidar com um grande volume. O Journey Orchestration oferece várias medidas de proteção para proteger seu sistema contra sobrecarga.

Todos os sistemas externos são diferentes em termos de desempenho. É necessário adaptar a configuração a cada caso de uso.

Quando o Journey Orchestration executa uma chamada para uma API externa, as grades de proteção técnica são executadas da seguinte maneira:

1. Limitação: regras de limitação são aplicadas
2. Tempo limite e tentativa:

## Limitação

A API de limitação integrada oferece uma garantia técnica de upstream que ajudará a proteger seu sistema externo. Anteriormente, é necessário avaliar a capacidade da API externa. Por exemplo, se o Journey Orchestration enviar 1000 chamadas por segundo e o sistema suportar apenas 100 chamadas por segundo, é necessário definir uma regra de limitação para que o sistema não fique saturado.

As regras de limitação são definidas no nível de sanddox para um endpoint específico (URL chamado). No tempo de execução, o Journey Orchestration verifica se há uma regra de limitação definida e aplica a taxa definida durante as chamadas para esse terminal. Se o número de chamadas exceder a taxa definida, as chamadas restantes serão descartadas.

Uma regra de limitação é específica de um ponto de extremidade, mas global para todas as jornadas de uma sandbox. Isso significa que os slots de chamada são compartilhados entre todas as jornadas de uma sandbox. Por exemplo, digamos que o sistema externo tenha um limite definido de 100 chamadas por segundo e seja chamado por uma ação personalizada em 10 jornadas diferentes. Se uma jornada receber 200 chamadas por segundo, ela manterá os 100 slots disponíveis e descartará os 100 slots restantes. Como a taxa máxima já foi excedida, as outras 9 jornadas não terão nenhum slot disponível. Essa granularidade ajuda a proteger o sistema externo contra sobrecarga e falha.

Uma chamada descartada devido a limites máximos é contada como um erro no relatório.

Para saber como configurar regras de limitação, consulte [esta página](../api/timezone-management.md).

## Tempo limite e tentativas

Ensuite -> definição de tempo limite, et qui definir le temps máximo que em si mesmo um lappel au sys externe. Pendant ce temps là, em essaie de faire des appels. Em fait un appel, si l&#39;appel procedure moinre longtemps que le timeout ca marche, si plus longtemps on voit pode comme une timeout error, et coté reportando comme une erreur. si l&#39;appel echoue, (planter sur 500 ou autre), repetir. 3 tentativas máx., pas configuráveis. SI pode exceder le timeoutglobal (par exemplo 2 essais, mais depasse le timeout) erre de timeout. mais de temps que necessário. O tempo limite do tempo máximo que é em todas as tentativas do appel et aux é um erro.

