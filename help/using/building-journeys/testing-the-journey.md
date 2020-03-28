---
title: Testar a jornada
description: 'Saiba mais sobre testes de viagem '
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
source-git-commit: e53ecd96bbb308fe109843de6f64cde4cba5e246

---


# Testar a jornada{#testing_the_journey}

Antes de poder testar sua jornada, você deve resolver todos os erros, se houver. Consulte [](../about/troubleshooting.md#section_h3q_kqk_fhb).

Você tem a possibilidade de testar sua jornada antes da publicação, usando perfis de teste. Isso permite analisar como os indivíduos fluem na jornada e solucionam problemas antes da publicação.

Para usar o modo de teste, siga estas etapas:

1. Antes de testar sua jornada, verifique se ela é válida e se não há erro. Você não poderá iniciar um teste de uma jornada com erros. Consulte [](../about/troubleshooting.md#section_h3q_kqk_fhb). Um símbolo de aviso é exibido quando há erros.

1. Para ativar o modo de teste, clique na **[!UICONTROL Test]** alternância localizada no canto superior direito.

   ![](../assets/journeytest1.png)

1. Use o tempo de **espera no parâmetro de teste** , no canto inferior esquerdo, para definir o tempo que cada atividade de espera durará no modo de teste. O tempo padrão é de 10 segundos. Isso garantirá que você obtenha os resultados do teste rapidamente. Este parâmetro só será exibido se você tiver soltado uma ou mais atividades de espera em sua jornada.

   ![](../assets/journeytest_wait.png)

1. Clique **[!UICONTROL Trigger an event]** para configurar e enviar eventos para a jornada. Certifique-se de enviar eventos relacionados a perfis de teste. Consulte [Disparando seus eventos](#firing_events).

   ![](../assets/journeyuctest1.png)

1. Depois que os eventos forem recebidos, clique no **[!UICONTROL Show log]** botão para visualização do resultado do teste e verificá-los. Consulte [Visualização dos registros](#viewing_logs).

   ![](../assets/journeyuctest2.png)

1. Se houver algum erro, desative o modo de teste, modifique sua jornada e teste-a novamente. Quando o teste é conclusivo, você pode publicar sua jornada. Consulte [](../building-journeys/publishing-the-journey.md).

## Observações importantes {#important_notes}

* É fornecida uma interface para disparar eventos para a viagem testada, mas eventos também podem ser enviados por sistemas de terceiros, como o Postman.
* Somente indivíduos marcados como &quot;perfis de teste&quot; no Serviço de Perfil do Cliente em tempo real poderão entrar na jornada testada. O processo para criar um perfil de teste é o mesmo que o processo para criar um Perfil na Plataforma de dados. Você só precisa ter certeza de que a bandeira do perfil de teste é verdadeira. Você pode usar a seção Segmentos na interface da Plataforma de dados para criar um segmento de perfis de teste na Plataforma de dados e ver uma lista não exaustiva. A lista exaustiva não pode ser exibida por enquanto.
* O modo de teste só está disponível em viagens de rascunho que utilizem uma namespace. Na verdade, o modo de teste precisa verificar se uma pessoa que entra na jornada é um perfil de teste ou não e, portanto, deve poder acessar a Plataforma de Dados.
* O número máximo de perfis de teste que podem entrar em uma jornada durante uma sessão de teste é 100.
* Quando você desativa o modo de teste, ele esvazia as viagens de todas as pessoas que entraram no modo de teste ou que estão atualmente nele.
* Você pode ativar/desativar o modo de teste quantas vezes forem necessárias.
* Não é possível modificar sua jornada quando o modo de teste é ativado. Quando estiver no modo de teste, você pode publicar diretamente a jornada, não é necessário desativar o modo de teste antes.

## Acionando seus eventos {#firing_events}

O **[!UICONTROL Trigger an event]** botão permite configurar um evento que fará com que uma pessoa entre na jornada.

Como pré-requisito, você deve saber quais perfis são sinalizados como perfis de teste na Plataforma de dados. Na verdade, o modo de teste só permite esses perfis na jornada e o evento deve conter uma ID. A ID esperada depende da configuração do evento. Pode ser um ECID, por exemplo.

Se sua jornada contiver vários eventos, use a lista suspensa para selecionar um evento. Em seguida, para cada evento, configure os campos transmitidos e a execução do envio do evento. A interface o ajuda a passar as informações certas na carga do evento e a verificar se o tipo de informações está correto. O modo de teste salva os últimos parâmetros usados em uma sessão de teste para uso posterior.

![](../assets/journeytest4.png)

A interface permite que você passe parâmetros de evento simples. Se quiser passar coleções ou outros objetos avançados no evento, clique em para ver todo o código da carga e modificá-lo. **[!UICONTROL Code View]** Por exemplo, você pode copiar e colar informações do evento preparadas por um usuário técnico.

![](../assets/journeytest5.png)

Um usuário técnico também pode usar essa interface para compor cargas úteis de eventos e acionar eventos sem precisar usar uma ferramenta de terceiros.

## Exibição dos registros {#viewing_logs}

O **[!UICONTROL Show log]** botão permite que você visualização os resultados do teste. Esta página exibe as informações atuais da jornada no formato JSON. Um botão permite copiar nós inteiros. É necessário atualizar manualmente a página para atualizar os resultados de teste da jornada.

![](../assets/journeytest3.png)

>[!NOTE]
>
>Nos registros de teste, no caso de erro ao chamar um sistema de terceiros (fonte de dados ou ação), o código de erro e a resposta do erro são exibidos.

O número de indivíduos (tecnicamente chamados de instâncias) atualmente dentro da jornada é exibido. Estas são informações úteis exibidas para cada indivíduo:

* _Id_: a ID interna da pessoa na jornada. Isso pode ser usado para fins de depuração.
* _etapa atual_: a etapa em que o indivíduo está na viagem. Recomendamos adicionar etiquetas às suas atividades para identificá-las mais facilmente.
* _etapa atual_ > fase: o estado da viagem da pessoa (em execução, concluída, erro ou tempo limite). Consulte abaixo para obter mais informações.
* _etapa atual_ > _extraInfo_: descrição do erro e outras informações contextuais.
* _currentstep_ > _fetchErrors_: informações sobre erros de busca de dados ocorridos durante esta etapa.
* _externalKeys_: o valor da fórmula de chave definida no evento.
* _EnhedData_: os dados que a jornada recuperou se a jornada utiliza fontes de dados.
* _TransitionHistory_: a lista de etapas que o indivíduo seguiu. Para eventos, a carga é exibida.
* _actionExecutionErrors_ : informações sobre os erros que ocorreram.

