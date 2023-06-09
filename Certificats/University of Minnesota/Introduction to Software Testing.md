# Semaine 1
## Introduction
### Pourquoi?
Parce que le coût d'un test en bien inférieur au coût d'une perte de données, de clients, un piratage ou autres... Par exemple, en 2016, on calcule 1.1 trillion de dollars en coût annuel causé par un manque de tests. 

### C'est quoi?
Cela consiste assurer que le logiciel rencontre les besoins de l'utilisateur en usant de la vérification et de la validation:
- Verification: Est-ce que nous faisons le produit comme il doit être? Est-ce que nous nous conformons aux spécifications?
- Validation: Est-ce que nous faisons le bon produit? Est-ce qu'il répond vraiment au besoin de l'utilisateur?

#### Faire le bon logiciel
1. Comprendre ce que fait le logiciel et aussi ce qu'il devrait faire
2. Nécessité d'appliquer plusieurs V&V techniques tout au long du développement
    - Inspections
    - Discussions sur le design
    - Analyse statique 
    - Testing
    - Vérification runtime

### Pourquoi focus sur les tests logiciels
- Parce que c'est la seule facon de vraiment vérifier tout le système pour trouver des bugs (compiler, processor, devices, network, linker, loader...)
- Parce qu'il s'agit de la meilleure manière de vérifier certains comportements (performances)
- Meilleure facon de bien documenter la facon dont fonctionne le système

Notez que tester, reste malgré tout incomplet, mais on peut au moins le rendre utile

### Analysis Square
![](https://github.com/joshuavachon25/notes/blob/main/analysis_square.png)

## Pourquoi et comment tester?
### Pourquoi les tests logiciels sont si difficiles?
La plupart des logiciels sont discontinues, ce qui fait qu'on tests en fait un échantillon de tous les comportements possibles. Par exemple, en ingénérie, pour tester une poutre, il serait possible d'appliquer de plus en plus de force jusqu'à obtenir une mesure précise de la force nécessaire pour briser celle-ci. Pour les logiciels, on ne peut pas seulement augmenter la charge, il faut vraiment faire des tests très distincts pour parvenir à vérifier le fonctionnement. On peut imaginer notre système comme une toile sur laquelle les programmeurs mettent sans le vouloir des petits insectes. Pour vérifier qu'il n'y a pas d'insecte, il faut faire une panoplie de tests en espérant tombé sur un insecte. Lorsque nous avons terminé, nous n'avons pas la certitude d'avoir tous les insectes... Si on sait qu'en rajoutant du poids, nous aurons un problème avec le pont; le fait de tester ne permet pas de dire qu'il ajouter ou supprimer quelques choses pour trouver un bug.

Même pour un petit système, il peut y avoir des millions d'états possibles... C'est donc impossible de tout tester!

![image](https://github.com/joshuavachon25/notes/assets/46571227/4cdc26f1-91fb-46bb-b09d-f732ca3f89d7)

### Types de tests
#### Échelles
- Unit: Tests sur des fonctions spécifiques
- Integration: Test d'une package, d'un sous-système
- System: E2E

#### Processus
- Test first: Test driven development (TDD)
    - Tests avant le code
    - Code est écrit pour répondre au test
- Test after
    - Vérifier que le code passe les tests
    - TDD demandent aussi du test after
- Iteration
    - Re-tester

#### Buts
- Functionnal
- Performance
- Security
- Usability
- Availability

## Qu'est-ce qu'un test?
Un élément permettant de vérifier le comportement/réation d'un bout de code terminé. 
- Software under Test
   - Demande des données de tests (générées ou non)
   - Vérifier que l'output fonctionne grâce à l'Oracle (par le passé: testeur manuel)
   - TestData => Software under test => Output => Oracle => Success or Fail?

![image](https://github.com/joshuavachon25/notes/assets/46571227/d25dc87b-bf8c-48d3-b9be-ecf4e05c2e29)

### Anatomie d'un test
- Setup: Préparation du contexte du test
- Invocation: Exécution d'un test à partir de données
- Assessment: Vérifier le succès ou l'échec
- Teardown: Remise à l'état initial

## Qu'est-ce qu'une suite de test?
### Exemple
- Le nom de la classe de test est la classe de test + Test (ClasseTest)
- Chaque test doit avoir au moins une assertion
- JUnit fait tous les tests, il n'arrête pas lors d'un fail
- Prioriser le test de petites méthodes au lieu de tout le code
- Les tests unitaires doivent être comprehensive 

### Exemple de TDD
- JUnit commence avec l'annotation @Test
- Ensuite une fonction avec le nom du test
- On veut rediriger l'entrée et la sortie dans nos tests
