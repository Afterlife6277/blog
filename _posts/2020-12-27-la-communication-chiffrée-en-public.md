---
layout: post
title: La communication chiffrée en public
permalink: la-communication-chiffrée-en-public/
status: en-cours
---

Est-ce possible de se parler secrètement en public ?
{: .message }

Dans le monde de la cryptographie, deux cryptologues américains du nom de [Whitfield Diffie](https://fr.wikipedia.org/wiki/Whitfield_Diffie) et [Martin Hellman](https://fr.wikipedia.org/wiki/Martin_Hellman), ont créé un algorithme qu'ils ont ainsi nommés l'algorithme d'échange de clés de Diffie-Hellman.

> Le principe, consiste à pouvoir communiquer secrètement en public, en chiffrant les messages de deux agents, que nous nommerons par convention Alice et Bob. Ses deux agents, peuvent se mettre d'accord sur un nombre qu'ils utiliseront par la suite comme la clef pour chiffrer la conversation. Un troisième agent, que nous appellerons Charlotte ne peut donc pas découvrir se nombre même en ayant écouté au préalable tous leurs échanges.

Cet algorithme d'échanges de clés de Diffie-Hellman leur valut le prix Turing en 2015.

## Introduction

Pendant des millénaires, les plus grands cryptographes étaient obligés de se rencontrer au préalable en secret, afin de se mettre d'accord sur la façon de chiffrer et déchiffrer leurs messages. 

Et pour l'instant, il semblait mathématiquement impossible que deux agents, nommés précédemment Alice et Bob puissent se parler secrètement sans n'avoir déjà parlé secrètement avant au préalable. Puis en 1976, les informaticiens et cryptologues Diiffe et Hellman ont démontré l'impossible en trouvant un protocole cryptographique pour que nos deux agents Alice et Bob puissent se parler secrètement sans n'avoir jamais eu à se parler secrètement avant.

### Explication du protocole

On considère nos deux agents Alice et Bob. Nos deux agents ont chacun une valise, un cadenas et une clef. Sachant que seul Alice peut déverrouiller son cadenas et Bob de même pour Bob.
