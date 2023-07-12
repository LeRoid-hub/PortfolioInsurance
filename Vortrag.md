<style> :root {--r-code-font: "FiraCode Nerd Font"; text-align: justify; text-justify: inter-word;} .reveal .hljs {font-size:16px; min-height: 50%;} .table-small{font-size:25px;} .table-big{font-size: 18px;}</style>

## Portfolio Insurance
>von Jan Barfuß

---
## Übersicht
- Allgemein / Wiederholung
- TIPP
- Rainbow Options

---
## Allgemein

---
### Strategien

| Option oder Spot Strategies   | Statische PI            | Dynamische PI                     |
| ----------------------------- | ----------------------- | --------------------------------- |
| *Option Strategien*             | Protective put          | Protective Put with delta hedging |
| Option Duplacating Strategien | Long call, covered call | Long call with delta              |
| Spot Strategien               | *Stop-Loss*               | Synthetic protective put          |
|                               |                         | Synthetic long call               |
|                               |                         | *CPPI*                              |
|                               |                         | *TIPP*                              |
<!-- element class="table-small" -->

nach Agic-Sabeta[^1]

---
### Keine PI Strategien
- Buy and Hold
- Money Management

notes:
- der Kurswert schwankt mit der Marktentwicklung
- keine Mathe def


---
### Leerverkauf / short sale
> Sonderstellung

- kann Leerverkäufer absichern
- per Definition keine PI

notes:
_Beispiel_ X leiht sich eine Aktie von Y - verkauft diese und spekuliert, dass er die später günstiger wiederkaufen kann um diese an Y zurückzugeben.

Da beim Leerverkauf jedoch eine Veräußerung von nicht vorhandenen Vermögenswerten stattfindet, erfüllt er formal nicht die Definition der Wertsicherungsstrategie.

Gamestop

---
Verringern das systematische Risiko eines Portfolios

notes:
heutiger Stand der Wissenschaft -> Verlust von Rendite

---
## TIPP
### *T*ime-*i*nvariant *p*ortfolio *p*rotection

---
### Time-Invariant

Bei Zeitverschiebung ändert sich der Ausgang nicht.

notes:
Ist durch aufzinsung bei CPPI nicht gegeben.

---

### Variablen
$E_{t}$ : Exposure \
$R_{t}$: Risikolose Assets
$m$: risk multiplier  \
$V_{t}$: Portfoliowert \
$F_t$: Floorwert \
$C_{t}$: Cushion \
$\lambda$: propotion of  garantee 

---
### Cushion 
$C_{t} = V_{t} - F_{t}$

notes:
$E_{t}$ : Exposure \
$R_{t}$: Risikolose Assets
$m$: risk multiplier  \
$V_{t}$: Portfoliowert \
$F_t$: Floorwert \
$C_{t}$: Cushion \
$\lambda$: propotion of  garantee 

---
### Exposure
$E_{t} = min(C_{t} * m , V_{t})$

notes:
$E_{t}$ : Exposure \
$R_{t}$: Risikolose Assets
$m$: risk multiplier  \
$V_{t}$: Portfoliowert \
$F_t$: Floorwert \
$C_{t}$: Cushion \
$\lambda$: propotion of  garantee 

---
### Risikolose Assets 
$R_{t} = V_{t} - E_{t}$

notes:
$E_{t}$ : Exposure \
$R_{t}$: Risikolose Assets
$m$: risk multiplier  \
$V_{t}$: Portfoliowert \
$F_t$: Floorwert \
$C_{t}$: Cushion \
$\lambda$: propotion of  garantee 

---
### Portfoliowert 
$V_{t} = E_{t-1} * e^{\textrm{Risiko Anlage }\%} + R_{t-1} * e^{\textrm{Risikofreie Anlage}\%}$


notes:
$E_{t}$ : Exposure \
$R_{t}$: Risikolose Assets
$m$: risk multiplier  \
$V_{t}$: Portfoliowert \
$F_t$: Floorwert \
$C_{t}$: Cushion \
$\lambda$: propotion of  garantee 

---
### Floorberechnung 
$F_{t} = max(F_{t-1}, \lambda V_{t})$

notes:
$E_{t}$ : Exposure \
$R_{t}$: Risikolose Assets
$m$: risk multiplier  \
$V_{t}$: Portfoliowert \
$F_t$: Floorwert \
$C_{t}$: Cushion \
$\lambda$: propotion of  garantee 

---
### Excelvergleich
CPPI 

