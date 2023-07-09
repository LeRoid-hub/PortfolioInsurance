<style> :root {--r-code-font: "FiraCode Nerd Font";} .reveal .hljs {min-height: 50%;} </style>

## Portfolio Insurance
>von Jan Ole Barfuß

---
## Übersicht
- Allgemein / Wiederholung
- TIPP
- Rainbow options
- Auswertung

---
## Allgemein

---
### Strategien

| Statistische PI           | dynamische PI |
| ------------------------- | ------------- |
| Stop-Loss                 | TIPP          |
| Protective Puts und Calls | CPPI          |
|                           | dynamische Replikation             |

---
### Keine PI Stragtegien
- Buy and Hold
- Money Management


---
### Leerverkauf / short sale
> Sonderstellung

- kann Leerverkäufer absichern
- per Definition keine PI

notes:
_Beispielsweise_ kann ein Agrarprodukt im Leerverkauf veräußert werden, um den Leerverkäufer vor sinkenden Agrarpreisen zu schützen.

Da beim Leerverkauf jedoch eine Veräußerung von nicht vorhandenen Vermögenswerten stattfindet, erfüllt er formal nicht die Definition der Wertsicherungsstrategie.

---
Verringern das systematische Risiko eines Portfolios

notes:
heutiger Stand der Wissenschaft -> Verlust von Rendite

---
## TIPP
### *T*ime-*i*nvariant *p*ortfolio *p*rotection

---

### Variablen
$E_{t}$ : value of risky asset at time t 
$m$: risk multiplier 
$V_{t}$: Portfoliowert 
$F_t$ Floorwert
$C_{t}$: Cushion
$\lambda$: propotion of  garantee   

---
### Floorberechnung 
$F_{t} = max(F_{t-1}, \lambda V_{t})$

---
### Excelvergleich
CPPI 

![[Pasted image 20230709133256.png]]
notes:

::: block <!-- element style="width: 1%" -->

| Einstiegsbeispiel CPPI |             |                   |                |             |                   |             |               |
| ---------------------- | ----------- | ----------------- | -------------- | ----------- | ----------------- | ----------- | ------------- |
|                        |             |                   |                |             |                   |             |               |
| Garantiezins           | 2%          |                   | Floorstart     | 90          |                   |             |               |
| Anlagezins:            | 2%          |                   | Startkapital   | 100         |                   |             |               |
| Multiplier:            | 2           |                   | Anteil Aktien  | 100%        |                   |             |               |
| Periode                | Floor       | Rendite risikoarm | Rendite Aktien | Cushion     | Exposure (Aktien) | Renten      | Portfoliowert |
| 0                      | 90          | 2%                | 10%            | 10          | 20                | 80          | 100           |
| 1                      | 91,8        | 2%                | 10%            | 10          | 20                | 80          | 103,6         |
| 2                      | 93,636      | 2%                | -2%            | 11,8        | 23,6              | 80          | 104,728       |
| 3                      | 95,50872    | 2%                | 5%             | 11,092      | 22,184            | 82,544      | 107,48808     |
| 4                      | 97,4188944  | 2%                | 7%             | 11,97936    | 23,95872          | 83,52936    | 110,8357776   |
| 5                      | 99,36727229 | 2%                | -8%            | 13,4168832  | 26,8337664        | 84,0020112  | 110,3691165   |
| 6                      | 101,3546177 | 2%                | 5%             | 11,00184422 | 22,00368845       | 88,36542806 | 113,2366095   |
| 7                      | 103,3817101 | 2%                | 6%             | 11,88199176 | 23,76398352       | 89,47262597 | 116,451901    |
| 8                      | 105,4493443 | 2%                | 2%             | 13,07019094 | 26,14038188       | 90,31151915 | 118,780939    |
| 9                      | 107,5583312 | 2%                | -1%            | 13,33159476 | 26,66318951       | 92,11774953 | 120,3566621   |
| 10                     | 109,7094978 | 2%                | -3%            | 12,79833097 | 25,59666193       | 94,76000021 | 121,4839623   |

::: 

---
### Excelvergleich
TIPP

![[Pasted image 20230709133424.png]]

---
### Mögliche Verbesserungen
Dynamic Multiplier [^1] 


---
### Rainbow Options

---



## Quellen:

[^1]:[[Yao, Li]]  European Journal of Research and Reflection in Management Sciences Vol. 4 No. 2, 2016 p60
