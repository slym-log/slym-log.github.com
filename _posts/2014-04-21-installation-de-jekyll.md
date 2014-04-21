---
layout: post
title : Installation de Jekyll sur Mac OS
---

Pour installer Jekyll sur Mac OS, rien de plus simple.

	$ sudo gem install jekyll		
Par contre, il semble avoir des soucis avec OS X 10.9, une erreur de ce type peut apparaitre :	
	
	clang: error: unknown argument: ‘-multiply_definedsuppress’ [-Wunused-		command-line-argument-hard-error-in-future]
	
	clang: note: this will be a hard error (cannot be downgraded to a warning) 	in the future
	
	make : *** [redcarpet.bundle] Error 1
	
	make failed, exit code 2		
La solution la plus simple est de copier/coller ses commandes (une à la fois) dans le terminal.

	$ export ARCHFLAGS=”-Wno-error=unused-command-line-argument-hard-error-in-future
	$ export CFLAGS=-Wunused-command-line-argument-hard-error-in-future
	$ export CPPFLAGS=-Qunused-arguments
Devrez régler le problème.

Quand l’installation est finie, on peut générer son site. Pour ce faire, toujours en utilisant le terminal, se rendre dans le répertoire de votre choix puis exécuter cette commande.

	$ cd /chemin/de-mon/répertoire	
	$ jekyll new nom-de-votre-site
Voilà, votre site est prêt !	
Pour l’utiliser, aller dans le répertoire du site.

	$ jekyll -w serve
Cela permet de générer le site à la volée et donc de voir les modifications que vous faites sans devoir relancer constamment Jekyll. 
