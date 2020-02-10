# Deploy (dislocazione)

In questo capitolo vedremo come fare il deploy (dislocazione) della nostra applicazione nei casi più comuni: cloud e on-premises.

## Matrice delle dislocazioni

Uno strumento che ritengo utile per riuscire a fare un po' di chiarezza sui vari termini che si usano nel campo della dislocazione è la seguente tabella.

| | | |
|-------|-------|-------|
|  | **Macchina di proprietà** | **Macchina non di proprietà** |
| **Locali di proprietà** | on premises | noleggio / leasing |
| **Locali non di proprietà** | housing | cloud |

Fino all'inizio del secolo, l'unica scelta delle aziende era praticamente l'on-premises (letteralmente "nei locali"); con il passare del tempo molte società hanno trovato conveniente spostare parte o tutto il loro business su macchine remote, prima in housing e oggi in cloud. Il noleggio/leasing è invece sempre stato un mercato di nicchia.

Oggi le soluzioni maggiormente praticate sono i due casi di on-premises e cloud, e sono quelli che vedremo in questo corso. Vediamo vantaggi e svantaggi.



## Cosa, come, dove dislocare
Il deploy di una applicazione web si inserisce all'interno di un processo di sviluppo, che rivediamo brevemente:

1. Creazione dell'architettura
Ovvero cosa devo sviluppare: quanti tiers mi servono, come devono comunicare tra loro, etc. Ad esempio la mia architettura potrebbe prevedere dei client desktop e mobile, un server PHP, un server Java, un database MySQL per i prodotti e un database Oracle per gli utenti

2. Scelta del numero di macchine (come)
Una volta che so come è organizzata la mia web app, devo decidere fisicamente come dividere le varie macchine: posso decidere di mettere il server PHP e Java nella stessa macchina fisica, magari su macchine virtuali differenti oppure su docker container differenti (virtualizzazione leggera). Questo dipende dai requisiti di sicurezza ed affidabilità, dal peso computazionale, dalla potenza di calcolo delle macchine, etc.

3. Locazione delle macchine (dove)
Strettamente legato al punto precedente c'è quindi la scelta della dislocazione delle macchine: on-prem? cloud? ibrido? è una scelta non facile che coinvolge tanti fattori e che adesso andremo a vedere.