| Garantiezins | 2%          |                   | Floorstart     | 90          |                   |             |               |
|--------------|-------------|-------------------|----------------|-------------|-------------------|-------------|---------------|
| Anlagezins:  | 2%          |                   | Startkapital   | 100         |                   |             |               |
| Multiplier:  | 2           |                   | Anteil Aktien  | 100%        |                   |             |               |
| Periode      | Floor       | Rendite risikoarm | Rendite Aktien | Cushion     | Exposure (Aktien) | Renten      | Portfoliowert |
| 0            | 90          | 2%                | 10%            | 10          | 20                | 80          | 100           |
| 1            | 91,8        | 2%                | 10%            | 10          | 20                | 80          | 103,6         |
| 2            | 93,636      | 2%                | -2%            | 11,8        | 23,6              | 80          | 104,728       |
| 3            | 95,50872    | 2%                | 5%             | 11,092      | 22,184            | 82,544      | 107,48808     |
| 4            | 97,4188944  | 2%                | 7%             | 11,97936    | 23,95872          | 83,52936    | 110,8357776   |
| 5            | 99,36727229 | 2%                | -8%            | 13,4168832  | 26,8337664        | 84,0020112  | 110,3691165   |
| 6            | 101,3546177 | 2%                | 5%             | 11,00184422 | 22,00368845       | 88,36542806 | 113,2366095   |
| 7            | 103,3817101 | 2%                | 6%             | 11,88199176 | 23,76398352       | 89,47262597 | 116,451901    |
| 8            | 105,4493443 | 2%                | 2%             | 13,07019094 | 26,14038188       | 90,31151915 | 118,780939    |
| 9            | 107,5583312 | 2%                | -1%            | 13,33159476 | 26,66318951       | 92,11774953 | 120,3566621   |
| 10           | 109,7094978 | 2%                | -3%            | 12,79833097 | 25,59666193       | 94,76000021 | 121,4839623   |
<!-- element class="table-big" -->



---
### Excelvergleich
TIPP

| Risk        | 0,85        |                   | Floorstart     | 90          |                   |             |                |
|-------------|-------------|-------------------|----------------|-------------|-------------------|-------------|----------------|
| Anlagezins: | 2%          |                   | Startkapital   | 100         |                   |             |                |
| Multiplier: | 2           |                   | Anteil Aktien  | 100%        |                   |             |                |
| Periode     | Floor       | Rendite risikoarm | Rendite Aktien | Cushion     | Exposure (Aktien) | Renten      | Portfolio-wert |
| 0           | 90          | 2%                | 10%            | 10          | 20                | 80          | 100            |
| 1           | 90          | 2%                | 10%            | 10          | 20                | 80          | 103,6          |
| 2           | 90          | 2%                | -2%            | 13,6        | 27,2              | 76,4        | 104,584        |
| 3           | 91,418112   | 2%                | 5%             | 14,584      | 29,168            | 75,416      | 107,55072      |
| 4           | 94,61774592 | 2%                | 7%             | 16,132608   | 32,265216         | 75,285504   | 111,3149952    |
| 5           | 94,61774592 | 2%                | -8%            | 16,69724928 | 33,39449856       | 77,92049664 | 110,2018452    |
| 6           | 96,3397889  | 2%                | 5%             | 15,58409933 | 31,16819866       | 79,03364659 | 113,3409281    |
| 7           | 99,42266214 | 2%                | 6%             | 17,00113922 | 34,00227843       | 79,33864968 | 116,9678378    |
| 8           | 103,2007233 | 2%                | 8%             | 17,54517567 | 35,09035134       | 81,87748647 | 121,4126156    |
| 9           | 104,3359313 | 2%                | -1%            | 18,21189235 | 36,42378469       | 84,98883095 | 122,7481544    |
| 10          | 104,8576109 | 2%                | -3%            | 18,41222316 | 36,82444633       | 85,92370809 | 123,3618952    |
<!-- element class="table-big" -->

---
### Floorberechnung 
$F_{t} = max(F_{t-1}, \lambda V_{t})$

notes:
$E_{t}$ : Exposure \
$R_{t}$: Risikolose Assets
$m$: risk multiplier  \
$V_{t}$: Portfoliowert \
$F_t$: Floorwert \
$C_{t}$: Cushion \
$\lambda$: propotion of  garantee 

---
### Riskfaktor bestimmen


![[TIPPBestRisk.jpg]]

--
### Mean

![[TIPPBestMean.jpg]]

---
### Multipier bestimmen

![[TIPPBestMulti.jpg]]

---

