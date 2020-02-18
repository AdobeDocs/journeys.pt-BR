---
title: Notas de versão
description: Saiba mais sobre as notas de versão
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
source-git-commit: 8023d7780d43f1de4447c63568f641ce204722c7

---


# Notas de versão {#release-notes}

Esta página lista todos os novos recursos e melhorias para o Journey Orchestration.
Você também pode consultar as Atualizações [da](../release-notes/documentation-updates.md)documentação.

## Versão do primeiro trimestre - fevereiro de 2019 {#q1-release---february-2019}

**Gerenciamento de fuso horário**

Os fusos horários agora são gerenciados no nível da jornada. Foram adicionados dois parâmetros às propriedades de viagem:

* O menu suspenso **Fuso horário** permite selecionar um fuso horário específico. Por padrão, o fuso horário do navegador é usado.

* A caixa de seleção Fuso horário **do perfil** permite usar o fuso horário do Perfil da plataforma de experiência da pessoa que entra na jornada, se disponível. Caso contrário, o fuso horário definido na lista suspensa será usado. Este recurso não é compatível com viagens sem namespace.

**Ajuda contextual**

Uma função de ajuda contextual agora está disponível em diferentes telas de orquestração de jornada. Isso significa que, em um único clique, você pode acessar diretamente a documentação sobre a funcionalidade que está usando no momento.

Para exibir a ajuda contextual, clique no ícone &quot;i&quot; no canto superior direito da tela.

Por enquanto, esse recurso está disponível nas telas Início, Fontes de dados, Eventos e lista de ações.

**Outras alterações**

* No modo de teste, um novo parâmetro permite que você defina o tempo do afinador.  as atividades de espera de tempo podem durar. Isso permite acessar os resultados do teste rapidamente.

* No modo de teste, agora você pode acionar todos os eventos da jornada.


* um novo parâmetro permite que você defina o tempo do peafiner.  as atividades de espera de tempo podem durar. Isso permite acessar os resultados do teste rapidamente.

* O Journey Orchestration está agora disponível na EMEA.

* Novo ícone na paleta para exibir ou não itens disponíveis. sans namespace. par padrão .

* tela de desenho, desconexão, icone petite, qui dit desconectou o nó.

* lista de títulos do atalho C

* interface do usuário da paleta, resultado de pesquisa icone de

* Pouvoir capper les chama a des APIS externes (fontes de dados ou ações). marque n&#39;accept que 500 chama par seconde, elle pourra mettre un capping a 500 chamadas de segundos qui evite de overcharge system de loyalty tiers tiers

* logs du test log. Status de disponibilidade = erro. sistema de cor em paleta. Possibilityé de voir code erreur words que&#39;à renvidé le systeme. -> ds un test en cas d&#39;erreur, níveis do sistema, código de erro, resposta de erro.

* interrupção da eliminação da viagem

* viagem: versão 1 il the met is latest

1er mars.


## Versão GA - dezembro de 2019 {#ga-release---december-2019}

A Orquestração de Jornadas está agora pronta.

Crie casos de uso de orquestração em tempo real aproveitando dados contextuais armazenados em eventos ou fontes de dados.

O Journey Orchestration permite a orquestração em tempo real com dados contextuais de eventos, informações da Adobe Experience Platform ou dados de serviços de API de terceiros. O aplicativo determina, em fluxos em várias etapas, as próximas melhores ações específicas ao consumidor, com base no seu perfil e comportamento. Isso inclui o tempo ideal, bem como o tipo de ação, como enviar ao consumidor uma notificação por push por meio dos recursos de mensagens transacionais do Adobe Campaign Standard (requer o Adobe Campaign Standard) ou a notificação de um sistema de terceiros. Essas decisões são tomadas com base em regras e pontuações do Sensei.

[Saiba mais](../action/working-with-adobe-campaign.md) sobre a Journey Orchestration.

Recursos adicionais:

* [Tutoriais](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [Comunidade](https://www.adobe.com/go/journeyorchestrationcommunity)