**Étape 1 : Initialiser Git dans mlops-lab-01**

**Objectif** : Placer le projet MLOps sous contrôle de version Git pour suivre les modifications, collaborer et assurer la reproductibilité.

Initialiser le dépôt Git et  Vérifier l’état du 

dépôt :

![1.png](attachment:1ff39211-6029-45d8-871e-d910c0e07539:1.png)

**Étape 2 : Premier commit du projet** 
**Objectif** : Voir comment Git suit les changements dans les fichiers de travail et comment utiliser les outils de staging (`git diff` et `git diff --staged`).

**MLOps**Créer le premier commit :

![2.png](attachment:67840b8e-8a9a-43b9-a247-28de0d9c112d:2.png)

Afficher l’historique :

![3.png](attachment:173dc037-6b3e-4aeb-ab2b-c0a4731d9457:3.png)

**Étape 3 : Observer une modification avec git diff**

**Objectif** : Simuler un développement de nouvelle fonctionnalité en utilisant une branche Git isolée pour éviter de casser la branche principale (`master`).

Afficher les différences par rapport au dernier commit 

![4.png](attachment:3c81585c-ee7b-4e77-8d0e-e7f39de7f82d:4.png)

Ajouter le fichier modifié à l’index et  Afficher les différences en staging :

![5.png](attachment:399f09bd-87a5-42a2-96db-6f2070161e1a:5.png)

Créer un commit :

![6.png](attachment:347b9ab6-e1ec-46b4-a7af-c9034ac21e26:613629cd-e19d-44e1-abb7-3aa261c922e6.png)

**Étape 4 : Créer une branche de fonctionnalité liée au lab:**

**Objectif** : Intégrer la fonctionnalité développée et testée sur la branche isolée  dans la branche de base (`master`)

Créer une branche Ajouter et committer puis aficher Lister les branches  et puis Revenir sur la branche principale :

![image.png](attachment:b035aaa0-7d12-4e09-a9df-26cc6868ccbb:7a6727d6-4d0c-47a8-ad88-82ceadd46c9f.png)

**Étape 5 : Fusionner la branche feature dans la branche principale**

**Objectif** : Apprendre à gérer un scénario courant de collaboration où deux branches modifient la même partie du même fichier, entraînant un conflit de fusion

Fusionner la branche 

![image.png](attachment:e45b52bc-7f69-4ec1-800f-e7e14eb1fefb:051e8164-6b06-42ac-95b9-71fd6e661400.png)

Vérifier l’historique :

![7.png](attachment:f1ff5a0a-ac93-4340-a0cd-dd1ee2916d5e:7.png)

**Étape 6 : Créer un conflit de merge sur src/train.py**

Créer une nouvelle branche Modifier `src/train.py`  puuis Ajouter et committer :

![8.png](attachment:d5fce927-5709-4cc4-8f98-fb6d1f1b07d1:8.png)

Revenir sur la branche principale puis Modifier la même ligne dans `src/train.py` puis Ajouter et committer  :

![9.png](attachment:08870e27-2e2e-4dd4-b5a5-e2ccecef76e2:9.png)

Tenter la fusion  il y’a un conflit alors Résoudre le conflit :

![image.png](attachment:a7e002e3-ee78-4cee-aa41-3f154852685b:e186ed4d-95ca-49b7-9206-a715d40f5bed.png)

**Étape 7 : Utiliser git stash dans le contexte du lab**

Modifier un fichier sans vouloir committer (src/rollback.py) et Afficher l’état :

![10.png](attachment:1bae95d1-1bad-4920-a70a-52c786d0e03b:10.png)

Mettre de côté les modifications et Lister les stash  et Récupérer les modifications :

![11.png](attachment:ba1253e6-7565-4605-827f-b8dd5c2ed32d:11.png)

![12.png](attachment:fbe6b05a-3770-4eb6-9715-6ef3d768f533:12.png)

**Étape 8 : Tester git reset sur un fichier d’expérimentation**

Créer un dossier d’expérimentation et Créons un fichier de test:

![13.png](attachment:9b5393e3-bed0-491d-8cf9-366a75408524:fbc18a1a-4544-4ee4-b8f8-178817b3b332.png)

Modifier puis committer deux fois :

![image.png](attachment:b5160779-9708-4373-b754-34e69e7a615b:44790aea-259e-46d7-8f37-66b694501f85.png)

![14.png](attachment:10962103-fac3-43ef-b033-407f6325f82e:06c52251-829b-4489-b813-106415844d16.png)

Effectuer un reset soft :

![image.png](attachment:64c7ad86-52ac-450e-89f7-10d5bb634468:de28b912-77d8-46dc-9ebc-d3c9220b692e.png)

Effectuer un reset mixed puis un reset hard :

![15.png](attachment:77ffe65a-b38f-4cbc-9b46-fbbcd4f29573:15.png)

**Étape 9 : Annuler un commit avec git revert**

Ajouter un changement non souhaité dans `src/api.py` puis on a Lister les commits  et on a fait Revert du dernier commit :

![16.png](attachment:878d5bab-11ab-4581-9bd0-2133edfb867c:16.png)

on Vérifie le contenu du fichier :

![17.png](attachment:55c158a1-6077-41ea-a199-e5bef3da3bd6:17.png)

**Étape 10 : Rebase d’une branche feature sur la branche principale**

Créons une branche et Modifions`src/monitor_drift.py` pui on Ajout et commit:

![18.png](attachment:c31932e3-7187-4c55-808f-54b58692bd86:108a3600-6f39-4943-8155-c8890815b0fe.png)

 

Revenir sur la branche principale et créons un nouveau commit sur un autre fichier (par exemple `src/generate_data.py`)  puis Revenons sur la branche feature : 

![image.png](attachment:16c3355a-7a67-45b8-8206-786b793d1690:91132abd-6134-49e6-afe3-8b064eb96e29.png)

Rebasons la branche feature sur la branche principale Vérifions l’historique :

![image.png](attachment:db1daa27-d2ca-4944-b3b8-74f425166993:3a1141d3-0858-4afc-ae2c-6c71daa2d188.png)