<canvas data-chart="line" >
<!--
{
 "data": {
  "labels": ["0"," 1"," 2"," 3"," 4"," 5"," 6","7","8","9","10"],
  "datasets":[
   {
    "data":[90,90,90,91.418112,94.61774592,94.61774592,96.3397889,99.42266214,103.2007233,104.3359313,104.8576109],
    "label":"Floor","backgroundColor":"rgba(20,220,220,.8)"
   },
   {
    "data":[80,80,76.4,75.416,75.285504,77.92049664,79.03364659,79.33864968,81.87748647,84.98883095,85.92370809],
    "label":"Renten","backgroundColor":"rgba(220,220,120,.8)"
   },
   {
    "data":[20,20,27.2,29.168,32.265216,33.39449856,31.16819866,34.00227843,35.09035134,36.42378469,36.82444633],
    "label":"Exposure","backgroundColor":"rgba(110,120,120,.8)"
   },
   {
    "data":[100,103.6,104.584,107.55072,111.3149952,110.2018452,113.3409281,116.9678378,121.4126156,122.7481544,123.3618952],
    "label":"Portfoliowert","backgroundColor":"rgba(220,120,120,.8)"
   }
  ]
 }
}
-->
</canvas>

---
### Simulation

Historischen Daten & Bootstrap

---
### Datensatz
DAX & RAX 1997 - 2007

notes:
Yahoo finance

DAX als Risiko Asset
REX als Risikoloses Asset

REX - Deutsche staatsanleihen

---
### Rendite

$\textrm{ln(Alt Portfoliowert)}-\textrm{ln(Neu Portfoliowert)}$

notes:
natürlicher Logarithmus

---
### Risikoeigenschaften

Rendite: 0,64%

Standartabweichung: 0,15%

---

![[TIPPBoot10000.jpg]]

---
### Mögliche Verbesserungen
Dynamischer Multiplikator  Yao,Li[^2]

---
### TODO

- Mit besseren Daten durchführen
- Graph mit Kursverlauf

---

## Option Strategien

### Rainbow options[^3]

notes:
exotic option
OTC

---

Jedes Asset ist eine Farbe des Regenbogens.


notes:
Ähnlich zu einer Basket open.

---
### Arten
- best/worst-of-n
- spread
- correlation

---
### Payoff

- Best of assets or cash option
- Call on max option
- Call on min option
- Put on max option
- Put on min option
- Put X and call Y

notes:
-   _Best of assets or cash_ option, delivering the maximum of two risky assets and cash at expiry
-   _Call on max_ option, giving the holder the right to purchase the maximum asset at the strike price at expiry
-   _Call on min_ option, giving the holder the right to purchase the minimum asset at the strike price at expiry
-   _Put on max_ option, giving the holder the right to sell the maximum of the risky assets at the strike price at expiry
-   _Put on min_ option, giving the holder the right to sell the minimum of the risky assets at the strike at expiry
-   _Put 2 and call 1_, an exchange option to put a predefined risky asset and call the other risky asset. Thus, asset 1 is called with the 'strike' being asset 2.


--

-   Best of assets or cash: max(S1,S2,...,Sn,K)
-   Call on max: max(max(S1,S2,...,Sn)−K,0)
-   Call on min: max(min(S1,S2,...,Sn)−K,0)
-   Put on max: max(K−max(S1,S2,...,Sn),0)
-   Put on min: max(K−min(S1,S2,...,Sn),0)
-   Put 2 and Call 1: max(S1−S2,0)

nach Wikipedia[^4]

---
### Call on max
max(max(S1,S2,...,Sn)−K,0)

---
### Rendite
max(max(S1,S2,...,Sn)−K,0) - Prämie

---
### MC Simulation

notes:
Ähnliche Sim wie Basket die Auszahl. abgeändert.

---

### Risikoeigenschaften

Rendite = 6,8695 %

Standartabweichung = 31,17

notes:
bei Opt Preis 

---

![[Rainbow.jpg]]

---
### Mögliche Verbesserungen
- Floor


---
### TODO
Zusammenhang Parameter - Rendite & Risiken 

notes:
- Correlationsmatrix
- Subperioden
- Laufzeit


---
## Foliensatz

![[frame.png]]

https://github.com/LeRoid-hub/PortfolioInsurance
---

## Quellen:

[^1]: [[Agic-Sabeta]] UTMS Journal of Economics Vol. 8, Iss. 2, pp. 91-104, Portfolio insurance investment strategies: A riskmanagement tool
[^2]:[[Yao, Li]]  European Journal of Research and Reflection in Management Sciences Vol. 4 No. 2, 2016 p60, PORTFOLIO INSURANCE WITH A DYNAMIC RISK MULTIPLIER BASED ON PRICE FLUCTUATION
[^3]:[[Lucas Downey]] https://www.investopedia.com/terms/r/rainbowoption.asp#
[^4]:Wikipedia, https://en.wikipedia.org/wiki/Rainbow_option 05.07.2023
