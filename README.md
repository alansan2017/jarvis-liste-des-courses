<!---
IMPORTANT
=========
This README.md is displayed in the WebStore as well as within Jarvis app
Please do not change the structure of this file
Fill-in Description, Usage & Author sections
Make sure to rename the [en] folder into the language code your plugin is written in (ex: fr, es, de, it...)
For multi-language plugin:
- clone the language directory and translate commands/functions.sh
- optionally write the Description / Usage sections in several languages
-->
## LISTE DE COURSES IMPRIMABLE !

## Description
Gestion de liste de courses basée sur plusieurs magasins 

Imprimera au final une liste complète de courses classées par magasins! 
Pas d'envois sur email dans cette version !! mais peux être ajouté en option en ajoutant les commandes originales ;-)

Important: décompresser l'archive magasins.tar.gz à la racine de votre répertoire personnel:
résultat : /home/USER/magasins/

## Usage
'*AJOUTE*ALDI (*)==echo "[ ] (1)" >> ~/magasins/aldi.txt && say "j'ai rajouté (1) chez aldi"
...' etc

'*EFFACE*ALDI==say "Veux tu confirmer la supression de la liste d'aldi?"
>*OUI*==echo "" > ~/magasins/aldi.txt && say "Ok la liste d'aldi est réinitialisée" && echo "" >> ~/magasins/aldi.txt && echo "[ ] CHEZ ALDI:" >> ~/magasins/aldi.txt && echo "" >> ~/magasins/aldi.txt
>*NON*==say "Je ne la supprime pas"
...' etc

'*QUOI*DANS*ALDI==say "$(cat ~/magasins/aldi.txt)"
...' etc

'*QUOI*DANS*COUR*==cat ~/magasins/trafic.txt >> ~/magasins/listecourses.txt ; cat ~/magasins/colruyt.txt >> ~/magasins/listecourses.txt ; cat ~/magasins/lidl.txt >> ~/magasins/listecourses.txt ; cat ~/magasins/aldi.txt >> ~/magasins/listecourses.txt ; cat ~/magasins/carrefour.txt >> ~/magasins/listecourses.txt ; cat ~/magasins/makro.txt >> ~/magasins/listecourses.txt ; cat ~/magasins/cora.txt >> ~/magasins/listecourses.txt ; cat ~/magasins/solderie.txt >> ~/magasins/listecourses.txt && say "$(cat ~/magasins/listecourses.txt)" ;say "la liste est-elle complète?"
>*NON*==say "OK, complète la liste de courses quand tu veux $username"
>*OUI*==say "faut-il l'imprimer?"
>>*NON*==say "OK $username, je ne l'imprime pas"
>>*OUI*==say "OK, je te l'imprime de suite" && lpr <<< cat ~/magasins/listecourses.txt ; say "l'impression est en cours $usename !" '

You: ajoute chez aldi du pain
Jarvis: j'ai rajouté du pain chez aldi
You: ajoute chez carrefour pizza
Jarvis: j'ai rajouté pizza chez carrefour
You: il y a quoi dans aldi
Jarvis: [ ] CHEZ ALDI:
jarvis:
Jarvis: [ ] du pain
You: y'a quoi dans la liste de courses
Jarvis: LISTE DE COURSES DU JOUR:
Jarvis: 
Jarvis: 
Jarvis: 
Jarvis: [ ] CHEZ TRAFIC:
Jarvis: 
Jarvis: 
Jarvis: 
Jarvis: [ ] CHEZ COLRUYT:
Jarvis: 
Jarvis: 
Jarvis: 
Jarvis: [ ] CHEZ LIDL:
Jarvis: 
Jarvis: 
Jarvis: 
Jarvis: [ ] CHEZ ALDI:
Jarvis: 
Jarvis: [ ] du pain
Jarvis: 
Jarvis: 
Jarvis: [ ] CHEZ CARREFOUR:
Jarvis: 
Jarvis: [ ] pizza
Jarvis: 
Jarvis: 
Jarvis: [ ] CHEZ MAKRO:
Jarvis: 
Jarvis: 
Jarvis: 
Jarvis: [ ] CHEZ CORA:
Jarvis: 
Jarvis: 
Jarvis: 
Jarvis: [ ] CHEZ LEDISCOUNT:
Jarvis: la liste est-elle complète?
*NON*			*OUI*
You: non
Jarvis: OK, complète la liste de courses quand tu veux You
...
Jarvis: la liste est-elle complète?
*NON*			*OUI*
You: oui
Jarvis: faut-il l'imprimer?
*NON*			*OUI*
You: oui
Jarvis: OK, je te l'imprime de suite
Jarvis: l'impression est en cours  !


```


## Author
[tchoul] et [godinperson] (https://github.com/tchoul)
