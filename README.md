# Classificació de Tipus de Pokémon amb Tècniques d'Apranentatge Computacional

Aquest projecte implementa un flux complet d'anàlisi de dades, preprocessament, entrenament de models de classificació binària i avaluació d'aquests per tal de predir el tipus (o els tipus en cas que sigui possible) dels Pokémon utilitzant diverses tècniques d'Aprenentatge Computacional.

El codi principal es troba al fitxer `main.ipynb`, mentre que les dades originals utilitzades són al fitxer `pokemon.csv`.


## Contingut del projecte
Notebook principal que conté:


### 1. Exploració i neteja de les dades

+ Càrrega del dataset `pokemon.csv`
+ Detecció i tractament de: 
    + valors no numèrics,
    + formes especials com **Minior**,
    + valors faltants (*height* i *weight*)
    + Pokémon sense gènere.
+ Eliminació de columnes no útils (*name*, *japanese_name*, *classification*, *abilities*, etc.)
+ Conversió de totes les característiques en valors numèrics.
+ Engineering d'etiquetes: creació d'una variable objectiu per cada tipus (`is_<type>`).


### 2. Visualització

+ Histograma del recompte de tipus.
+ KDE plots per veure la distribució de les característiques per tipus.
+ Matrius de correlació i *heatmaps*.

### 3. Entrenament i tria de models
+ Es defineix una *grid de paràmetres* específica per a cada classificador per trobar els paràmetres adients per cada tipus de Pokémon.
+ Ús de `GridSearchCV` amb mètrica $F_\beta$ amb $\beta=2$.
+ Selecció del millor model per a cada tipus amb *cross validation* i mininitzant l'*overfitting* amb una tolerància variable depenent del *f2 score* obtingut a validació.

### 4. Agrupament de models
Creació d'una classe `TypeOVA` que ajunta els models de cada tipus per predir el (o els) tipus de Pokèmon donades les *stats*, creant així un classificador *one-vs-all*.

## Dataset: `pokemon.csv`
Conté totes les dades originals dePokémonutilitzades:
+ Estadístiques base (HP, Attack, Defense, etc.)
+ Tipus primari i secundari
+ Habilitat, forma, atura, pes, proporció de gènere, etc.

## Com executar el projecte
1. Col·loca `main.ipynb` i `pokemon.csv` a la mateixa carpeta.
2. Obre el notebook amb Jupyter, VS Code o Google Colab.
3. Executa les cel·les en ordre

## Llibreries utilitzades
+ **Pandas, Numpy**: gestió de dades
+ **Matplotlib, Seaborn**: visualització
+ **Scikit-Learn**: models clàssics i GridSearch
+ **SHAP**:interpretabilitat de models
+ **SciPy**: Funcions auxiliars

## Objectiu del projecte
Construir un sistema capaç de predir el (o els) tipus d’un Pokémon basant-se en les seves estadístiques, característiques físiques i atributs numèrics, així com analitzar quines variables són més importants segons cada tipus.

## Accés al repositori de GIT
Es pot accedir a tot el contingut del projecte a través del següent enllaç: https://github.com/themossen69/pokemon-classification