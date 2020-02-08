# Cloud - Tutorial

In questa sezione vedremo praticamente come fare il deploy di una applicazione in cloud con AWS.

## Creare un'istanza
Dopo aver fatto il login, nella pagina che vi si presenta selezionare "Go to Classroom" e quindi la propria classe.

Dopo un paio di click si dovrebbe aprire una pagina di Vocareum, dove potete vedere il vostro credito residuo. Cliccate sul bottone AWS Console.

Ora vi ritrovate in una console reale di AWS! Ricordatevi di rimanere sempre in Virginia Settentrionale, altrimenti il vostro credito _non_ funzionerà.

Dalla lista dei servizi in alto, selezionate EC2. Nella pagina che si apre, selezionate il bottone blu per lanciare una nuova istanza. Lasciate tutto di default: Linux Amazon 2 AMI su x86 a 64bit, e t2.micro.

Generate una nuova chiave privata quando richiesto, con il vostro cognome tutto minuscolo. **ATTENZIONE!** mettete la chiave privata in un luogo sicuro, per esempio inviatevela per posta o copiatela su una chiavetta. Se perdete il file, non potrete più accedere alla vostra istanza; se qualcuno entra in possesso del file, potrà entrare e modificare la vostra istanza cloud.

Non chiudere la finestra della dashboard, ci servirà in seguito.

**CHECKPOINT**
Controllare sulla dashboard che l'istanza sia "running".

<p class="centered img-container">
<img class="centered w80p" title="EC2 running" alt="EC2 running" src="assets/ec2-running.png">
</p>


## Accedere all'istanza da VSCode
In questo tutorial accederemo all'istanza direttamente da Visual Studio Code, perché ci permetterà uno sviluppo più rapido e senza intoppi.

### Installare Remote-SSH extension
Aprire VSCode, andare nel pannello verticale a sinistra su "Extensions", cercare ed installare l'estensione [Remote - SSH](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh) di Microsoft.

Dopo l'installazione, vi comparirà una nuova icona nel pannello a sinistra e un quadratino verde in basso a sinistra.

**CHECKPOINT**
Controllare che VSCode sia come in figura.

<p class="centered img-container">
<img class="centered w80p" title="Remote-SSH" alt="Remote-SSH" src="assets/vscode-ssh.png">
</p>

### Copiare la chiave
Per potersi connettere correttamente, la vostra chiave privata deve stare dentro la cartella `.ssh` della vostra home.

1. controllate che esista la cartella `.ssh` dentro `C:\Users\NomeUtente\`, se non esiste createla
2. copiate la vostra chiave privata all'interno della cartella

**CHECKPOINT**
Controllare che la vostra chiave privata sia all'interno della cartella `.ssh` del vostro utente.


### Configurare il target

1. da VSCode, premere sull'icona "Remote Explorer" nel pannello di sinistra.
2. passare il mouse nella barra dove è scritto "SSH Targets" e premere su `+`
3. copiare dalla dashboard di AWS la stringa per connettersi alla macchina e incollarla nella casella di VSCode; la stringa la trovate selezionando l'istanza e facendo click su "Connect" in alto.

<p class="centered img-container">
<img class="centered w80p" title="Remote-SSH" alt="Remote-SSH" src="assets/ec2-connect.png">
</p>

4. sempre dalla barra di SSH Targets, cliccate ora sulla rotella e cliccate sulla prima voce
5. modificare il percorso della vostra chiave con il path completo del file, ovvero `C:\Users\NomeUtente\.ssh\nomechiave.pem`



**Checkpoint**
A questo punto dovete avere un target pronto per connettervi.

<p class="centered img-container">
<img class="centered w80p" title="Remote-SSH" alt="Remote-SSH" src="assets/vscode-target.png">
</p>


### Connettersi alla macchina remota
Da VSCode, connettetevi al target appena creato premendo sulla piccola icona con la finestra ed il + vicino al nome del target. Vi si aprirà una nuova finestra con una sessione di VSCode sulla macchina remota.

Aprite un terminale da VSCode.

**Checkpoint**
Controllate di avere una finestra del genere e che l'utente remoto da terminale si ec2-user.

<p class="centered img-container">
<img class="centered w80p" title="Remote-SSH" alt="Remote-SSH" src="assets/vscode-remote.png">
</p>


## Configurare l'istanza
Per configurare l'istanza, la prima volta fate come segue.

```
sudo yum update -y

# install docker and docker-compose
sudo yum install docker -y
sudo groupadd docker
sudo usermod -aG docker $USER # logout per avere effetto
```

**CHECKPOINT** Eseguite il comando `docker --version` e assicuratevi di non avere un messaggio di errore.
