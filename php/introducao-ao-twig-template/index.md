---
title:       Introdução ao Twig template para PHP
description: Este artigo é uma introdução ao Twig Template Engine para PHP
capitulo:    "twig"
ordem:       1
---



## A linha divisória de sua view (visão)

    /app
        controllers/
            index.php
        views/
            index.php


```php
<?php

#
# Controller
#
$user = new User($_GET['id']);
$products = $users->products();


#
# View
#
echo $twig->render('views/index.html', array(
    'user'    => $user,
    'product' => $product
));
```



## Herança

```php{% raw  %}
<!DOCTYPE html>
<html>
    <head>
        {% block head %}{% endblock %}
    </head>
    <body>
        <div id="content">{% block content %}{% endblock %}</div>
        <div id="footer">{% block footer %}{% endblock %}</div>
    </body>
</html>{% endraw %}
```


```php{% raw  %}
{% extends "base.html" %}

{% block head %}
    <title>Index</title>
    <style type="text/css">
        .important { color: #336699; }
    </style>
{% endblock %}

{% block content %}
    <h1>Index</h1>
    <p class="important">
        Welcome to my awesome homepage.
    </p>
{% endblock %}

{% block footer %}
    &copy; Copyright 2011 by <a href="http://domain.invalid/">you</a>.
{% endblock %}{% endraw %}
```

 

## echo

Em PHP...

```php
<p><?php echo $var ?></p>
```

Com Twig...

```php
<p>{% raw  %}{{ var }}{% endraw %}</p>
```



## Estrutura de decisão

Em PHP...

```php
<?php if($var): ?>
    <p>true</p>
<?php else: ?>
    <p>false</p>
<?php endif; ?>
```

Com Twig...

```php
{% raw  %}{% if var %}
    <p>true</p>
{% else %}
    <p>false</p>
{% endif %}{% endraw %}
```



## Laço de Repetição

Em PHP...

```php
<h1>Members</h1>
<ul>
    <?php foreach($users as $user): ?>
        <li><?php echo $user['username'] ?></li>
    <?php endfor; ?>
</ul>
```

Com Twig...

```php
{% raw  %}<h1>Members</h1>
<ul>
    {% for user in users %}
        <li>{{ user.username }}</li>
    {% endfor %}
</ul>{% endraw %}
```



## Datas

Em PHP...

```php
<?php
$d = date('d/m/Y H:i');
echo $d;
```

Com Twig...

```php
{% raw  %}{{ "now"|date('d/m/Y H:i', timezone="Europe/Paris") }}{% endraw %}
```


