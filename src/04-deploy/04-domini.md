# Domini

Per accedere al nostro servizio web, abbiamo bisogno di un dominio che ci permetta di raggiungerlo.

Il concetto di associare un nome (o dominio) ad un indirizzo IP risale al 1983 ed è diventato standard internazionale nel 1987, quindi quando Tim Berners Lee inventò il web nel 1989, era già una tecnologia diffusa.

Lo scopo iniziale dei domini era quella di usare dei nomi mnemonici per le macchine, al posto degli indirizzi IP, molto difficili da ricordare.

In seguito sono stati usati per anche altri scopi: in particolare, è possibile cambiare l'IP dietro ad un nome di dominio, senza che l'utente se ne accorga, in modo da poter aggiornare o cambiare facilmente un servizio. Oppure è possibile associare IP diversi in aree geografiche diverse: com'è ragionevole, google.com punta a server diversi se ti trovi in Italia o negli Stati Uniti.

Oggi i domini hanno un altro ruolo fondamentale: servono per instaurare _fiducia_ nel cliente finale. Infatti, il mondo di Internet (come quello reale, d'altra parte) è pieno di siti che offrono servizi o prodotti simili e per cui è difficile distinguerne la qualità e l'autenticità. La fiducia è sempre alla base di qualsiasi relazione.

Per questo la tecnologia HTTPS, che offre connessioni sicure con un sito, è strettamente legata al nome del dominio. Quello che infatti dobbiamo fare è assicurarci che la nostra _fiducia_ sia riposta nel giusto sito, e non in uno contraffatto.

## Registrazione di un dominio
Per cominciare a creare il proprio business e la propria relazione con il cliente, uno dei primi passi è registrare il proprio dominio. 

Esistono molti siti che offrono questo servizio, chiamati "registrar", ad esempio noi abbiamo usato [GoDaddy](godaddy.com), ma è possibile usare AWS, Google, Aruba e tantissimi altre aziende simili.

Ovviamente, i registrar non decidono quali siti puoi comprare oppure no: seguono le regole che vengono fornite dallo [IANA]
(https://www.iana.org/), l'ente internazionale che si occupa di gestire fondamentalmente gli indirizzi IP. Lo IANA è un'emanazione dell'ICANN (Internet Corporation for Assigned Names and Numbers), un ente sotto il diretto controllo del Ministero del commercio degli Stati Uniti. 

Per consultare quali sono tutti i domini di primi livello esistenti, la fonte ufficiale è [questa](https://www.iana.org/domains/root/db).