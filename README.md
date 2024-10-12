# OpenBar Pocket Reborn

## Un peu d'histoire

[OpenBar Pocket](https://github.com/fusetim/open_bar_pocket) est la précédente itération d'une application mobile pour le service [OpenBar](https://github.com/CETEN-OpenBar/bar/). Réalisé en Dart avec Flutter, dans un but de simplement "jouer avec" tout en faisant quelque chose d'utile.

Aujourd'hui, le 12 octobre 2024, OpenBar Pocket n'est réellement utilisé que par moi-même, notamment car je n'ai pas vraiment envie d'assurer le support et qu'il y a d'assez gros problèmes à régler (quelques bugs graphiques, l'affichage des prix qui n'est pas tout à fait correcte, le manque d'infinity-scroll etc). Hélas, Flutter / Dart est un écosystème assez particulier avec lequel je n'ai pas forcément beaucoup l'occasion de passer du temps dessus. 

OpenBar Pocket Reborn est la deuxième itération d'une application mobile pour le service [OpenBar](https://github.com/CETEN-OpenBar/bar/), cette fois-ci écrit
en Typescript (Svelte 5) pour son UI, Rust pour son "backend" et supporté par [Tauri](https://v2.tauri.app). Le but n'est toujours pas d'en faire un remplacement
ou complément réel à OpenBar, mais de jouer encore une fois avec des écosystèmes nouveaux tout en faisant quelque chose d'intéressant. Si je n'ai jamais touché à
Tauri et que son écosystème est plutôt nouveau, j'ai passé déjà un certain sur Svelte (notamment la version 5) ce qui devrait régler pas mal les problèmes graphiques
de la dernière édition, mais aussi avec Rust, qui assurera le "backend" de l'application.

C'est donc encore une fois un plongeon dans l'inconnu pour voir la viabilité de ce type de plateforme.