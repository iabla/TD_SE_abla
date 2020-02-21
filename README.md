# INSA 2SU 2020 - ABLA 

## Questions : 
Q1. Les chemins d'attaque possibles sur la signature d'un système embarqué : le port USB, ethernet port, mémoire flash, JTAG port, bouton reset ... 

Q2. 

Q3. La méthode pour aborder la sécurité sur un produit embarqué : 
- Il faut identifier le service le produit (quel besoin nous remplissons ?)
- Connaître les motivations de l'attaquant (qu'est ce qu'il va gagner ? ) 
- Identifier la surface, les chemins d'attaques  et les points d'entrée possibles pour accéder au système.

Etablir un mode d'attaquant est important pour comprendre comment l'attaquant va agir, connaître les étapes qu'il compte suivre et évaluer ses capacités.


Q4. Moyens pour faire le debugs embarqué  : emulation , qemu, ... les avantages sont : ils permettent de réaliser un déboggage rapide en quelques minutes.

Q5. Les catégories de bug possibles: 
Overflow
Double free

Q6.Améliorer la sécurité de l'embarqué : L'obfuscation 

C’est un ensemble de techniques destinées à rendre un code source moins lisible. Elle consiste à multiplier ces confusions entre données et instructions et à noyer le code parmi du faux code qui ne sert à rien ou des données aléatoires.



## TD 1 : Reverse engineering 

Le programme founi reçoit un mot de passe et vérifie s'il est correct ou non, le but de cet exercice est de modifier le programme compilé (le code binaire) de telle sorte que le programme puisse accepter n'importe quel mot de passe entré. 

### Les étapes suivies sont : 
1. On compile le programme : *gcc emily_crack.c -o a.out*

2. On teste : Please input a word: poop   
              That's correct!     

Please input a word: toto
That's not correct!

3. En utilisant l'utilitaire objdump, nous allons décomposer le programme en plusieurs opérations, chaque opération occupe une ligne dans le fichier objdump : *objdump -S -l -C -F -t -w a.out | less*
On peut facilement repérer les fonctions du programme (main, is_valid ) et les instructions de chacune de ces fonctions : 
![capture 1](https://github.com/iabla/TD_SE_abla/blob/master/docs/screens/Capture%20du%202020-02-21%2016-54-26.png)

4. On modifie le binaire (on modifie l'adresse qui va être appelée lorsque le mot de passe sera différent de "poop")
![capture 2](https://github.com/iabla/TD_SE_abla/blob/master/docs/screens/Capture%20du%202020-02-21%2016-54-12.png)

5. On teste : That's correct s'affiche quelque soilt le mot de passe entré : 
![capture 3](https://github.com/iabla/TD_SE_abla/blob/master/docs/screens/Capture%20du%202020-02-21%2016-53-45.png)





binaire de votre choix ls par ex -> il faut le patcher , changer son comportement 
