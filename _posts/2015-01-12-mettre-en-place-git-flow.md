---
layout: post
title:  "Mettre en place git flow"
date:   2015-01-12 14:45:24
tags: ["git", "automation"]
---

## Préalable

Après avoir mis en place le célèbre [Git branching model](http://nvie.com/posts/a-successful-git-branching-model/) de [Vincent Driessen](http://nvie.com/about/) dans mes derniers projets, je me rends compte à quel point il est fastidieux de saisir manuellement toutes ces commandes.

Heureusement la procédure est également accompagnée d'un helper : [https://github.com/nvie/gitflow](https://github.com/nvie/gitflow)

Référence : [Why aren't you using git-flow ?](http://jeffkreeftmeijer.com/2010/why-arent-you-using-git-flow/)

## Installation

{% highlight bash %}
$ brew install git-flow
{% endhighlight %}

{% highlight console %}
==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/git-flow-0.4.1.yosemite.bottle.
######################################################################## 100,0%
==> Pouring git-flow-0.4.1.yosemite.bottle.tar.gz
==> Caveats
Bash completion has been installed to:
  /usr/local/etc/bash_completion.d

zsh completion has been installed to:
  /usr/local/share/zsh/site-functions
==> Summary
🍺  /usr/local/Cellar/git-flow/0.4.1: 15 files, 144K
{% endhighlight %}

Le script installe maintenant automatiquement le [git-flow-completion](https://github.com/bobthecow/git-flow-completion) dans /usr/local/etc/bash_completion.d/git-flow-completion.bash

Et c'est tout ... il n'y a plus qu'à utiliser les commandes de git flow

**Bonus**

Pour utiliser git dans un shell dédié, essayer [git-sh](https://github.com/rtomayko/git-sh).

## Utilisation

### Initialisation du dépôt git

{% highlight bash %}
$ git flow init
{% endhighlight %}

### Correction à chaud d'un bug en production (hotfix)

Un bug urgent à corriger sur la production ?

{% highlight bash %}
$ git flow hotfix start <nomduhotfix>
{% endhighlight %}

Il est temps de corriger ce bug puis ...

{% highlight bash %}
$ git flow hotfix finish <nomduhotfix>
{% endhighlight %}
