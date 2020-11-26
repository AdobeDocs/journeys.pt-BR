---
product: adobe campaign
solution: Journey Orchestration
title: Operadores
description: Saiba mais sobre operadores em expressões avançadas
translation-type: tm+mt
source-git-commit: 20498e89eb9c95dd19a11e42150a0bbf67024f67
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 5%

---



# Operadores {#concept_wd5_pj5_dgb}

Há dois tipos de operadores: operadores unários e binários. Há operadores unários à esquerda e operadores unários à direita.

```
    // left-hand unary operators
    <operator> <operand> // operand is an expression
    not (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example@adobe.com")

    // right-hand unary operators
    <operand> <operator> // operand is an expression
    @{LobbyBeacon.endUserIDs._experience.emailid.id} is not null

    // binary operators
    <operand1> <operator> <operand2>
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example1@adobe.com") or
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example2@adobe.com")
```

Esta é a lista dos operadores suportados:

## Lógica  {#logical}

### e

**Expressão literal**

```<expression1> and <expression2>```

Ambos &lt;expressão1> e &lt;expressão2> devem ser booleanos. O resultado é booleano.

**Exemplo**

```3.14 > 2 and 3.15 < 1```

### ou

**Expressão literal**

```<expression1> or <expression2>```

Ambos &lt;expressão1> e &lt;expressão2> devem ser booleanos. O resultado é booleano.

**Exemplo**

```3.14 > 2 or 3.15 < 1```

### not

**Expressão literal**

```not <expression>```

&lt;expressão> deve ser booleano. O resultado é booleano.

**Exemplo**

```not 3.15 < 1```

## Comparação {#comparison}

### é nulo

**Expressão literal**

```<expression> is null```

O resultado é booleano.

Observe que nulo significa que a expressão não tem valor avaliado.

**Exemplo**

```@{BarBeacon.location} is null```

### não é nulo

**Expressão literal**

```<expression> is not null```

O resultado é booleano.

Observe que nulo significa que a expressão não tem valor avaliado.

**Exemplo**

```@ is not null```

### tem nulo

**Expressão literal**

```<expression> has null```

&lt;expressão> deve ser uma lista. O resultado é booleano.

Útil para identificar se uma lista contém pelo menos um valor nulo.

**Exemplo**

```["foo", "bar", null] has null``` retorna true.

```["foo", "bar", ""] has null``` retorna false porque &quot;&quot; não é considerado nulo.

### ==

**Expressão literal**

```<expression1> == <expression2>```

As opções &lt;expressão1> e &lt;expressão2> devem ter o mesmo tipo de dados. O resultado é booleano.

**Exemplo**

```3.14 == 42```

```"foo" == "bar"```

### !=

**Expressão literal**

```<expression1> != <expression2>```

As opções &lt;expressão1> e &lt;expressão2> devem ter o mesmo tipo de dados. O resultado é booleano.

**Exemplo**

```3.14 != 42```

```"foo" != "bar"```

### >

**Expressão literal**

```<expression1> > <expression2>```

A data e hora pode ser comparada com a data e hora.

Só é possível comparar Datetimeonly com Datetimeonly.

Tanto o número inteiro quanto o número decimal podem ser comparados com o número inteiro ou o número decimal.

Qualquer outra combinação é proibida.

O resultado é booleano.

**Exemplo**

```3.14 > 42```

### >=

**Expressão literal**

```<expression1> >= <expression2>```

A data e hora pode ser comparada com a data e hora.

Só é possível comparar Datetimeonly com Datetimeonly.

Tanto o número inteiro quanto o número decimal podem ser comparados com o número inteiro ou o número decimal.

Qualquer outra combinação é proibida.

O resultado é booleano.

**Exemplo**

```42 >= 3.14```

### &lt;

**Expressão literal**

```<expression1> < <expression2>```

A data e hora pode ser comparada com a data e hora.

Só é possível comparar Datetimeonly com Datetimeonly.

Tanto o número inteiro quanto o número decimal podem ser comparados com o número inteiro ou o número decimal.

Qualquer outra combinação é proibida.

O resultado é booleano.

**Exemplo**

```42 < 3.14```

### &lt;=

**Expressão literal**

```<expression1> <= <expression2>```

A data e hora pode ser comparada com a data e hora.

Só é possível comparar Datetimeonly com Datetimeonly.

Tanto o número inteiro quanto o número decimal podem ser comparados com o número inteiro ou o número decimal.

Qualquer outra combinação é proibida.

O resultado é booleano.

**Exemplo**

```42 <= 3.14```

## Aritmética {#arithmetic}

### +

**Expressão literal**

```<expression1> + <expression2>```

Ambas as expressões devem ser numéricas (números inteiros ou decimais).

O resultado também é numérico.

**Exemplo**

```1 + 2``` devoluções 3

### -

**Expressão literal**

```<expression1> - <expression2>```

Ambas as expressões devem ser numéricas (números inteiros ou decimais).

O resultado também é numérico.

**Exemplo**

```2 - 1``` retorna 1

### /

**Expressão literal**

```<expression1> / <expression2>```

Ambas as expressões devem ser numéricas (números inteiros ou decimais).

O resultado também é numérico.

&lt;expressão2> não deve ser igual a 0 (retorna 0).

**Exemplo**

```4 / 2``` retorna 2

### *

**Expressão literal**

```<expression1> * <expression2>```

Ambas as expressões devem ser numéricas (números inteiros ou decimais).

O resultado também é numérico.

**Exemplo**

```3 * 4``` retorna 12

### %

**Expressão literal**

```<expression1> % <expression2>```

Ambas as expressões devem ser numéricas (números inteiros ou decimais).

O resultado também é numérico.

**Exemplo**

```3 % 2``` retorna 1.

## Matemática {#math}

### é numérico

**Expressão literal**

```<expression> is numeric```

O tipo da expressão é inteiro ou decimal.

**Exemplo**

```@ is numeric```

### é integer

**Expressão literal**

```<expression> is integer```

O tipo da expressão é inteiro.

**Exemplo**

```@ is integer```

### é decimal

**Expressão literal**

```<expression> is decimal```

O tipo da expressão é decimal.

**Exemplo**

```@ is decimal```

## String {#string}

### +

**Expressão literal**

```<string> + <expression>```

```<expression> + <string>```

Concatena duas expressões.

Uma expressão deve ser uma cadeia encadeada.

**Exemplo**

```"the current time is " + (now())``` retorna &quot;a hora atual é 2019-09-23T09:30:06.693Z&quot;

```(now()) + " is the current time"``` retorna &quot;2019-09-23T09:30:06.693Z é a hora atual&quot;

```"a" + "b" + "c" + 1234``` retorna &quot;abc1234&quot;.

## Data {#date}

### +

**Expressão literal**

```<expression + <duration>```

Anexe uma duração a dateTime, a dateTimeOnly ou a duração.

**Exemplo**

```toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M")``` retorna 2011-12-03T15:30:30Z

```toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M")``` retorna 2011-12-03T15:30:30

```now() + toDuration("PT1H")``` retorna um dateTime (com fuso horário UTC) uma hora depois do horário atual

```toDuration("PT1H") + toDuration("PT1H")``` retorna PT2H
