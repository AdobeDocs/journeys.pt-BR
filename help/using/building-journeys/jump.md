---
title: Saltando de uma viagem para outra
description: Saltando de uma viagem para outra
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 1ec824dcfd54bde5f3aab80ce30dbc9a19b9e4c1
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 0%

---


# Saltando de uma viagem para outra {#jump}

>[!NOTE]
>
>Disponibilidade efetiva: 15 de novembro de 2020

A atividade de ação **Saltar** permite que você empurre indivíduos de uma jornada para outra. Este recurso permite:

* simplificar a concepção de viagens muito complexas, dividindo-as em várias
* construir viagens baseadas em padrões de viagem comuns e reutilizáveis

Na jornada da origem, basta adicionar um **Salto** e selecionar uma jornada do público alvo. Quando o indivíduo entra na etapa de salto, um evento interno é enviado para o primeiro evento da jornada do público alvo. Se a ação de salto for bem sucedida, o indivíduo continua a progredir na jornada. O comportamento é semelhante a outras ações.

Na jornada do público alvo, o primeiro evento acionado internamente pelo salto fará o fluxo individual na jornada.

## Ciclo

Digamos que você adicionou um salto em uma jornada A a uma jornada B. A jornada A é a jornada **da** origem e a jornada B, a jornada **do**público alvo.
Estas são as diferentes etapas do processo de execução:

**A jornada A** é disparada a partir de um evento externo:

1. A jornada A recebe um evento externo relacionado a um indivíduo.
1. O indivíduo atinge o salto.
1. O indivíduo é empurrado para a Jornada B, e segue para os próximos passos na Jornada A, depois do salto.

Na **jornada B**, o primeiro evento pode ser acionado externamente (como um evento normal) ou internamente, através de um salto da jornada A:

1. A jornada B recebeu um evento interno da Jornada A.
1. O primeiro evento da Jornada B é acionado com as informações vindas da Jornada A.
1. Os start individuais que fluem na Jornada B.

## Observações importantes

* Você só pode pular para uma jornada que usa a mesma namespace que a jornada da origem.
* Não é possível pular para uma jornada que se start com um evento de qualificação **de** Segmento.
* Quando o salto é executado, a versão mais recente da jornada do público alvo é acionada.
* Você pode incluir tantos saltos quanto precisar em uma jornada. Após um salto, você pode adicionar qualquer atividade necessária.
* Você pode ter quantos níveis de salto forem necessários. Por exemplo, a jornada A vai para a jornada B, que vai para a jornada C, e assim por diante.
* A jornada do público alvo também pode incluir quantos saltos forem necessários.
* Os padrões de loop não são suportados. Não há como ligar duas ou mais viagens que criariam um ciclo infinito. A tela de configuração **Jump** atividade impede que você faça isso.
* Como de costume, um indivíduo único só pode estar presente uma vez na mesma jornada. Como resultado, se o indivíduo empurrado da jornada de origem já está na jornada do público alvo, então o indivíduo não entrará na jornada do público alvo. Nenhum erro será relatado no salto porque esse é um comportamento normal.

## Configuração do salto

1. Projete sua jornada de origem.

   ![](../assets/jump1.png)

1. Em qualquer etapa da jornada, adicione uma atividade de **Salto** , da categoria **Action** . Adicione um rótulo e uma descrição.

   ![](../assets/jump2.png)

1. Clique dentro do campo de viagem **do** Público alvo.
A lista exibe todas as versões de viagem que estão em modo de rascunho, ao vivo ou de teste. As viagens que usam uma namespace diferente ou aquele start com um evento de qualificação **de** Segmento não estão disponíveis. As viagens de público alvo que criariam um padrão de ciclo também são filtradas.

   ![](../assets/jump3.png)

   >[!NOTE]
   >
   >Você pode clicar no ícone **Abrir jornada** do público alvo, no lado direito, para abrir a jornada do público alvo em uma nova guia.

1. Selecione a jornada do público alvo para a qual você deseja pular.
O campo **Primeiro evento** é preenchido com o nome do primeiro evento da jornada do público alvo. Se sua jornada de público alvo incluir vários eventos, o salto só será permitido no primeiro evento.

   ![](../assets/jump4.png)

1. A seção Parâmetros **de** ação exibe todos os campos do evento do público alvo. Da mesma forma que para outros tipos de ações, mapeie cada campo com campos do evento de origem ou fonte de dados. Essas informações serão passadas para a jornada do público alvo no tempo de execução.
1. Adicione as próximas atividades para terminar sua jornada de origem.

   ![](../assets/jump5.png)

Seu salto está configurado. Assim que sua jornada estiver ao vivo ou no modo de teste, os indivíduos que chegarem ao salto serão empurrados da jornada para o público alvo.

Quando um salto é configurado em uma jornada, um ícone de entrada de salto é adicionado automaticamente no início da jornada do público alvo. Isso ajuda a identificar que a jornada pode ser acionada externamente, mas também internamente, a partir de um salto.

## Solução de problemas

Quando a viagem é publicada ou está em modo de teste, ocorrerão erros se:
* a viagem de público alvo já não existe
* a viagem de público alvo for desembaraçada, fechada ou interrompida
* se o primeiro evento da jornada do público alvo tiver mudado e o mapeamento estiver quebrado