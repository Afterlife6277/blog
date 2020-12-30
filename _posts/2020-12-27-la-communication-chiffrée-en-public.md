---
layout: post
title: La communication chiffrée en public
permalink: la-communication-chiffrée-en-public/
status: fini
---

Est-ce possible de se parler secrètement en public ?
{: .message }

Dans le monde de la cryptographie, deux cryptologues américains du nom de [Whitfield Diffie](https://fr.wikipedia.org/wiki/Whitfield_Diffie) et [Martin Hellman](https://fr.wikipedia.org/wiki/Martin_Hellman), ont créé un algorithme qu'ils ont ainsi nommés l'algorithme d'échange de clés de Diffie-Hellman.

> Le principe, consiste à pouvoir communiquer secrètement en public, en chiffrant les messages de deux agents, que nous nommerons par convention Alice et Bob. Ses deux agents, peuvent se mettre d'accord sur un nombre qu'ils utiliseront par la suite comme la clef pour chiffrer la conversation. Un troisième agent, que nous appellerons Charlotte ne peut donc pas découvrir se nombre même en ayant écouté au préalable tous leurs échanges.

Cet algorithme d'échanges de clés de Diffie-Hellman leur valut le prix Turing en 2015.

## Introduction

Pendant des millénaires, les plus grands cryptographes étaient obligés de se rencontrer au préalable en secret, afin de se mettre d'accord sur la façon de chiffrer et déchiffrer leurs messages. 

Et pour l'instant, il semblait mathématiquement impossible que deux agents, nommés précédemment Alice et Bob puissent se parler secrètement sans n'avoir déjà parlé secrètement avant au préalable. Puis en 1976, les informaticiens et cryptologues Diiffe et Hellman ont démontré l'impossible en trouvant un protocole cryptographique pour que nos deux agents Alice et Bob puissent se parler secrètement sans n'avoir jamais eu à se parler secrètement avant.

### Schéma d'une partie de protocole (mais pas encore entièrement sécurisé)

On considère nos deux agents Alice et Bob. Nos deux agents ont chacun une valise, un cadenas et une clef. Sachant que seul Alice peut déverrouiller son cadenas et de même pour Bob. Par ailleurs, on sait qu'ils ne peuvent que communiquer en s'envoyant des valises via la poste. Or on sait aussi que les valises sont régulièrement ouvertes et pillés par la poste.

Donc pour communiquer en toute sécurité, prenons l'exemple d'Alice, qui prend sa valise et qui met sa lettre à l'intérieur. Elle ferme ensuite, sa valise avec son cadenas puis envoie la valise cadenassée à Bob. Or on sait que Bob ne peut pas l'ouvrir, il met ainsi un second cadenas en parallèle du premier sur la valise d'Alice. Puis il renvoie la valise doublement cadenassée à Alice.

Alors, Alice enlève son cadenas de la valise puis renvoie la valise simplement cadanasée. Ainsi, Bob peut enfin déverrouiller son cadenas, ouvrir la valise et ainsi lire la lettre d'Alice.

*Attention, il reste encore un petit problème.*
{: .message }

Considérons maintenant, que la poste, que nous avons considérée comme intermédiaire, entre nos deux agents ou qu'un autre agent que nous avons nommés précédemment Charlotte, puisse à présent casser le cadenas sur la valise.

Ils auraient alors, une possibilité de contourner le protocole et celui-ci n'aurait donc servi à rien. Donc ce protocole n'est pas sécurisé et c'est justement à ce moment précis, que l'algorithme de Diffie-Hellman répond à la problématique.

### Le protocole de l'algorithme de Diffie-Hellman

Dans le cas de l'algorithme de Diffie-Hellman, on considère que nos deux agents Alice et Bob ont à leur disposition des haut-parleurs de sorte qu'ils sont capables de s'envoyer des messages. Or, le problème c'est que les messages qu'ils s'envoient sont publics.

Donc pour communiquer, il leur faudra parler de façon à chiffrer leurs messages. Or pour chiffrer leurs messages, il leur faudra se mettre secrètement d'accord sur quel chiffrement utiliser alors même, que le choix de ce chiffrement sera issu d'une conversation entièrement publique.

Comment peuvent-ils y remédier ?
{: .message }

En s'appuyant sur les [mathématiques modulaires](https://fr.wikipedia.org/wiki/Arithm%C3%A9tique_modulaire), Alice va choisir et crier un nombre premier que l'on nomme par convention $$ p $$ et ce nombre premier doit être cryptographique, ensuite elle devra crier un autre très grand nombre que nous nommerons $$ g $$.

On considère à présent qu'Alice crie le nombre $$ p = 100.000.217 $$ et $$ g = 123 $$. Bob prend donc note de ses deux nombres, ensuite Alice et Bob vont ensuite se créer une sorte de clef de cadenas. Cette clef secrète sera donc de l'ordre de grandeur de p et nous les nommerons a et b. Les deux clefs précédemment créent seront pour jamais secrètes donc seul Alice connaîtra a et seul Bob connaîtra b.

Enfin, Alice va calculer et crier le nombre g exposant a, de même Bob va calculer et crier g exposant de b. Ensuite, Alice va prendre le nombre g exposant b et mettre ce nombre à la puissance de a. Elle obtient alors $$ (gb)^a $$ et de façon symétrique, Bob prend g exposant a puis il met ce nombre à la puissance b pour obtenir $$ (ga)^b $$.

D'où $$ (gb)^a = g^(ab) = (ga)^b $$ on remarquera qu'Alice et Bob auront donc calculé le même nombre.

|Informations publiques|Informations privées|
|----------------------|--------------------|
|$$ p $$ et $$ g $$    |                    |
|$$ (g^a) $$ et $$ (g^b) $$ | $$ a $$ et $$ b $$ |

*Attention, ceci n'est qu'un exemple dans la mathématique des nombre entiers.*
{: .message }

En circonstance réelle, il faudra exécuter les mathématiques modulo $$ p $$. Ce qui aura pour effet de rendre les calculs d'Alice et Bob beaucoup plus faciles. Car dans cette mathématique, calculer n'importe quel nombre exposant n'importe quel autre nombre, peut se faire facilement.

Cependant, grâce au protocole de Diffie-Hellman, un autre agent Charlotte ne pourra pas trouver les clefs secrètes de $$ a $$ et $$ b $$ appartenant à Alice et Bob. Car en effet, il est extrêmement difficile de calculer a à partir de $$ g^a $$.  
> $$ a $$ -> $$ (g^a) $$ | *facile*  
$$ (g^a) $$ -> $$ a $$ | *difficile*

On dit donc que l'opération pour passer de $$ a $$ à $$ (g^a) $$ est une fonction à sens unique.

*Attention, d'après la loi de Moore la puissance de calcul des ordinateurs évolue constement et pour le moment, il est uniquement possible de calculer $$ a $$ à partir de $$ (g^a) $$ avec un ordinateur quantique.*
{: .message }

Pour conclure, un autre agent Charlotte ne peut déterminer ni $$ a $$, ni $$ b $$. Il lui est alors impossible de calculer g(ab) à partir des informations publiques que nous retrouvons dans le tableau ci-dessus.

Le protocole de Diffie-Hellman permet donc de créer un secret partagé à savoir le nombre $$ g(a^b) $$. Et grâce à ce secret, Alice et Bob peuvent utiliser d'autres outils cryptographiques pour déterminer un chiffrement commun qui leur permettra ensuite de communiquer de manière complètement chiffrée sans avoir eu à se rencontrer à l'avance au préalable.
