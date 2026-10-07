---
product: adobe campaign
title: filtro
description: Saiba mais sobre o filtro de função
feature: Journeys
role: Developer
level: Experienced
exl-id: 3c1c188c-0ffd-44c5-b1b3-1758ed12235e
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 10%
---
# filtro{#filter}

Retorna um listObject com objetos que têm o atributo de chave correspondente a um dos valores de chave fornecidos.

## Categoria

Lista

## Sintaxe da função

`filter(<parameters>)`

## Parâmetros

| Parâmetro | Tipo | Descrição |
|-----------|------------------|------------------|
| listToFilter | listObject | lista de objetos a serem filtrados. Deve ser uma referência de campo. |
| keyAttributeName | sequência de caracteres | nome do atributo nos objetos da lista fornecida, usado como chave para filtragem |
| keyValueList | list | matriz de valores principais para filtragem |

## Assinaturas e tipos retornados

`filter(listObject, string, listString)`

`filter(listObject, string, listInteger)`

`filter(listObject, string, listDecimal)`

`filter(listObject, string, listDateTime)`

`filter(listObject, string, listDateTimeOnly)`

`filter(listObject, string, listDateOnly)`

`filter(listObject, string, listDuration)`

`filter(listObject, string, listBoolean)`

Retorna um listObject.

## Exemplos

Este é um exemplo de uma carga útil transmitida em um evento de entrada &quot;myevent&quot;:

```json
"productListItems": [{
   "id": "product1",
   "name": "the product 1",
   "price": 20
},{
   "id": "product2",
   "name": "the product 2",
   "price": 30
},{
   "id": "product3",
   "name": "the product 3",
   "price": 50
}]
```

Você pode usar a seguinte expressão:

```json
filter(
 @{myevent.productListItems},
 "id", 
 ["product2", "product3", "product4"]
)
```

Retorna um listObject contendo os dois objetos com &quot;product2&quot; e &quot;product3&quot; como id.
