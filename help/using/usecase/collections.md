---
product: adobe campaign
solution: Journey Orchestration
title: Envio dinâmico de coleções usando ações personalizadas
description: Envio de uma mensagem usando o Campaign v7/v8
exl-id: 9ed62a74-3c51-4f15-af8a-d530ddf80b51
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 7%

---

# Envio dinâmico de coleções usando ações personalizadas{#passing-collection}


>[!CAUTION]
>
>**Procurando Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para obter a documentação do Journey Optimizer.
>
>
>_Esta documentação se refere ao material herdado do Journey Orchestration que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de conta em caso de dúvidas sobre o acesso ao Journey Orchestration ou Journey Optimizer._


Você pode passar uma coleção em parâmetros de ação personalizados que serão preenchidos dinamicamente no tempo de execução. Há suporte para dois tipos de coleções:

* coleções simples: matrizes de tipos de dados simples, por exemplo, com uma listString:

  ```
  {
   "deviceTypes": [
       "android",
       "ios"
   ]
  }
  ```

* coleções de objetos: uma matriz de objetos JSON, por exemplo:

  ```
  {
  "products":[
     {
        "id":"productA",
        "name":"A",
        "price":20.1
     },
     {
        "id":"productB",
        "name":"B",
        "price":10.0
     },
     {
        "id":"productC",
        "name":"C",
        "price":5.99
     }
   ]
  }
  ```

## Limitações {#limitations}

* Matrizes aninhadas de objetos em uma matriz de objetos não têm suporte no momento. Por exemplo:

  ```
  {
  "products":[
    {
       "id":"productA",
       "name":"A",
       "price":20,
       "locations": [{"name": "Paris"}, {"name": "London"}]
    },
   ]
  }
  ```

* Para testar coleções usando o modo de teste, é necessário usar o modo de visualização de código. No momento, o modo de exibição de código não é compatível com eventos comerciais. Você só pode enviar uma coleção com um único elemento.

## Procedimento geral {#general-procedure}

Nesta seção, usaremos o seguinte exemplo de carga JSON. Esta é uma matriz de objetos com um campo que é uma coleção simples.

```
{
  "ctxt": {
    "products": [
      {
        "id": "productA",
        "name": "A",
        "price": 20.1,
        "color":"blue",
        "locations": [
          "Paris",
          "London"
        ]
      },
      {
        "id": "productB",
        "name": "B",
        "price": 10.99
      }
    ]
  }
}
```

Você pode ver que &quot;produtos&quot; é uma matriz de dois objetos. Você precisa ter pelo menos um objeto.

1. Crie sua ação personalizada. Consulte [esta página](../action/about-custom-action-configuration.md).

1. Na seção **[!UICONTROL Action parameters]**, cole o exemplo JSON. A estrutura exibida é estática: ao colar a carga, todos os campos são definidos como constantes.

   ![](../assets/uc-collection-1.png)

1. Se necessário, ajuste os tipos de campo. Os seguintes tipos de campo são compatíveis com coleções: listString, listInteger, listDecimal, listBoolean, listDateTime, listDateTimeOnly, listDateOnly, listObject

   >[!NOTE]
   >
   >O tipo de campo é inferido automaticamente de acordo com o exemplo de carga útil.

1. Se você quiser passar objetos dinamicamente, precisará defini-los como variáveis. Neste exemplo, definimos &quot;products&quot; como variável. Todos os campos de objeto incluídos no objeto são definidos como variáveis automaticamente.

   >[!NOTE]
   >
   >O primeiro objeto do exemplo de carga útil é usado para definir os campos.

1. Para cada campo, defina o rótulo que será exibido na tela de jornada.

   ![](../assets/uc-collection-2.png)

1. Crie sua jornada e adicione a ação personalizada que você criou. Consulte [esta página](../building-journeys/using-custom-actions.md).

1. Na seção **[!UICONTROL Action parameters]**, defina o parâmetro de matriz (&quot;produtos&quot; em nosso exemplo) usando o editor de expressão avançado.

   ![](../assets/uc-collection-3.png)

1. Para cada um dos campos de objeto a seguir, digite o nome do campo correspondente do esquema XDM de origem. Se os nomes forem idênticos, isso não será necessário. No nosso exemplo, precisamos definir apenas &quot;product id&quot; e &quot;color&quot;.

   ![](../assets/uc-collection-4.png)

Para o campo de matriz, também é possível usar o editor de expressão avançado para executar a manipulação de dados. No exemplo a seguir, usamos as funções [filtro](../functions/functionfilter.md) e [interseção](../functions/functionintersect.md):

![](../assets/uc-collection-5.png)

## Casos específicos{#examples}

Para tipos heterogêneos e arrays de arrays, o array é definido com o tipo listAny. Você só pode mapear itens individuais, mas não pode alterar a matriz para a variável.

![](../assets/uc-collection-heterogeneous.png)

Exemplo de tipo heterogêneo:

```
{
    "data_mixed-types": [
        "test",
        "test2",
        null,
        0
    ]
}
```

Exemplo de matriz de matrizes:

```
{
    "data_multiple-arrays": [
        [
            "test",
            "test1",
            "test2"
        ]
    ]
}
```

**Tópicos relacionados**

[Usar ações personalizadas](../building-journeys/using-custom-actions.md)
