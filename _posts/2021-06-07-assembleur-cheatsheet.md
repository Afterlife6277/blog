---
title: Assembleur Cheatsheet
published: true
---

Les instructions, en assembleur sont parfois compliqués à retenir. C'est le langage de programmation, de plus bas niveau en même temps, ce qui signifie qu'il est très proche du langage machine, contrairement à d'autres langages comme Python, Java ou encore C qui eux sont considérés, comme des langages de haut niveau, donc plus proche du langage humain.

Je me suis donc permis, de vous préparer une petite Cheatsheet, avec les instructions fondamentales à connaître en assembleur. J'aime beaucoup désassembler, des programmes pour faire du reverse engineering et passer le temps, donc contrairement, à ce que l'on pourrait penser, ce langage est très utile et ne permet pas, d'uniquement programmer les composants d'une machine ou encore, seulement des compilateurs.

Bien sûr, tout ça est vraiment relatif, vous ne pourrez pas programmer des logiciels, uniquement en assembleur, à moins d'être une personne très déterminée et barbue.

## Les Instructions :

L'instruction MOV (move) attribue une valeur dans un registre.

```assembly
MOV R0, R1
```

> Dans notre cas, elle récupère la valeur stockée, dans le registre R1 puis elle l'a place, dans le registre R0.



L'instruction CALL appelle une procédure (sub-routine).

```assembly
CALL function_name
```

> Dans notre cas, elle appelle la fonction située dans *function_name*.



L'instruction RET appelle la dernière instruction d'une procédure.

```assembly
RET function_name
```

> Dans notre cas, elle appelle, la dernière instruction de la procédure *function_name*.



L'instruction ADD (addition) additionne une valeur puis place le résultat dans un registre.

```assembly
ADD R0, R1, R2
```

> Dans notre cas, elle récupère la valeur stockée, dans le registre R2, elle l'additionne à la valeur stockée dans le registre R1, puis elle place le résultat dans le registre R0.



L'instruction SUB (subtraction) soustrait une valeur puis place le résultat dans un registre.

```assembly
SUB R0, R1, R2
```

> Dans notre cas, elle récupère la valeur stockée dans le registre R2, elle l'a soustrait à la valeur stockée dans le registre R1, puis elle place le résultat dans le registre R0.



L'instruction INC (increment) incrémente de 1 une valeur dans un registre.

```assembly
INC R0
```

> Dans notre cas, elle ajoute 1 à la valeur du registre R0.



L'instruction DEC (decrement) décrémente de 1 une valeur dans un registre.

```assembly
DEC R0
```

> Dans notre cas, elle enlève 1 à la valeur du registre R0.



L'instruction NOP n'effectue rien.

~~JNE function_name~~ #avant

```assembly
NOP
```

> Dans notre cas, on remplace l'instruction JNE, par l'instruction NOP, afin que l'instruction JNE ne soit pas exécutée.



L'instruction CMP (compare) effectue une comparaison entre deux éléments.

```assembly
CMP R0, R1
```

> Dans notre cas, elle récupère la valeur stockée, dans le registre R1 et elle l'a compare à la valeur stockée, dans le registre R0.



L'instruction JMP (jump) effectue un saut sans conditions.

```assembly
JMP function_name
```

> Dans notre cas, elle effectue un saut vers l'adresse *function_name*.

## Les sauts conditionnels :

L'instruction JE (jump if equal) effectue un saut conditionnel par rapport au résultat de l'instruction CMP précédente si le résultat est égal.

```assembly
JE function_name
```

> Dans notre cas, elle effectue un saut vers l'adresse *function_name* si le résultat, de l'instruction CMP effectué avant est égal.



L'instruction JNE (jump if not equal) effectue un saut conditionnel par rapport au résultat de l'instruction CMP précédente si le résultat est différent.

```assembly
JNE function_name
```

> Dans notre cas, elle effectue un saut vers l'adresse *function_name* si le résultat, de l'instruction CMP effectué avant est différent.



L'instruction JZ (jump if zero) effectue un saut conditionnel par rapport au résultat de l'instruction CMP précédente si le résultat est nul.

```assembly
JZ function_name
```

> Dans notre cas, elle effectue un saut vers l'adresse *function_name* si le résultat, de l'instruction CMP effectué avant est égal à 0.



L'instruction JNZ (jump if not zero) effectue un saut conditionnel par rapport au résultat de l'instruction CMP précédente si le résultat n'est pas nul.

```assembly
JNZ function_name
```

> Dans notre cas, elle effectue un saut vers l'adresse *function_name* si le résultat, de l'instruction CMP effectué avant n'est pas égal à 0.

------
```shell
$ echo "Auteur : Keany Vy KHUN"
```

- Lire la publication sur Github : [Assembleur Cheatsheet](https://github.com/thisiskeanyvy/thisiskeanyvy.github.io/blob/main/_posts/2021-06-07-assembleur-cheatsheet.md)

Si cet article n'est pas complet ou comporte des erreurs merci de me contacter. Mes informations de contact sont dans la section [À Propos](https://thisiskeanyvy.github.io/about/).

Merci à vous, d'avoir pris le temps de lire cet article !! ;-)