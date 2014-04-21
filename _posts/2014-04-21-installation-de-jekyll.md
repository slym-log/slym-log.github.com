---
layout: post
title: Installation de Jekyll sur Mac OS
---

Pour installer Jekyll sur Mac OS, rien de plus simple.		
`$ sudo gem install jekyll`			
Vous entrez votre mot de passe et vous valider. Par contre, selon la version de Xcode, il est possible que vous ayez une erreur de ce type :			
	clang: error: unknown argument: ‘-multiply_definedsuppress’ [-Wunused-		command-line-argument-hard-error-in-future]
	
	clang: note: this will be a hard error (cannot be downgraded to a warning) 	in the future
	
	make: *** [redcarpet.bundle] Error 1
	
	make failed, exit code 2		
La solution la plus simple, copier/coller ses commandes (une à la fois) dans le terminal.
`$ export ARCHFLAGS=”-Wno-error=unused-command-line-argument-hard-error-in-future”
`$ export CFLAGS=-Wunused-command-line-argument-hard-error-in-future`
`export CPPFLAGS=-Qunused-arguments`