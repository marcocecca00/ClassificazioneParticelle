# **Classificazione dei prodotti di Scattering Elettrone-Protone**

Confronto tra diversi modelli di *apprendimento supervisionato* per la *classificazione* di particelle prodotte durante uno scattering inelastico elettrone-protone basato sulla risposta di sei diversi rilevatori. L'obiettivo è quello di identificare le particelle e valutare il migliore modello tra i seguenti:

- **Decision Tree**
- **Random Forest**
- **Multilayer Perceptron**

I dati utilizzati sono il prodotto della risposta di sei diversi rilevatori mediante la piattaforma di simulazione *[GEANT4](https://geant4.web.cern.ch/)*. Il DataSet è reperibile su *[Kaggle](https://www.kaggle.com/datasets/naharrison/particle-identification-from-detector-responses)*.


## **Composizione DataSet**

|    Features    |              Significato              | Unità di Misura |
| :-------------: | :------------------------------------: | :--------------: |
|  **id**  |            Nome Particella            |    $NoDim$    |
|   **p**   |           Quantità di moto           |    $GeV/c$    |
| **theta** |          Angolo di Scattering          |     $rad$     |
| **beta** | Rapporto tra la velocità$v$ e $c$ |    $NoDim$    |
| **nphe** |        Numero di fotoelettroni        |    $NoDim$    |
|  **ein**  |          Energia in ingresso          |     $GeV$     |
| **eout** |           Energia in uscita           |     $GeV$     |

\
**Valore Particelle**
|        id        | Particella |              Simbolo              | Massa (MeV)
| :--------------: | :--------: | :-------------------------------: | :-----:
| **(-11)** | Positroni |              $e^+$              | $0.51$
| **(211)** |   Pioni   | $\pi \quad (\pi^0,\pi^+,\pi^-)$ | $133$
| **(321)** |   Kaoni   |     $K \quad (K^0,K^+,K^-)$     | $495$
| **(2212)** |  Protoni  |               $p$               | $940$
