# SHELL BASH

## Lezione 1

### Introduzione alla Shell
La shell è un'interfaccia che permette agli utenti di interagire con il sistema operativo. Quando è in stato di sleep (S), resta in attesa di ricevere comandi dall'utente, elabora questi comandi, e poi ritorna in attesa.

### Tipi di Shell
- **Login shell**: una shell che viene avviata al momento del login dell'utente nel sistema.
- **Interactive shell**: una shell che attende input dall'utente, elabora tali input e fornisce output.
- **Non-interactive shell**: una shell che non interagisce direttamente con l'utente e di solito esegue script in background.

### Uso della Shell
- Utilizzare il punto e virgola `;` per eseguire più comandi sulla stessa linea.
- Un **alias** è un comando abbreviato. Per esempio: `alias x="echo ciao;ls;ls;echo hello"`
- Raggruppare comandi con parentesi tonde `()` crea una sub-shell non interattiva. Ad esempio, `cd` in una sub-shell non altera la directory della shell corrente.
- Raggruppare comandi con parentesi graffe `{}` esegue tutti i comandi nella stessa shell.
- **History dei comandi**: premendo `CTRL-R`, è possibile cercare comandi precedentemente eseguiti.

## Lezione 2

### Esecuzione Condizionale
- `&&` (AND logico): `cmd1 && cmd2 && cmd3` - se `cmd1` esegue senza errori, allora esegue `cmd2`, e così via.
- `||` (OR logico): `cmd1 || cmd2 || cmd3` - se `cmd1` fallisce, allora esegue `cmd2`, altrimenti si ferma.

### Verifica dell'Esito di un Comando
Digitando `echo $?`, si ottiene l'esito dell'ultimo comando eseguito: `0` indica successo, altri valori indicano errori.

### Combinare Esecuzione Condizionale e Gruppi di Comandi
Esempio: `{ ls || echo ciao; } && echo finito`

## Lezione 3

### Redirezioni
- Redirigere l'output di un comando in un file: `ls > ciao.txt` (sovrascrive il contenuto del file)
- Uso di `>>` per appendere l'output al file senza sovrascrivere: `ls >> ciao.txt`
- Traduzione di input utilizzando `tr`: `tr "1234" "acbd" < t.txt` traduce i caratteri secondo la mappatura specificata.

### Redirezione Permanente
- Utilizzo di `exec` per creare una redirezione permanente. Esempio: `exec 5> /C/Fede/ciao.txt` crea una redirezione usando il file descriptor 5.
- Duplicazione della scrittura: `echo ciao 1>&5` usa il file descriptor 5 al posto di STDOUT.
- Chiusura di una redirezione: `exec 5>&-` chiude il file descriptor 5.

