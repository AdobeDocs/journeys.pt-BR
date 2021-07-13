---
product: adobe campaign
title: Mudar de uma jornada para outra
description: Mudar de uma jornada para outra
feature: Jornadas
role: User
level: Intermediate
exl-id: 520376aa-2cb5-46d6-8f21-3e03544f5da1
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 4%

---

# Mudar de uma jornada para outra {#jump}

A atividade de ação **[!UICONTROL Jump]** permite encaminhar indivíduos de uma jornada para outra. Esse recurso permite:

* simplificar o design de jornadas muito complexas dividindo-as em várias
* criar jornadas com base em padrões de jornada comuns e reutilizáveis

Na jornada de origem, basta adicionar uma atividade **[!UICONTROL Jump]** e selecionar uma jornada de destino. Quando o indivíduo insere a etapa **[!UICONTROL Jump]** , um evento interno é enviado para o primeiro evento da jornada de destino. Se a ação **[!UICONTROL Jump]** for bem-sucedida, o indivíduo continuará a progredir na jornada. O comportamento é semelhante a outras ações.

Na jornada do target, o primeiro evento acionado internamente pela atividade **[!UICONTROL Jump]** fará o fluxo individual na jornada.

>[!NOTE]
>
>Consulte também o vídeo tutorial [aqui](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/building-a-journey/jumping-to-another-journey.html?lang=pt-BR)

## Vida útil

Digamos que você tenha adicionado uma atividade **[!UICONTROL Jump]** em uma jornada A a uma jornada B. A Jornada A é a **jornada de origem** e a jornada B, a **jornada de destino**.
Estas são as diferentes etapas do processo de execução:

**A Jornada** é acionada a partir de um evento externo:

1. A jornada A recebe um evento externo relacionado a um indivíduo.
1. O indivíduo alcança a etapa **[!UICONTROL Jump]**.
1. O indivíduo é empurrado para a Jornada B e avança para as próximas etapas na Jornada A, após a etapa **[!UICONTROL Jump]**.

Na jornada B, o primeiro evento é acionado internamente, por meio da atividade **[!UICONTROL Jump]** da jornada A:

1. A jornada B recebeu um evento interno da Jornada A.
1. O indivíduo começa a fluir na Jornada B.

>[!NOTE]
>
>A jornada B também pode ser acionada por meio de um evento externo.

## Práticas recomendadas e limitações

### Criação

* A atividade **[!UICONTROL Jump]** só está disponível em jornadas que usam um namespace.
* Você só pode ir para uma jornada que usa o mesmo namespace que a jornada de origem.
* Não é possível pular para uma jornada que começa com um evento **Segment qualification**.
* Não é possível ter uma atividade **[!UICONTROL Jump]** e um evento **Segment qualification** na mesma jornada.
* Você pode incluir quantas atividades **[!UICONTROL Jump]** forem necessárias em uma jornada. Após um **[!UICONTROL Jump]**, você pode adicionar qualquer atividade necessária.
* Você pode ter quantos níveis de salto forem necessários. Por exemplo, a Jornada A vai para a jornada B, que vai para a jornada C e assim por diante.
* A jornada de destino também pode incluir quantas atividades **[!UICONTROL Jump]** forem necessárias.
* Os padrões de loop não são suportados. Não há como vincular duas ou mais jornadas que criariam um loop infinito. A tela de configuração da atividade **[!UICONTROL Jump]** impede que você faça isso.

### Execução

* Quando a atividade **[!UICONTROL Jump]** é executada, a versão mais recente da jornada de destino é acionada.
* Como de costume, um indivíduo único só pode estar presente uma vez em uma mesma jornada. Como resultado, se o indivíduo enviado da jornada de origem já estiver na jornada de destino, o indivíduo não entrará na jornada de destino. Nenhum erro será relatado na atividade **[!UICONTROL Jump]** porque esse é um comportamento normal.

## Configuração da atividade Jump

1. Projete a **jornada de origem**.

   ![](../assets/jump1.png)

1. Em qualquer etapa da jornada, adicione uma atividade **[!UICONTROL Jump]** da categoria **[!UICONTROL ACTIONS]**. Adicione um rótulo e uma descrição.

   ![](../assets/jump2.png)

1. Clique dentro do campo **jornada do Target**.
A lista exibe todas as versões de jornada que são rascunho, ativo ou em modo de teste. Jornadas que usam um namespace diferente ou que começam com um evento **Segment qualification** não estão disponíveis. Jornadas do Target que criariam um padrão de loop também são filtradas.

   ![](../assets/jump3.png)

   >[!NOTE]
   >
   >Você pode clicar no ícone **Open target jornada**, no lado direito, para abrir a jornada do target em uma nova guia.

1. Selecione a jornada de destino para a qual você deseja ir.
O campo **First event** é preenchido com o nome do primeiro evento da jornada de destino. Se a jornada de destino incluir vários eventos, **[!UICONTROL Jump]** será permitido somente no primeiro evento.

   ![](../assets/jump4.png)

1. A seção **Action parameters** exibe todos os campos do evento de destino. Da mesma forma que para outros tipos de ações, mapeie cada campo com campos do evento de origem ou fonte de dados. Essas informações serão passadas para a jornada de destino no tempo de execução.
1. Adicione as próximas atividades para finalizar a jornada de origem.

   ![](../assets/jump5.png)


   >[!NOTE]
   >
   >A identidade do indivíduo é mapeada automaticamente. Essas informações não estão visíveis na interface.

Sua atividade **[!UICONTROL Jump]** está configurada. Assim que sua jornada estiver ativa ou no modo de teste, os indivíduos que atingem a etapa **[!UICONTROL Jump]** serão encaminhados do para a jornada de destino.

Quando uma atividade **[!UICONTROL Jump]** é configurada em uma jornada, um ícone de entrada **[!UICONTROL Jump]** é adicionado automaticamente no início da jornada de destino. Isso ajuda a identificar que a jornada pode ser acionada externamente, mas também internamente a partir de uma atividade **[!UICONTROL Jump]** .

![](../assets/jump7.png)

## Solução de problemas

Quando a jornada é publicada ou no modo de teste, os erros acontecerão se:
* a jornada de destino não existe mais
* a jornada do target é rascunho, fechada ou interrompida
* se o primeiro evento da jornada de destino tiver sido alterado e o mapeamento estiver quebrado

![](../assets/jump6.png)
