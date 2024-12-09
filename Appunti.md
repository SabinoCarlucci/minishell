Ecco la tua lista formattata correttamente come un file `.md`:

```markdown
# Funzioni ammesse nel progetto Minishell

## **Funzioni di libreria standard**
### **Input/Output**
- **`readline`**  
  Legge una riga di input dall'utente con supporto per editing e cronologia.  
  Restituisce un puntatore a una stringa allocata dinamicamente.

- **`rl_clear_history`**  
  Libera la memoria utilizzata dalla cronologia dei comandi.

- **`rl_on_new_line`**  
  Notifica a `readline` che un nuovo comando è iniziato.

- **`rl_replace_line`**  
  Sostituisce la riga corrente con un testo specificato.

- **`rl_redisplay`**  
  Ridisegna la riga corrente sul terminale.

- **`add_history`**  
  Aggiunge una stringa alla cronologia dei comandi.

- **`printf`**  
  Stampa un formato specifico su standard output. Simile a `ft_printf` nella tua `libft`.

### **Gestione della memoria**
- **`malloc`**  
  Alloca dinamicamente memoria.

- **`free`**  
  Libera memoria precedentemente allocata con `malloc`.

### **Scrittura e accesso ai file**
- **`write`**  
  Scrive dati in un file o una descrizione di file, incluso lo standard output.

- **`access`**  
  Controlla i permessi di accesso a un file o una directory.

- **`open`**  
  Apre un file e restituisce un file descriptor.

- **`read`**  
  Legge dati da un file descriptor.

- **`close`**  
  Chiude un file descriptor.

---

## **Gestione dei processi**
- **`fork`**  
  Crea un nuovo processo duplicando il processo corrente.

- **`wait`**  
  Attende la terminazione di un processo figlio.

- **`waitpid`**  
  Estensione di `wait`, consente di specificare quale processo attendere.

- **`wait3`** e **`wait4`**  
  Versioni avanzate di `wait`, permettono di ottenere informazioni aggiuntive sul processo terminato.

- **`signal`**  
  Imposta un gestore per un segnale specifico.

- **`sigaction`**  
  Una versione più avanzata e portabile di `signal`.

- **`sigemptyset`** e **`sigaddset`**  
  - `sigemptyset`: Inizializza un set di segnali vuoto.  
  - `sigaddset`: Aggiunge un segnale a un set.

- **`kill`**  
  Invia un segnale a un processo.

- **`exit`**  
  Termina un processo con un codice di uscita specificato.

---

## **Gestione dei file e directory**
- **`getcwd`**  
  Restituisce la directory corrente come stringa.

- **`chdir`**  
  Cambia la directory corrente.

- **`stat`**, **`lstat`**, **`fstat`**  
  Recuperano informazioni sui file:  
  - `stat`: informazioni su un file specificato.  
  - `lstat`: come `stat`, ma segue i link simbolici.  
  - `fstat`: lavora su file descriptor.

- **`unlink`**  
  Rimuove un file.

- **`execve`**  
  Esegue un file binario, sostituendo il processo corrente.

---

## **Redirezioni e pipe**
- **`dup`**  
  Duplica un file descriptor.

- **`dup2`**  
  Duplica un file descriptor su un altro, chiudendo il file descriptor target.

- **`pipe`**  
  Crea una connessione bidirezionale tra processi tramite un array di due file descriptor.

---

## **Gestione delle directory**
- **`opendir`**  
  Apre una directory per leggere i suoi contenuti.

- **`readdir`**  
  Legge l'elemento successivo in una directory aperta.

- **`closedir`**  
  Chiude una directory aperta con `opendir`.

---

## **Funzioni per il terminale**
- **`isatty`**  
  Controlla se un file descriptor corrisponde a un terminale.

- **`ttyname`**  
  Restituisce il nome del terminale associato a un file descriptor.

- **`ttyslot`**  
  Restituisce l'indice del terminale nel file `/etc/ttys`.

- **`ioctl`**  
  Controlla e configura dispositivi hardware (come i terminali).

---

## **Gestione delle variabili d'ambiente**
- **`getenv`**  
  Recupera il valore di una variabile d'ambiente.

---

## **Funzioni di configurazione del terminale**
- **`tcsetattr`** e **`tcgetattr`**  
  - `tcsetattr`: Configura le impostazioni del terminale.  
  - `tcgetattr`: Legge le impostazioni del terminale.

- **`tgetent`**, **`tgetflag`**, **`tgetnum`**, **`tgetstr`**, **`tgoto`**, **`tputs`**  
  Funzioni per il controllo avanzato del terminale. Utili per configurare la visualizzazione e i comportamenti interattivi.

---
