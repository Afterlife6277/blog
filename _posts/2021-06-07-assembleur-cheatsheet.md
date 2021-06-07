---
title: Assembleur Cheatsheet
published: true
---

Les instructions, en assembleur sont parfois compliqués à retenir. C'est le langage de programmation, de plus bas niveau en même temps, ce qui signifie qu'il est très proche du langage machine, contrairement à d'autres langages comme Python, Java ou encore C qui eux sont considérés, comme des langages de haut niveau, donc plus proche du langage humain.

Je me suis donc permis, de vous préparer une petite Cheatsheet, avec les instructions fondamentales à connaître en assembleur. J'aime beaucoup désassembler, des programmes pour faire du reverse engineering et passer le temps, donc contrairement, à ce que l'on pourrait penser, ce langage est très utile et ne permet pas, d'uniquement programmer les composants d'une machine ou encore, seulement des compilateurs.

Bien sûr, tout ça est vraiment relatif, vous ne pourrez pas programmer des logiciels, uniquement en assembleur, à moins d'être une personne très déterminée et barbue.

## Les Instructions :

L'instruction MOV attribue une valeur dans un registre.

```assembly
MOV R0, R1
```

Dans notre cas, elle récupère la valeur stockée, dans le registre R1 puis elle l'a déplace, dans le registre R0.