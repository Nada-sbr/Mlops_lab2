**Étape 1 : Initialiser Git dans mlops-lab-01**

**Objectif** : Placer le projet MLOps sous contrôle de version Git pour suivre les modifications, collaborer et assurer la reproductibilité.

Initialiser le dépôt Git et  Vérifier l’état du 

dépôt :

![1.png](screen-lab02/1.png)

**Étape 2 : Premier commit du projet** 
**Objectif** : Voir comment Git suit les changements dans les fichiers de travail et comment utiliser les outils de staging (`git diff` et `git diff --staged`).

**MLOps**Créer le premier commit :

![2.png](screen-lab02/2.png)

Afficher l’historique :

![3.png](screen-lab02/3.png)

**Étape 3 : Observer une modification avec git diff**

**Objectif** : Simuler un développement de nouvelle fonctionnalité en utilisant une branche Git isolée pour éviter de casser la branche principale (`master`).

Afficher les différences par rapport au dernier commit 

![4.png](screen-lab02/4.png)

Ajouter le fichier modifié à l’index et  Afficher les différences en staging :

![5.png](screen-lab02/5.png)

Créer un commit :

![6.png](screen-lab02/6.png)

**Étape 4 : Créer une branche de fonctionnalité liée au lab:**

**Objectif** : Intégrer la fonctionnalité développée et testée sur la branche isolée  dans la branche de base (`master`)

Créer une branche Ajouter et committer puis aficher Lister les branches  et puis Revenir sur la branche principale :

<img width="1856" height="562" alt="image" src="https://github.com/user-attachments/assets/6d2bea69-7b7d-4132-bd5a-cb1a58246a87" />


**Étape 5 : Fusionner la branche feature dans la branche principale**

**Objectif** : Apprendre à gérer un scénario courant de collaboration où deux branches modifient la même partie du même fichier, entraînant un conflit de fusion

Fusionner la branche 

<img width="1856" height="311" alt="image" src="https://github.com/user-attachments/assets/fbd0bd73-4736-4260-b168-1f2d808d3dc2" />


Vérifier l’historique :

![7.png](screen-lab02/7.png)

**Étape 6 : Créer un conflit de merge sur src/train.py**

Créer une nouvelle branche Modifier `src/train.py`  puuis Ajouter et committer :
![8.png](screen-lab02/8.png)

Revenir sur la branche principale puis Modifier la même ligne dans `src/train.py` puis Ajouter et committer  :
![9.png](screen-lab02/9.png)
Tenter la fusion  il y’a un conflit alors Résoudre le conflit :

<img width="1904" height="349" alt="image" src="https://github.com/user-attachments/assets/be085a8e-6839-47f2-9af6-89ae1b68f83d" />


**Étape 7 : Utiliser git stash dans le contexte du lab**

Modifier un fichier sans vouloir committer (src/rollback.py) et Afficher l’état :

![10.png](screen-lab02/10.png)

Mettre de côté les modifications et Lister les stash  et Récupérer les modifications :

![11.png](screen-lab02/11.png)

<img width="1763" height="801" alt="image" src="https://github.com/user-attachments/assets/471d1cb2-54e9-450f-90ba-62382e8baf52" />


**Étape 8 : Tester git reset sur un fichier d’expérimentation**

Créer un dossier d’expérimentation et Créons un fichier de test:

![13.png](screen-lab02/13.png)

Modifier puis committer deux fois :

<img width="1895" height="317" alt="image" src="https://github.com/user-attachments/assets/797f981b-fd0e-4f23-8280-160adda48d01" />


<img width="1888" height="316" alt="image" src="https://github.com/user-attachments/assets/fc993ae1-6c26-4f3f-8e38-ab5fe87eade7" />


Effectuer un reset soft :

<img width="1888" height="747" alt="image" src="https://github.com/user-attachments/assets/5be8976b-6341-4a53-b3c4-eb12ab6a2dd9" />


Effectuer un reset mixed puis un reset hard :

![15.png](screen-lab02/15.png)

**Étape 9 : Annuler un commit avec git revert**

Ajouter un changement non souhaité dans `src/api.py` puis on a Lister les commits  et on a fait Revert du dernier commit :

![16.png](screen-lab02/16.png)

on Vérifie le contenu du fichier :

![17.png](screen-lab02/17.png)

**Étape 10 : Rebase d’une branche feature sur la branche principale**

Créons une branche et Modifions`src/monitor_drift.py` pui on Ajout et commit:

<img width="1913" height="329" alt="image" src="https://github.com/user-attachments/assets/251fcf6a-ae95-4f09-9947-7ad31f8b5d05" />


 

Revenir sur la branche principale et créons un nouveau commit sur un autre fichier (par exemple `src/generate_data.py`)  puis Revenons sur la branche feature : 

<img width="1913" height="476" alt="image" src="https://github.com/user-attachments/assets/ac31e644-f4a1-4c66-990d-e01960889ebe" />


Rebasons la branche feature sur la branche principale Vérifions l’historique :

<img width="1913" height="677" alt="image" src="https://github.com/user-attachments/assets/77f5061a-5142-42e0-b713-ddd25a9e9c49" />

