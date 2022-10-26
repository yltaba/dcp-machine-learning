# Projeto 1

Neste projeto, utilizo um modelo classifador Random Forest para prever o presidente que proferiu uma série de 25 discursos.

Como uma parte relevante do projeto é o preprocessamento dos discursos e o `sklearn` ajuda muito nestes pontos (não tendo também muita flexibilidade), optei por focar mais em aprimorar dois modelos diferentes.

Primeiro, apresento um modelo baseline que foi utilizado para tarefa semelhante nos exercícios da aula 5. 

Incrementei este modelo (Gaussian Naive Bayes) com uma etapa de *model tuning* utilizando GridSearchCV para estimar o melhor valor para o parâmetro `var_smoothing`, que ajusta a [porção da maior variância de todas as *features* do modelo que são adicionadas às variâncias para estabilidade no cálculo](https://scikit-learn.org/stable/modules/generated/sklearn.naive_bayes.GaussianNB.html).

Em seguida, apresento um modelo classificador Random Forest também com e sem *model tuning* para os parâmetros `n_estimators`, `max_depth`. `min_samples_split`, `criterion`, [que controlam pontos importantes do modelo](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html), como o número de árvores na floresta (`n_estimators`) e a função que mede a qualidade de uma divisão na árvore (`criterion`).

Este modelo teve performance superior, seguindo a métrica de acuracidade da própria biblioteca `accuracy_score`, e foi validado utilizando *cross validation* com `cross_val_score()`.