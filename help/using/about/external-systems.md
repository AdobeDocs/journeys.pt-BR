---
product: adobe campaign
solution: Journey Orchestration
title: Integração com sistemas externos
description: Conheça as práticas recomendadas ao integrar sistemas externos
feature: Jornadas
role: Business Practitioner
level: Beginner
exl-id: 27859689-dc61-4f7a-b942-431cdf244455
source-git-commit: 5d2e82c10dd22b5b4bac15a78a2f6f592aedd371
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 1%

---

# Integração com sistemas externos {#external-systems}

Esta página apresenta as diferentes medidas de proteção fornecidas pelo Journey Orchestration ao integrar um sistema externo, bem como as práticas recomendadas: como otimizar a proteção do sistema externo usando a API de limitação, como configurar o tempo limite da jornada e como as tentativas funcionam.

O Journey Orchestration permite configurar conexões com sistemas externos por meio de fontes de dados personalizadas e ações personalizadas. Isso permite, por exemplo, enriquecer suas jornadas com dados provenientes de um sistema de reservas externo ou enviar mensagens usando um sistema de terceiros, como Epsilon ou Facebook.

Ao integrar um sistema externo, você pode encontrar vários problemas, o sistema pode estar lento, pode parar de responder ou pode não ser capaz de lidar com um grande volume. O Journey Orchestration oferece várias medidas de proteção para proteger seu sistema contra sobrecarga.

Todos os sistemas externos são diferentes em termos de desempenho. Você precisa adaptar a configuração aos seus casos de uso.

Quando o Journey Orchestration executa uma chamada para uma API externa, as grades de proteção técnica são executadas da seguinte maneira:

1. As regras de limitação são aplicadas: se a taxa máxima for atingida, as chamadas restantes serão descartadas.

2. Tempo limite e tentativa: se a regra de limitação for cumprida, o Journey Orchestration tenta executar a chamada até que o fim do tempo limite seja atingido.

## Limitação{#capping}

A API de limitação integrada oferece uma garantia técnica de upstream que ajuda a proteger seu sistema externo. Anteriormente, é necessário avaliar a capacidade da API externa. Por exemplo, se o Journey Orchestration enviar 1000 chamadas por segundo e o sistema suportar apenas 100 chamadas por segundo, é necessário definir uma regra de limitação para que o sistema não fique saturado.

As regras de limitação são definidas no nível da sandbox para um endpoint específico (o URL chamado). No tempo de execução, o Journey Orchestration verifica se há uma regra de limitação definida e aplica a taxa definida durante as chamadas para esse terminal. Se o número de chamadas exceder a taxa definida, as chamadas restantes serão descartadas e serão contadas como erros no relatório.

Uma regra de limitação é específica de um ponto de extremidade, mas global para todas as jornadas de uma sandbox. Isso significa que os slots de limitação são compartilhados entre todas as jornadas de uma sandbox.

Por exemplo, digamos que você tenha definido uma regra de limite de 100 chamadas por segundo para seu sistema externo. Seu sistema é chamado por uma ação personalizada em 10 jornadas diferentes. Se uma jornada receber 200 chamadas por segundo, ela usará os 100 slots disponíveis e descartará os 100 slots restantes. Como a taxa máxima foi excedida, as outras 9 jornadas não terão mais nenhum slot. Essa granularidade ajuda a proteger o sistema externo contra sobrecarga e falha.

Para saber mais sobre a API de limitação e como configurar regras de limitação, consulte [esta página](../api/capping.md).

## Tempo limite e tentativas{#timeout}

Se a regra de limitação for cumprida, a regra de tempo limite será aplicada.

Em cada jornada, é possível definir uma duração de tempo limite. Isso permite definir uma duração máxima ao chamar um sistema externo. A duração do tempo limite é configurada nas propriedades de uma jornada. Consulte [esta página](../building-journeys/changing-properties.md#timeout_and_error).

Esse tempo limite é global para todas as chamadas externas (chamadas de API externas em ações personalizadas e fontes de dados personalizadas). Por padrão, é definido como 5 segundos.

Durante o tempo limite definido, o Journey Orchestration tenta chamar o sistema externo. Após a primeira chamada, um máximo de três tentativas pode ser executado até que o fim do tempo limite seja atingido. Não é possível alterar o número de tentativas.

Cada tentativa usa um slot. Se você tiver um limite de 100 chamadas por segundo e cada uma delas exigir duas tentativas, a taxa cairá para 30 chamadas por segundo (cada chamada usa 3 slots: a primeira chamada e duas tentativas).

O valor da duração do tempo limite depende do caso de uso. Se desejar enviar a mensagem rapidamente, por exemplo, quando o cliente entra na loja, você não quer definir um tempo limite longo. Além disso, quanto mais tempo limite for definido, mais itens serão colocados na fila. Isso pode afetar muito o desempenho. Se o Journey Orchestration executar 1000 chamadas por segundo, manter 5 ou 15 segundos de dados pode dominar rapidamente o sistema.

Vamos tomar um exemplo por um tempo limite de 5 segundos.

* A primeira chamada dura menos de 5 segundos: se a chamada for bem-sucedida, nenhuma tentativa será executada.
* A primeira chamada dura mais de 5 segundos: a chamada é cancelada e não há nova tentativa. Ele é contado como um erro de tempo limite no relatório.
* A primeira chamada falha após 2 segundos (o sistema externo retorna um erro): Restam 3 segundos para tentativas, se os slots de limitação estiverem disponíveis.
   * Se uma das três tentativas for bem-sucedida antes do final dos 5 segundos, a chamada será executada e não haverá erro.
   * Se o fim da duração do tempo limite for atingido durante as tentativas, a chamada será cancelada e contada como um erro de tempo limite no relatório.

## Perguntas frequentes{#faq}

**Como posso configurar uma regra de limitação? Existe uma regra de limitação padrão?**

Por padrão, não há regra de limitação. As regras de limitação são definidas no nível da sandbox para um endpoint específico (o URL chamado), usando a API de limitação. Consulte [esta seção](../about/external-systems.md#capping) e [esta página](../api/capping.md).

**Quantas tentativas são executadas? Posso alterar o número de tentativas ou definir um período de espera mínimo entre tentativas?**

Para uma chamada específica, é possível executar no máximo três tentativas após a primeira chamada, até que o tempo limite seja atingido. Não é possível alterar o número de tentativas e o tempo entre cada nova tentativa. Consulte [esta seção](../about/external-systems.md#timeout).

**Onde posso configurar o tempo limite? Existe um valor máximo?**

Em cada jornada, é possível definir uma duração de tempo limite. A duração do tempo limite é configurada nas propriedades de uma jornada. A duração do tempo limite deve estar entre 1 segundo e 30 segundos. Consulte [esta seção](../about/external-systems.md#timeout) e [esta página](../building-journeys/changing-properties.md#timeout_and_error).