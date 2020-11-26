---
product: adobe campaign
solution: Journey Orchestration
title: Operadores
description: Saiba mais sobre operadores em expressões avançadas
translation-type: tm+mt
source-git-commit: 062b4648e2eb3a4270f9c09e4478d541209e1247
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 6%

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

```
<expression1> and <expression2>
```

Ambos &lt;expressão1> e &lt;expressão2> devem ser booleanos. O resultado é booleano.

Exemplo:

```
3.14 > 2 and 3.15 < 1
```

### ou



```
<expression1> or <expression2>
```

Ambos &lt;expressão1> e &lt;expressão2> devem ser booleanos. O resultado é booleano.

Exemplo:

```
3.14 > 2 or 3.15 < 1
```

### not



```
not <expression>
```

&lt;expressão> deve ser booleano. O resultado é booleano.

Exemplo:

```
not 3.15 < 1
```

## Comparação {#comparison}

### é nulo



```
<expression> is null
```

O resultado é booleano.

Observe que nulo significa que a expressão não tem valor avaliado.

Exemplo:

```
@{BarBeacon.location} is null
```

### não é nulo



```
<expression> is not null
```

O resultado é booleano.

Observe que nulo significa que a expressão não tem valor avaliado.

Exemplo:

```
@ is not null
```

### tem nulo



```
<expression> has null
```

&lt;expressão> deve ser uma lista. O resultado é booleano.

Útil para identificar se uma lista contém pelo menos um valor nulo.

Exemplo:

```
["foo", "bar", null] has null --  returns true.
```

```
["foo", "bar", ""] has null -- returns false because "" is not considered as null.
```

### ==



```
<expression1> == <expression2>
```

As opções &lt;expressão1> e &lt;expressão2> devem ter o mesmo tipo de dados. O resultado é booleano.

Exemplo:

```
3.14 == 42
```

```
"foo" == "bar"
```

### !=



```
<expression1> != <expression2>
```

As opções &lt;expressão1> e &lt;expressão2> devem ter o mesmo tipo de dados. O resultado é booleano.

Exemplo:

```
3.14 != 42
```

```
"foo" != "bar"
```

### >



```
<expression1> > <expression2>
```

A data e hora pode ser comparada com a data e hora.

Só é possível comparar Datetimeonly com Datetimeonly.

Tanto o número inteiro quanto o número decimal podem ser comparados com o número inteiro ou o número decimal.

Qualquer outra combinação é proibida.

O resultado é booleano.

Exemplo:

```
3.14 > 42
```

### >=



```
<expression1> >= <expression2>
```

A data e hora pode ser comparada com a data e hora.

Só é possível comparar Datetimeonly com Datetimeonly.

Tanto o número inteiro quanto o número decimal podem ser comparados com o número inteiro ou o número decimal.

Qualquer outra combinação é proibida.

O resultado é booleano.

Exemplo:

```
42 >= 3.14
```

### &lt;



```
<expression1> < <expression2>
```

A data e hora pode ser comparada com a data e hora.

Só é possível comparar Datetimeonly com Datetimeonly.

Tanto o número inteiro quanto o número decimal podem ser comparados com o número inteiro ou o número decimal.

Qualquer outra combinação é proibida.

O resultado é booleano.

Exemplo:

```
42 < 3.14
```

### &lt;=



```
<expression1> <= <expression2>
```

A data e hora pode ser comparada com a data e hora.

Só é possível comparar Datetimeonly com Datetimeonly.

Tanto o número inteiro quanto o número decimal podem ser comparados com o número inteiro ou o número decimal.

Qualquer outra combinação é proibida.

O resultado é booleano.

Exemplo:

```
42 <= 3.14
```

## Aritmética {#arithmetic}

### +



```
<expression1> + <expression2>
```

Ambas as expressões devem ser numéricas (números inteiros ou decimais).

O resultado também é numérico.

Exemplo:

```
1 + 2 -- returns 3
```

### -



```
<expression1> - <expression2>
```

Ambas as expressões devem ser numéricas (números inteiros ou decimais).

O resultado também é numérico.

Exemplo:

```
2 - 1 -- returns 1
```

### /



```
<expression1> / <expression2>
```

Ambas as expressões devem ser numéricas (números inteiros ou decimais).

O resultado também é numérico.

&lt;expressão2> não deve ser igual a 0 (retorna 0).

Exemplo:

```
4 / 2 -- returns 2
```

### *



```
<expression1> * <expression2>
```

Ambas as expressões devem ser numéricas (números inteiros ou decimais).

O resultado também é numérico.

Exemplo:

```
3 * 4 -- returns 12
```

### %



```
<expression1> % <expression2>
```

Ambas as expressões devem ser numéricas (números inteiros ou decimais).

O resultado também é numérico.

Exemplo:

```
3 % 2 -- returns 1.
```

## Matemática {#math}

### é numérico



```
<expression> is numeric
```

O tipo da expressão é inteiro ou decimal.

Exemplo:

```
@ is numeric
```

### é integer



```
<expression> is integer
```

O tipo da expressão é inteiro.

Exemplo:

```
@ is integer
```

### é decimal



```
<expression> is decimal
```

O tipo da expressão é decimal.

Exemplo:

```
@ is decimal
```

## String {#string}

### +



```
<string> + <expression>
```

```
<expression> + <string>
```

Concatena duas expressões.

Uma expressão deve ser uma cadeia encadeada.

Exemplo:

```
"the current time is " + (now()) -- returns "the current time is 2019-09-23T09:30:06.693Z"
```

```
(now()) + " is the current time" -- returns "2019-09-23T09:30:06.693Z is the current time"
```

```
"a" + "b" + "c" + 1234 -- returns "abc1234".
```

## Data {#date}

### +



```
<expression + <duration>
```

Anexe uma duração a dateTime, a dateTimeOnly ou a duração.

Exemplo:

```
toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M") -- returns 2011-12-03T15:30:30Z
```

```
toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M") -- returns 2011-12-03T15:30:30
```

```
now() + toDuration("PT1H") -- returns a dateTime (with UTC time zone) one hour later from current time
```

```
toDuration("PT1H") + toDuration("PT1H") -- returns  PT2H
```
