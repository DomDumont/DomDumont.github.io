---
layout: post
title:  "OSX Ouvrir le Finder dans un répertoire spécifique depuis un programme c/c++"
date:   2015-06-16 15:59:34
categories: divers
---

C’est tellement stupide que je devais l’écrire quelque part. J’ai passé vraiment trop de temps sur ce problème 😉

Je vouIais juste ouvrir l’application depuis mon application c/c++. Après une recherche rapide sur Google, je suis tombé sur la solution (enfin c’est ce que je croyais) un simple

	system ('open mypath')

devait faire l’affaire.

Je test dans Xcode … Bingo ça marche, j’étais trop content !

Malheureusement, quand je me suis mis à lancer mon programme hors de Xcode (c’est à dire depuis le finder) Bim, le drame. Rien ne marchait. La fonction « system » me renvoit des erreurs. Pourquoi ? Je n’en sais toujours rien. Est-ce un problème de privilèges ? un problème de Sandbox ? Si vous avez la réponse, laissez moi un commentaire, ça m’intéresse je suis vraiment curieux.

En fait la solution était bien plus complexe que prévue. Grâce au code source de QTCreator j’ai vu comment il fallait faire : Il faut executer un appleScript (via osascript) pour dire au finder d’ouvrir un fichier posix et executer une autre commande applescript pour dire au finder de se mettre devant toutes les autres fenêtres … Are you serious Apple ???

	std::string tempPath;
	std::string command;
	tempPath = currentDir;
	command = "osascript -e 'tell app \"Finder\" to open POSIX file \""+ tempPath+"\"'";
	system(command.c_str());
	command = "osascript -e 'tell application \"Finder\" to activate'";
	system(command.c_str());

