[![Made withJupyter](https://img.shields.io/badge/Made%20with-Jupyter-orange?style=for-the-badge&logo=Jupyter)](https://jupyter.org/try)

[![made-for-VSCode](https://img.shields.io/badge/Made%20for-VSCode-1f425f.svg

<h1> Classificazione dei prodotti di Scattering Elettrone-Protone</h1>

Confronto tra diversi modelli di *apprendimento supervisionato* per la *classificazione* di particelle prodotte durante uno scattering inelastico elettrone-protone. L'obiettivo è quello di identificare le particelle e valutare il migliore modello tra i seguenti:

- **Decision Tree**
- **Random Forest**
- **Multilayer Perceptron**
- **K-Nearest Neighbor**

I dati utilizzati sono il prodotto della risposta di sei diversi rilevatori, usanti mediante la piattaforma di simulazione *[GEANT4](https://geant4.web.cern.ch/)*. Il DataSet è reperibile su *[Kaggle](https://www.kaggle.com/datasets/naharrison/particle-identification-from-detector-responses)*.

## **Composizione DataSet**

Le *features* presenti nel dataset utilizzato sono le seguenti:

|    Features    |              Significato              | Unità di Misura |
| :-------------: | :------------------------------------: | :--------------: |
|  **id**  |            Nome Particella            |    $NoDim$    |
|   **p**   |           Quantità di moto           |    $GeV/c$    |
| **theta** |          Angolo di Scattering          |     $rad$     |
| **beta** | Rapporto tra la velocità $v$ e $c$ |    $NoDim$    |
| **nphe** |        Numero di fotoelettroni        |    $NoDim$    |
|  **ein**  |          Energia in ingresso          |     $GeV$     |
| **eout** |           Energia in uscita           |     $GeV$     |

A ciascun *id*  inoltre è associata una precisa particella:

|        id        | Particella |              Simbolo              | Massa (MeV) |
| :--------------: | :--------: | :-------------------------------: | :---------: |
| **(-11)** | Positroni |              $e^+$              |  $0.51$  |
| **(211)** |   Pioni   | $\pi \quad (\pi^0,\pi^+,\pi^-)$ |   $137$   |
| **(321)** |   Kaoni   |     $K \quad (K^0,K^+,K^-)$     |   $495$   |
| **(2212)** |  Protoni  |               $p$               |   $940$   |

Indipendentemente dal modello fisco alla base, ossia il [Modello Standard](https://it.wikipedia.org/wiki/Modello_standard), è sufficiente sapere che ciascuna particella è caratterizzata da un determinato set di valori e in particolare dalla loro *massa a riposo*.

## **Analisi Esplorativa & Preparazione dei Dati**

Per la preparazione preliminare dei dati sono state sfruttate le seguenti librerie:

- Numpy
- MatPlotLib
- Pandas
- Seaborn
- Imbalanced Learn

Inoltre osservazioni fisiche e intuitive hanno permesso di preparare e semplificare ulteriormente il dataset.

Infine prima della costruzione dei modelli di MachineLearning e il loro successivo addestramento è stata effettuata una procedura di **resampling** per correggere il bilanciamento del dataset.

## **Costruzione dei modelli & Addestramento**

Per la scelta dei modelli si è optato per un apprendimento supervisionato, in particolare si sono sfruttati dei *classificatori*. Quest'ultimi, basati sugli algoritmi citati precedentemente, sono offerti dalla libreria **Scikit Learn**:

- DecisionTreeClassifier
- RandomForestClassifier
- MLPClassifier
- KNeighborsClassifier

In particolare per il **RandomForestClassifier** è stata valutata l'*importanza delle features* per l'addestramento del modello, confermando ciò che era stato dedotto nell'analisi esplorativa.

Mentre per **MLPClassifier** si è scelto di effettuare una *ottimizzazione degli iperparametri*, mediante una *GridSearch*.

## **Confronto & Conclusione**

Infine si è utilizzata come metrica per valutare l'efficienza dei modelli, l'*accuracy*  e ,visivamente, delle *matrici di confusione*. I risultati non mostrano una predominanza di un modello rispetto ad un altro, ma il KNeighborsClassifier è il meno efficiente.

|          Classifier          | Accuracy |
| :--------------------------: | :------: |
|   **Decision Tree**   |  89.6%  |
|   **Random Forest**   |  93.2%  |
|   **ML Perceptron**   |  93.1%  |
| **K-Nearest Neighbor** |  88.6%  |

## **Autori**

- [Marco Cecca](https://github.com/marcocecca00) - m.cecca3@studenti.uniba.it
- Giorgia Osella - g.osella@studenti.uniba.it
- Vincenzo Scolletta - v.scolletta1@studenti.uniba.it
