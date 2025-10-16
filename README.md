# README Évalution

Pipeline CI/CD :


## Push sur la branche main et lors de la Pull request : 

```bash

on:
  push:
    branches:
      - main
```

## Lors de la Pull request :

Lance Jobs

```bash

jobs:
  build-exemple:
    name: Build | Afficher le nom de l'utilisateur
    runs-on: ubuntu-latest
    steps:
      - name: Echo user login
        run: echo "Hello, ${{ github.actor }}"

  test:
    name: Test | Exécution
    runs-on: ubuntu-latest
    needs: [build-exemple]
    steps:
      - name: Test
        run: echo "Test effectué depuis la branche ${{ github.ref_name }}"

```

## Lexique et explication

runs-on: ubuntu-latest -> Fait le test sur ubuntu

needs: [build-exemple] -> à besoin du jobs précédent nommé "build-exemple"

steps: -> Les étapes a réalisé lors du respect des exigences précédentes


---

## 💡 Mes contributions GitHub | My GitHub Contributions

<p align="center">
  <img src="https://ghchart.rshah.org/ff3434/Alexandre-git-SDV" alt="Alexandre's Github contribution graph" />
</p>

---