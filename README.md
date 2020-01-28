# INSA 2SU 2020 - ABLA 

## Questions : 
Q1. 
Q2.
Q3. 
produit ou service (le besoin qu'on rempli)
qu'est ce que l'attaquant peut gagner en faisant ça (
par où on rentre dans le système ? 

Q4. debug embarqué = emulation , qemu, ... les avantages pour debugger rapidement (moins de qlq min)
les catégories de bug : overflow... voir cours (comment attaquer comment défendre ...)

Q6.comment améliorer la sécurité de l'embarqué 



## TD 1 : Reverse engineering 

Le programme founi reçoit un mot de passe et vérifie s'il est correct ou non, le but de cet exercice est de modifier le programme compilé (le code binaire) de telle sorte que le programme puisse accepter n'importe quel mot de passe entré. 

### Les étapes suivies sont : 
1. On compile le programme : *gcc emily_crack.c -o a.out*

2. On teste : Please input a word: poop                   Please input a word: toto
              That's correct!                             That's not correct!

3. En utilisant l'utilitaire objdump, nous allons décomposer le programme en plusieurs opérations, chaque opération occupe une ligne dans le fichier objdump : *objdump -S -l -C -F -t -w a.out | less*
On peut facilement repérer les fonctions du programme (main, is_valid ) et les instructions de chacune de ces fonctions : 
![Capture hexa](https://github.com/iabla/TD_SE_abla/raw/master/docs/screens/Capture%20du%202020-01-28%2016-04-34.png)



binaire de votre choix ls par ex -> il faut le patcher , changer son comportement 
