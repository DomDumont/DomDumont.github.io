---
layout: post
title:  "Comment builder un project android/c++ fait sous Eclipse à partir d’un fichier de commande batch"
date:   2015-06-18 15:59:34
categories: divers
---

Salut à tous,

Si vous êtes comme moi, vous utilisez toujours des fichiers batch sous windows alors que c’est super « old-school ».

Si vous voulez compiler un projet android/jni fait sous Eclipse depuis un fichier batch, c’est finalement plus facile que prévu.

1) Il faut avoir tout (java/SDK/NDK/ant/…) installé et accessible dans votre PATH windows

2) N’utilisez pas ndk-build mais plutôt ndk-build.__cmd__ à la place.  Comme ce n’est pas un exécutable mais un fichier de commande, vous devez l’appeler avec un CALL sinon vous allez interrompre l’exécution du fichier batch courant.

3) N’utilisez pas « ant release » mais plutôt « ant __clean__ release » parce que les ressources ne sont pas compatibles entre eclipse et ant donc si vous switchez sans cleaner auparavant, ça ne marchera pas.

4) Le résultat :

	PUSHD ..\myproject\android

	call ndk-build.cmd clean
	call ndk-build.cmd
	call ant clean release

	POPD

