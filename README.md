# Atelier PyTorch · Deep Learning IndabaX RDC 2026

**Intelligence artificielle et langues congolaises : construire des ressources numériques ouvertes**
Université Nouveaux Horizons (UNH), Lubumbashi · 26 au 28 novembre 2026

Ce dépôt contient le matériel de l'atelier PyTorch de l'IndabaX RDC 2026.
Les notebooks suivent les tutoriels officiels de PyTorch. Ils sont en français, avec des schémas et des exercices.
Tout fonctionne dans **Google Colab**, avec le GPU gratuit (NVIDIA T4). Vous n'avez rien à installer.

*English: PyTorch workshop material for Deep Learning IndabaX DRC 2026 (Lubumbashi). The notebooks are in French and follow the official PyTorch "Learn the Basics" tutorials. They run on free Google Colab.*

## Les notebooks

| Jour | Notebook | Contenu | Ouvrir |
|---|---|---|---|
| Jour 1 (26 nov.) | [`Jour1_Introduction_PyTorch.ipynb`](notebooks/Jour1_Introduction_PyTorch.ipynb) | Tenseurs, GPU, autograd, données, modèle, boucle d'entraînement, sauvegarde, pont vers les modèles de langage | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ganji759/IndabaX-DRC-2026-PyTorch-Workshop/blob/main/notebooks/Jour1_Introduction_PyTorch.ipynb) |
| Jour 2 (27 nov.) | [`Jour2_Finetuning_LoRA.ipynb`](notebooks/Jour2_Finetuning_LoRA.ipynb) | Fine-tuning LoRA d'un petit modèle de langage (Qwen2.5-0.5B) sur des instructions en swahili, comparaison avant/après, sauvegarde, déploiement avec ExecuTorch. Session de 30 minutes. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ganji759/IndabaX-DRC-2026-PyTorch-Workshop/blob/main/notebooks/Jour2_Finetuning_LoRA.ipynb) |

## Jour 1 : Introduction à PyTorch

![Carte de l'atelier du jour 1](images/01_carte_atelier.png)

| Partie | Sujet | Durée indicative | Tutoriel officiel |
|---|---|---|---|
| 0 | Mise en place de Colab | 5 min | - |
| 1 | Les tenseurs | 15 min | [Tensors](https://docs.pytorch.org/tutorials/beginner/basics/tensorqs_tutorial.html) |
| 2 | Le GPU | 5 min | [Tensors](https://docs.pytorch.org/tutorials/beginner/basics/tensorqs_tutorial.html) |
| 3 | Autograd et descente de gradient | 15 min | [Autograd](https://docs.pytorch.org/tutorials/beginner/basics/autogradqs_tutorial.html) |
| 4 | Les données (FashionMNIST) | 10 min | [Datasets & DataLoaders](https://docs.pytorch.org/tutorials/beginner/basics/data_tutorial.html) |
| 5 | Construire le modèle | 10 min | [Build Model](https://docs.pytorch.org/tutorials/beginner/basics/buildmodel_tutorial.html) |
| 6 | La boucle d'entraînement | 15 min | [Optimization](https://docs.pytorch.org/tutorials/beginner/basics/optimization_tutorial.html) |
| 7 | Sauvegarder et charger | 5 min | [Save & Load](https://docs.pytorch.org/tutorials/beginner/basics/saveloadrun_tutorial.html) |
| 8 | Pont vers le Jour 2 : tokenizer, `nn.Embedding`, mini modèle de langage en swahili | 10 min | - |

Le notebook contient 3 exercices avec leurs solutions (cliquez sur « Voir la solution ») et 4 exercices bonus.

## Jour 2 : adapter un petit modèle de langage au swahili avec LoRA (30 minutes)

![Les étapes du jour 2](images/11_jour2_parcours.png)

| Partie | Sujet | Durée |
|---|---|---|
| 0 | Mise en place (GPU T4, installation de `peft`) | 3 min |
| 1 | Le modèle pré-entraîné `Qwen2.5-0.5B-Instruct` et les réponses « avant » | 5 min |
| 2 | Les données : 1 000 conversations en swahili, chat template, labels | 4 min |
| 3 | LoRA : on gèle `W`, on apprend `A` et `B` | 5 min |
| 4 | L'entraînement : la même boucle qu'au Jour 1, avec la précision mixte | 7 min |
| 5 | Les réponses « après » et la comparaison | 3 min |
| 6 | Sauvegarder (adaptateur, modèle fusionné) et déployer avec ExecuTorch | 3 min |

**Conseil :** activez le GPU T4, puis lancez **Exécution → Tout exécuter** au début. Le notebook tourne pendant les explications.

Données : [`regnant-io/swahili-instruction-22k`](https://huggingface.co/datasets/regnant-io/swahili-instruction-22k) (Apache-2.0, traduit automatiquement de l'anglais).
Modèle : [`Qwen/Qwen2.5-0.5B-Instruct`](https://huggingface.co/Qwen/Qwen2.5-0.5B-Instruct) (Apache-2.0).

## Comment commencer

1. Cliquez sur le badge **Open in Colab** ci-dessus.
2. Connectez-vous avec votre compte Google.
3. Menu **Exécution → Modifier le type d'exécution** → **GPU T4** → **Enregistrer**.
4. Exécutez les cellules dans l'ordre avec **Maj + Entrée**.

**Prérequis :** des bases de Python. Un compte Google. Aucun compte Hugging Face n'est nécessaire.

**Travail en équipe :** le GPU gratuit de Colab n'est pas garanti. Travaillez par équipes de 2 ou 3. Un GPU par équipe suffit. Sans GPU, le notebook fonctionne aussi sur CPU, plus lentement.

## Contenu du dépôt

```
notebooks/            les notebooks de l'atelier
images/               les schémas (PNG) utilisés dans les notebooks
images/excalidraw/    les sources des schémas (.excalidraw)
```

Pour modifier un schéma : ouvrez [excalidraw.com](https://excalidraw.com), puis **Ouvrir** le fichier `.excalidraw`.

## Ressources officielles

- [PyTorch : Learn the Basics](https://docs.pytorch.org/tutorials/beginner/basics/intro.html)
- [Deep Learning with PyTorch: A 60 Minute Blitz](https://docs.pytorch.org/tutorials/beginner/deep_learning_60min_blitz.html)
- [Documentation de PyTorch](https://docs.pytorch.org/docs/stable/index.html)
- [Forum PyTorch](https://discuss.pytorch.org/)

## Crédits et licence

- Les notebooks adaptent les tutoriels [PyTorch Learn the Basics](https://github.com/pytorch/tutorials/tree/main/beginner_source/basics) (licence BSD-3-Clause, © Pytorch contributors).
- Données : [FashionMNIST](https://github.com/zalandoresearch/fashion-mnist) (Zalando Research, licence MIT).
- Tokenizer de démonstration : [`HuggingFaceTB/SmolLM2-135M-Instruct`](https://huggingface.co/HuggingFaceTB/SmolLM2-135M-Instruct) (licence Apache-2.0).
- Schémas faits avec [Excalidraw](https://excalidraw.com).

Ce dépôt est sous licence [BSD-3-Clause](LICENSE).
