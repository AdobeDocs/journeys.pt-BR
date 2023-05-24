---
product: adobe campaign
title: Mudar de uma jornada para outra
description: Mudar de uma jornada para outra
feature: Journeys
role: User
level: Intermediate
exl-id: 520376aa-2cb5-46d6-8f21-3e03544f5da1
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 6%

---

# Mudar de uma jornada para outra {#jump}

A variável **[!UICONTROL Jump]** A atividade de ação permite enviar indivíduos de uma jornada para outra. Esse recurso permite:

* simplificar o design de jornadas muito complexas dividindo-as em várias jornadas
* criar jornadas com base em padrões de jornada comuns e reutilizáveis

Na jornada de origem, basta adicionar um **[!UICONTROL Jump]** e selecione uma jornada de público alvo. Quando o indivíduo entra na **[!UICONTROL Jump]** etapa, um evento interno é enviado para o primeiro evento da jornada do target. Se a variável **[!UICONTROL Jump]** for bem-sucedida, o indivíduo continuará a progredir na jornada. O comportamento é semelhante a outras ações.

Na jornada do target, o primeiro evento acionado internamente pelo **[!UICONTROL Jump]** A atividade fará o fluxo individual na jornada.

>[!NOTE]
>
>Consulte também o vídeo tutorial [aqui](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/building-a-journey/jumping-to-another-journey.html?lang=pt-BR)

## Vida útil

Digamos que você tenha adicionado um **[!UICONTROL Jump]** atividade em uma jornada A para uma jornada B. A Jornada A é a **jornada de origem** e na jornada B, a variável **jornada do público alvo**.
Estas são as diferentes etapas do processo de execução:

**JORNADA A** é acionado a partir de um evento externo:

1. A jornada A recebe um evento externo relacionado a um indivíduo.
1. O indivíduo alcança a **[!UICONTROL Jump]** etapa.
1. O indivíduo é encaminhado para a Jornada B e avança para as próximas etapas da Jornada A, após o **[!UICONTROL Jump]** etapa.

Na jornada B, o primeiro evento é acionado internamente, por meio do **[!UICONTROL Jump]** atividade da jornada A:

1. A jornada B recebeu um evento interno da Jornada A.
1. O indivíduo começa a fluir na Jornada B.

>[!NOTE]
>
>A jornada B também pode ser acionada por meio de um evento externo.

## Práticas recomendadas e limitações

### Criação

* A variável **[!UICONTROL Jump]** A atividade só está disponível em jornadas que usam namespace.
* Você só pode pular para uma jornada que use o mesmo namespace que a jornada de origem.
* Não é possível pular para uma jornada que começa com um **Qualificação do segmento** evento.
* Você não pode ter um **[!UICONTROL Jump]** atividade e um **Qualificação do segmento** evento na mesma jornada.
* Você pode incluir quantos **[!UICONTROL Jump]** conforme necessário em uma jornada. Depois de um **[!UICONTROL Jump]**, você pode adicionar qualquer atividade necessária.
* Você pode ter quantos níveis de salto forem necessários. Por exemplo, a Jornada A salta para a jornada B, que salta para a jornada C e assim por diante.
* A jornada do target também pode incluir quantos **[!UICONTROL Jump]** conforme necessário.
* Não há suporte para padrões de loop. Não há como vincular duas ou mais jornadas, o que criaria um loop infinito. A variável **[!UICONTROL Jump]** a tela de configuração de atividade impede que você faça isso.

### Execução

* Quando a variável **[!UICONTROL Jump]** for executada, a versão mais recente da jornada de destino será acionada.
* Como de costume, um indivíduo único só pode estar presente uma vez na mesma jornada. Como resultado, se o indivíduo enviado da jornada de origem já estiver na jornada de destino, ele não entrará na jornada de destino. Nenhum erro será relatado no **[!UICONTROL Jump]** atividade porque esse é um comportamento normal.

## Configuração da atividade Jump

1. Projete seu **jornada de origem**.

   ![](../assets/jump1.png)

1. Em qualquer etapa da jornada, adicione um **[!UICONTROL Jump]** atividade, a partir do **[!UICONTROL ACTIONS]** categoria. Adicione um rótulo e uma descrição.

   ![](../assets/jump2.png)

1. Clique dentro do **Jornada do Target** campo.
A lista exibe todas as versões do jornada que são modo de rascunho, ativo ou de teste. Jornadas que usam um namespace diferente ou que começam com um **Qualificação do segmento** evento não estão disponíveis. As jornadas do Target que criariam um padrão de loop também são filtradas.

   ![](../assets/jump3.png)

   >[!NOTE]
   >
   >Você pode clicar no link **Abrir jornada do público alvo** no lado direito, para abrir a jornada do target em uma nova guia.

1. Selecione a jornada de destino para a qual deseja ir.
A variável **Primeiro evento** é preenchido previamente com o nome do primeiro evento da jornada do target. Se sua jornada do target incluir vários eventos, a variável **[!UICONTROL Jump]** só é permitido no primeiro evento.

   ![](../assets/jump4.png)

1. A variável **Parâmetros de ação** exibe todos os campos do evento de destino. Da mesma forma que para outros tipos de ações, mapeie cada campo com campos do evento de origem ou da fonte de dados. Essas informações serão passadas para a jornada de destino no tempo de execução.
1. Adicione as próximas atividades para concluir a jornada de origem.

   ![](../assets/jump5.png)


   >[!NOTE]
   >
   >A identidade do indivíduo é mapeada automaticamente. Essas informações não estão visíveis na interface.

Seu **[!UICONTROL Jump]** atividade está configurada. Assim que a jornada estiver ativa ou em modo de teste, os indivíduos que atingem o estado **[!UICONTROL Jump]** a etapa será enviada do para a jornada de destino.

Quando um **[!UICONTROL Jump]** atividade estiver configurada em uma jornada, um **[!UICONTROL Jump]** O ícone de entrada é adicionado automaticamente no início da jornada de destino. Isso ajuda a identificar se a jornada pode ser acionada externamente, mas também internamente, a partir de uma **[!UICONTROL Jump]** atividade.

![](../assets/jump7.png)

## Solução de problemas

Quando a jornada for publicada ou estiver em modo de teste, ocorrerão erros se:
* a jornada de destino não existe mais
* a jornada de destino é rascunho, fechada ou interrompida
* se o primeiro evento da jornada de destino tiver sido alterado e o mapeamento for interrompido

![](../assets/jump6.png)
