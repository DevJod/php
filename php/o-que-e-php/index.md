---
title:       O que é php?
description: Artigo introdutório sobre PHP
capitulo:    "php-capitulo-1"
ordem:       1
---

> O PHP é uma linguagem popular de script (scripting language) de propósito geral que é especialmente adequada para 
> desenvolvimento web. Rápido, flexível e pragmático, o PHP pode fazer tudo, desde um blog até o sites mais populares do mundo.
>
> [Fonte: php.net](www.php.net)

PHP é uma linguagem de programação para uso geral.

Inicialmente, projetada por [Rasmus Lerdorf](http://pt.wikipedia.org/wiki/Rasmus_Lerdorf "link-externo") na década de
1990, tinha como objetivo principal contar as visitas que eram realizadas em seu currículo on-line.  Hoje (quase 20 anos
depois, estrou [re]escrevendo este artigo em julho/2017) ainda é isso o que fazemos com PHP, alteramos o  HTML de forma 
dinâmica lá no lado do servidor. À primeira vista, pode parecer algo simples e até estúpido, mas é assim que é, e posso 
garatir a você, é uma terafa desafiadora. Com o tempo, você descobrirá que ele pode fazer muito mais do que alterar HTML 
(rss), poderá fazer API's consistentes e que trabalham com JSON, por exemplo.

O PHP atua junto com um servidor web, esse último é alguém que foi programado para escutar requisições HTTP e devolver
algum tipo de resposta. Fazendo o papel de cliente, temos o browser, o seu navegador web! Ele é um softwarer que faz 
requisições web.

![](requisicoes.png "")

Pode dormir e sonhar com essa imagem, é esse o fluxo (à grosso modo) de um modelo cliente/servidor.


## Você precisa entender o processo

Um domínio, por exemplo `devfuria.com.br`, está configurado para apontar para determinado servidor. Neste referido
servidor, temos nossa estrutura de diretórios. Uma pasta muito importante é a raiz de documento (documentroot), o nome
dessa pasta normalmente é `public_html` ou `htdocs`.


![](document-root-02.png "")

![](document-root-01.png "")

Dentro de nosso documentroot temos uma infinidade de scripts que respondem pelas requisções, eles são arquivos de texto 
simples salvos com a extensão `.php`. Dentro de uma pasta, o script padrão executado será o de nome `index`, veja figura
abaixo.

![](index-php-01.png "")

Em outras palavras, o servidor irá procurar por esse nome, se ele achar, executa, se não achar ele listará o diretório,
veja figura abaixo. O programador mudou o nome do arquivo para `indexador.php`, portanto, o servidor não soube que script
executar e resolveu mostrar (listar) os arquivos contidos na pasta.

![](apache-lista-diretorio-01.png "")


Continuando, vamos imaginar que o domínio `dev.opera.com` está apontando para o número IP 213.236.208.98. Quando você
abrir seu navegador e digitar a URL `devfuria.com.br/php` ele irá fazer uma requisição através do protocolo HTTP para
o número do IP mencionado, vai percorrer dividido em pacotes por um "caminho maluco" chamado INTERNET (peça para uma cara 
de "redes' explicar esse negócio à você) e finalmente, vai bater no servidor. Este, encontrando o resultado, devolve
para o cliente o HTML. Estamos ainda nos referindo sobre o modelo cliente/servidor e sobre requisições e respostas 
(requests and responses). Veja a imagem abaixo.

![](requisicoes-02.gif "")


![](modelo-cliente-servidor-02.jpeg "")


## Hello World com PHP




## Desafios

1. Releia o artigo e me diz qual foi a sua dúvida nos comentários abaixo.
2. Abra um editor de texto qualquer e crie um arquivo PHP que faça alguma coisa, nem que seja um "hello world".
3. Procure na web por cada um dos itens avaixo que você desconhece...
    - modelo cliente-servidor
    - protocole HTTP
    - requisições (requests) HTTP
    - respostas (responses) HTTP
    - servidor web
    - script
    - domínio (para web)
    - URL
    - script
4. Descubra quais são os servidores web disponível.


## Olha o que eu selecionei para vc

links e mais links