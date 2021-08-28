# Crop yield predection project
<img src="https://raw.githubusercontent.com/Hamid-abdellaoui/crop-yield-predection/main/nb_bg.png"/>

Ce projet s'inscrit dans le cadre d'un satge
  <br>


## Contenue du [nootebook](https://github.com/Hamid-abdellaoui/crop-yield-predection/blob/main/croprediction.ipynb) :
  > * ##### 1. Data preparation & exploration <space><space>
  > * ##### 2. Prediction des Temperatures  <space><space>
   >>> * ###### SARIMA <space><space><space><space>
  > * ##### 3. Prediction des précipétations <space><space>
   >>>  * ###### ARIMA <space><space><space><space>
   >>>  * ###### LSTM <space><space><space><space>
  > * ##### 4. prédiction du rendement agricole <space><space>
   >>> * ###### Vector auto-regressive model - VAR <space><space><space><space>
   >>> * ###### Multiple linear regression <space><space><space><space>
  




## Théories derière les modèles et les techniques utilisés
  
### <font color='#03d7fc' size=5>▶ Regression Linéaire </font>
La régression linéaire multiple fait référence à une technique statistique qui utilise deux ou plusieurs variables indépendantes pour prédire le résultat d'une variable dépendante.
La technique permet aux analystes de déterminer la variation du modèle et la contribution relative de chaque variable indépendante dans la variance totale.
La régression multiple peut prendre deux formes, c'est-à-dire la régression linéaire et la régression non linéaire. <br>
<img src='https://cdn.corporatefinanceinstitute.com/assets/multiple-linear-regression1-600x67.png' width=400/> <br>

  
  
### <font color='#03d7fc' size=5>▶ Modèle Auto-Régressif (AR)</font>
Les modèles auto-régressifs fonctionnent en partant du principe que les valeurs passées ont un effet sur les valeurs actuelles. Les modèles AR sont couramment utilisés pour analyser la nature, l’économie et d’autres processus variables dans le temps. Tant que l’hypothèse tient, nous pouvons construire un modèle de régression linéaire qui tente de prédire aujourd’hui la valeur d’une variable dépendante, compte tenu des valeurs qu’elle avait les jours précédents. <br>
<img src='https://assets.moncoachdata.com/v7/moncoachdata.com/wp-content/uploads/2020/01/modele-ar.png?w=400'/> <br>

### <font color='#03d7fc' size=5>▶ Modèle de la Moyenne Mobile (MA)</font>
Supposez que la valeur de la variable dépendante du jour en cours dépend des termes d’erreur des jours précédents. La formule peut être exprimée sous cette forme :<br>
<img src='https://assets.moncoachdata.com/v7/moncoachdata.com/wp-content/uploads/2020/01/modele-moyenne-mobile-formule1.png?w=400'/> <br>
où μ est la moyenne de la série, les θ1, …, θq sont les paramètres du modèle et les εt, εt-1,…, εt-q sont les termes d’erreur de bruit. La valeur de q est appelée l’ordre du modèle MA. <br>
### <font color='#03d7fc' size=5>▶ Modèle de la Moyenne Mobile Auto-Régressive (ARMA)</font>
Le modèle ARMA est simplement la combinaison des 2 précédents modèles AR et MA : <br>
<img src='https://assets.moncoachdata.com/v7/moncoachdata.com/wp-content/uploads/2020/01/formule-modele-arma.png?w=400'/> <br>
### <font color='#03d7fc' size=5>▶ Modèle de la Moyenne Mobile Auto-Régressive Intégrée (ARIMA) </font>
Le modèle ARIMA ajoute une différence à un modèle ARMA. La différenciation soustrait la valeur actuelle de la précédente et peut être utilisée pour transformer une série temporelle en une série stationnaire. Par exemple, la différenciation du premier ordre traite des tendances linéaires et utilise la transformation zi = yi – yi-1. <br>
La différenciation du second ordre traite des tendances quadratiques et utilise une différence du premier ordre sur une différence du premier ordre, à savoir zi = (yi – yi-1) – (yi-1 – yi-2), et ainsi de suite. <br>

Trois entiers (p, d, q) sont généralement utilisés pour paramétrer les modèles ARIMA : <br>
<b>
* p : nombre de termes autorégressifs (ordre AR) 
* d : nombre de différences non saisonnières (ordre de différenciation)
* q : nombre de termes moyens mobiles (ordre MA)</b>
 <br>

### <font color='#03d7fc' size=5> ▶ Modèle SARIMA: Seasonal ARIMA </font><br>
SARIMA: Seasonal ARIMA ou ARIMA saisonnier est une extension du modèle ARIMA. <br>
<img src='https://miro.medium.com/max/1400/0*hTDJbnnbhS3SDJvc.png' width=400/> <br>
Il permet de modéliser les séries temporelles comportant une composante saisonnière et désigné par 7 paramètres : <br>
<b>
* p, d, q : les même que ceux de ARIMA.
* P : ordre de la partie autorégressive saisonnière.
* D : ordre de la différence saisonnière.
* Q : ordre de la moyenne mobile saisonnière.
* m : la période de la composante saisonnière. <b> <br>


<img src='https://i.stack.imgur.com/NUA6V.png'  width=400/>
<br><br>
<br>
  
  
### <font color='#03d7fc' size=5>▶ Modèle vector Auto-Regression (VAR)</font>
Dans le modèle VAR, chaque variable est modélisée comme une combinaison linéaire de valeurs passées d'elle-même et des valeurs passées d'autres variables du système . Étant donné que vous avez plusieurs séries temporelles qui s'influencent mutuellement, elles sont modélisées comme un système d'équations avec une équation par variable (série temporelle).
  <br>
Par exemple, le système d'équations d'un modèle VAR(1) avec deux séries temporelles (variables « Y1 » et « Y2 ») est le suivant :
  <p><img src='https://www.machinelearningplus.com/wp-content/uploads/2019/07/Equation_VAR1_Model-min.png?ezimgfmt=ng:webp/ngcb4'  width=400/></p>

 <br>
 
  
### Réferences :
#### - Data ressources : <a href="https://meteostat.net/fr/place/MA-ESIT?t=2021-08-16/2021-08-22">Meteostat </a>
