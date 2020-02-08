<style>
.centered {
	text-align: center;
}
img.right_side {
  float: right;
  margin:5px 5px 0px 20px;
  width: 50%;
}
img.left_side {
  float:left;
  margin:5px 20px 0px 5px;
  width: 20%;
}

p.clear {
  clear: both;  
}
p.img-container {
  margin-bottom: 15px;
}

p.img-container::after {
  margin-bottom: 15px;
  overflow: hidden;
  clear: both;
}
</style>

# Operazioni CRUD

Quando interagiamo con un qualsiasi database, sappiamo bene che esistono diverse categorie di comandi per interrogarlo e manipolarlo. In generale, i diversi comandi rientrano all'interno delle operazioni cosiddette **CRUD**: **C**reate, **R**ead, **U**pdate e **D**elete.

I database SQL e le chiamate HTTP usano strategie diverse per eseguire queste operazioni. Di seguito una tabella riassuntiva di confronto.

| Operazione  | SQL | HTTP |
|---|---|---|
| Create |INSERT|POST (o PUT)|
| Read  |SELECT|GET|
| Update  |UPDATE|PUT / PATCH|
| Delete  |DELETE|DELETE|

## Selezione della risorsa
In HTTP, per selezionare l'elemento che si vuole creare o modificare, bisogna identificare **l'URL** della risorsa.

In generale, avremo un URL base che identifica il database, e un path relativo che identifica la risorsa all'interno del db.


## Modifica della risorsa
Per modificare la risorsa, il ragionamento è simile. Troviamo il path della risorsa da modificare, ed usiamo `POST` e `PUT` in base al tipo di operazione che vogliamo eseguire.

### Idempotenza
Quale usiamo tra `POST` e `PUT`? Per rispondere, introduciamo brevemente il concetto di idempotenza. Un comando si chiama _idempotente_ se "_richieste ripetute identiche devono portare al medesimo stato dei dati sul server_". Per semplificare, pensate ad esempio ad una UPDATE in SQL. Se chiamate più volte UPDATE con gli stessi parametri, le chiamate successive alla prima non avranno effetto sulla riga da aggiornare. Pensate ora alla INSERT. Se chiamate più volte INSERT con gli stessi parametri (ipotizzando una assegnazione automatica della chiave primaria), ad ogni chiamata il database andrà ad aggiungere una nuova riga.

La stessa cosa per le chiamate HTTP.

PUT è idempotente: facendo più richieste HTTP PUT, il DB viene (eventualmente) modificato solo la prima volta.

POST non è idempotente: facendo più richieste HTTP POST, ad ogni chiamata verrà aggiunta una nuova risorsa e creata una chiave primaria per noi.

Approfondimento sul concetto di idempotenza [qui]( http://blog.loris.tissino.it/2013/06/http-rest-e-api.html).
