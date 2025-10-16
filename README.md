# README Évalution

Pipeline CI/CD :


## Push sur la branche main et lors de la Pull request : 

on:
  push:
    branches:
      - main

## Lors de la Pull request :

Lance Jobs

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

## Lexique et explication

runs-on: ubuntu-latest -> Fait le test sur ubuntu

needs: [build-exemple] -> à besoin du jobs précédent nommé "build-exemple"

steps: -> Les étapes a réalisé lors de l'exécution
