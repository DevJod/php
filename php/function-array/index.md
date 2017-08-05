---
layout:      functions
title:       PHP - Funções para array
description: 
capitulo:    "php-function"
ordem:       1
---

### array_pop

Para remover um valor no final do array:

    array_pop($arr);

Fonte: [Manual do PHP - array_pop](/php/refs/array_pop/)



### array_shift

Para remover um elemento do início do array:

    array_shift($arr);

Fonte: [Manual do PHP - array-shift](http://www.php.net/manual/pt_BR/function.array-shift.php "link-externo")


### array_unshift

Adiciona um elemento no início do array:

    array_unshift($arr, "valor");

Fonte: [Manual do PHP - array-unshift](http://www.php.net/manual/pt_BR/function.array-unshift.php "link-externo")



### unset

Para remover determinado elemento do array:

    unset($arr[5]);

Para remover o array da memória:

    unset($arr);

Fonte: [Manual do PHP - unset](http://www.php.net/manual/pt_BR/function.unset.php "link-externo")



### count

Retorna a quantidade de elementos de um array:

    count($arr);

Fonte: [Manual do PHP - count](http://www.php.net/manual/pt_BR/function.count.php "link-externo")


### explode

Transforma string em array.

```php
<?php
$arr = array();
$arr = explode("/", "20/01/2001");
var_dump($arr);
```

Resultado:

!["Imagem ilustrando o resulado da função explode()"](array06.png "Imagem ilustrando o resulado da função explode()")

Fonte: [Manual do PHP - explode](http://www.php.net/manual/pt_BR/function.explode.php "link-externo")



### implode

Tansforma array em string.


```php
<?php
$arr = array("Flavio", "Alexandre", "Micheletti");
$nomeCompleto = implode("-", $arr);
var_dump($nomeCompleto)
```

Resultado:

!["Imagem ilustrando o resulado da função implode()"](array07.png "Imagem ilustrando o resulado da função implode()")

Fonte: [Manual do PHP - implode](http://www.php.net/manual/pt_BR/function.implode.php "link-externo")



### in_array

Verifica se o array contém um determinado valor:

    in_array("valor", $arr);

Veja a assinatura do método.

    bool in_array ( mixed $needle , array $haystack [, bool $strict ] )

- `$needle`   - O valor procurado, se for uma string, a comparação é feita diferenciando caracteres maiúsculos e minúsculos.
- `$haystack` - O array.


Exemplos:

```php
<?php
var_dump(in_array(200, 100, 200, 300, 400)); // bool(true)
var_dump(in_array(900, $haystack));          // bool(false)
```

O terceiro parâmetro (`$strict`) nos ajuda-rá a checar os tipo, equivalente a `===`.

```php
<?php
# sem o terceiro parâmetro
var_dump(in_array("200", $haystack));       // bool(true)
# com o terceiro parâmetro
var_dump(in_array("200", $haystack, true)); // bool(false)
```

Quando `$neddle` também é um array:

```php
<?php
$haystack = array(
    array(100, 200),
    array(300, 400),
    500
);
var_dump(in_array(array(100, 200), $haystack)); // bool(true)
var_dump(in_array(array(600, 700), $haystack)); // bool(false)
var_dump(in_array(500, $haystack));             // bool(true)
```

Fonte: [Manual do PHP - in-array](http://www.php.net/manual/pt_BR/function.in-array.php "link-externo")




### array pop

Retira e retorna o último elemento do array.

    mixed array_pop ( array &$array )


Exemplo:

```php
<?php
$cesta = array("laranja", "banana", "melancia", "morango");
$fruta = array_pop($cesta);
print_r($cesta);
?>
```

O resultado será

    Array
    (
        [0] => laranja
        [1] => banana
        [2] => melancia
    )

Se o array estiver vazio (ou se não for um array), o valor `NULL` é retornado.

Emitirá um erro do tipo Warning quando invocado com um valor não-array.

A função irá "resetar" o ponteiro do array depois do uso.

Fonte: [Manual do PHP - array-pop](http://www.php.net/manual/pt_BR/function.array-pop.php "link-externo")

