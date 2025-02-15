# Domande e Risposte sul Progetto Minishell

## **Estratto e Risposte**

---

### 1) Estratto
> The shell will work only in interactive mode (no scripts, i.e. the executable takes no arguments)

#### Domanda:  
Che vuol dire modalità interattiva? Che vuol dire no scripts? Cos'è l'eseguibile?  

#### Risposta:  
- **Modalità interattiva**: Una modalità in cui il programma interagisce direttamente con l'utente, ricevendo comandi in tempo reale e rispondendo immediatamente. Ad esempio, quando apri un terminale e scrivi comandi come `ls`, il terminale è in modalità interattiva.  
- **No scripts**: Significa che il programma non deve accettare file di script come input. In Bash, uno script è un file contenente una sequenza di comandi che possono essere eseguiti automaticamente. Ad esempio, il comando `bash script.sh` esegue i comandi nel file `script.sh`. Minishell non supporta questo.  
- **Eseguibile**: È un file binario compilato che può essere eseguito direttamente dal sistema operativo. Ad esempio, quando compili il tuo progetto Minishell, il risultato sarà un file eseguibile che puoi avviare scrivendo `./minishell` nel terminale.  

---

### 2) Estratto
> Run simple commands with absolute, relative path (e.g. /bin/ls, ../bin/ls)

#### Domanda:  
Cosa sono i path assoluti e relativi? Fai degli esempi.  

#### Risposta:  
- **Path assoluto**: Specifica la posizione completa di un file o directory a partire dalla radice del filesystem. Ad esempio:  
  - `/bin/ls`: Indica l'eseguibile `ls` nella directory `/bin`.  
- **Path relativo**: Specifica la posizione di un file o directory rispetto alla directory corrente. Ad esempio:  
  - `../bin/ls`: Indica l'eseguibile `ls` nella directory `bin`, che si trova nella directory superiore rispetto a quella corrente (`..` indica "un livello sopra").  

---

### 3) Estratto
> Run simple commands without a path (e.g. ls, cat, grep, etc…)

#### Domanda:  
Che differenza c'è tra eseguire un comando con o senza path? Lo stesso comando può essere eseguito sia con che senza path?  

#### Risposta:  
- **Con path**: Quando fornisci il percorso completo o relativo del comando, il shell lo cerca esattamente in quella posizione.  
  - Esempio: `/bin/ls` esegue il comando `ls` dal path assoluto `/bin/ls`.  
- **Senza path**: Il shell cerca l'eseguibile nelle directory elencate nella variabile d'ambiente `$PATH`.  
  - Esempio: Scrivendo solo `ls`, il shell cerca `ls` in ogni directory definita in `$PATH`.  
- **Sì**, lo stesso comando può essere eseguito sia con che senza path, a condizione che il comando sia nel `$PATH` o che tu specifichi il percorso esatto.  

---

### 4) Estratto
> Have a working history (you can navigate through commands with up/down arrows)

#### Domanda:  
Cosa si intende con questo? Fai un esempio di come posso verificarlo con Bash.  

#### Risposta:  
- **Storia dei comandi**: È un registro dei comandi precedentemente eseguiti. Con le frecce su/giù, puoi navigare tra i comandi passati senza doverli riscrivere.  
- **Verifica in Bash**: Apri un terminale, scrivi un comando (`ls`), premi Invio. Poi premi la freccia su: vedrai `ls` apparire nuovamente, recuperato dalla cronologia.  

---

### 5) Estratto
> Implement pipes (|)

#### Domanda:  
Che vuol dire implementare le pipes? Fai un esempio di quale deve essere il risultato finale.  

#### Risposta:  
- **Pipes**: Permettono di collegare l'output di un comando all'input di un altro.  
  - Esempio:  
    - Comando: `ls | grep file`  
    - Risultato: L'output di `ls` (elenco dei file) è passato come input a `grep file`, che filtra solo i file contenenti "file" nel nome.  

---

### 6) Estratto
> Implement redirections (<, >, >>)

#### Domanda:  
Cosa sono i redirection? Fai esempi di input-output.  

#### Risposta:  
- **Redirection**: Permettono di modificare il flusso di input e output.  
  - Esempi:  
    - `echo "Hello" > file.txt`: Scrive "Hello" nel file `file.txt`.  
    - `cat < file.txt`: Legge l'input da `file.txt`.  
    - `echo "Add this" >> file.txt`: Aggiunge "Add this" alla fine di `file.txt`.  

---

### 7) Estratto
> Implement the here-doc (<<)

#### Domanda:  
Cos'è l'here-doc? Fai esempi.  

#### Risposta:  
- **Here-doc**: Consente di fornire input a un comando direttamente nel terminale, fino a un delimitatore definito.  
  - Esempio:  
    ```bash
    cat << EOF
    Hello
    World
    EOF
    ```
    L'output sarà:  
    ```
    Hello
    World
    ```  

---

### 8) Estratto
> Handle double quotes ("") and single quotes (''), which should escape special characters, beside $ for double quotes.

#### Domanda:  
Che vuol dire gestire double e single quotes? Cosa dovrebbero fare? Che vuol dire "escape" special characters?  

#### Risposta:  
- **Double quotes** (`""`): Preservano il testo tra le virgolette ma permettono l'espansione di variabili e caratteri speciali come `$`.  
  - Esempio: `echo "Hello $USER"` stampa "Hello <nome_utente>".  
- **Single quotes** (`''`): Preservano il testo tra le virgolette senza interpretare nulla.  
  - Esempio: `echo 'Hello $USER'` stampa "Hello $USER".  
- **Escape**: Rimuovere il significato speciale di un carattere. Ad esempio, `\$` stampa un simbolo `$` anziché interpretarlo come variabile.  

---

### 9) Estratto
> Handle environment variables ($ followed by a sequence of characters).

#### Domanda:  
Mi pare di capire che le variabili d'ambiente siano `$` seguito da una serie di caratteri, è corretto?  

#### Risposta:  
- Sì, le variabili d'ambiente sono rappresentate da `$` seguito da un nome, e contengono valori configurati nel sistema.  
  - Esempio: `$HOME` restituisce la directory home dell'utente.  

---

### 10) Estratto
> Handle signals like in bash (ctrl + C, ctrl + \, ctrl + D).

#### Domanda:  
Cosa significa gestire segnali come in Bash?  

#### Risposta:  
- Significa implementare reazioni specifiche per segnali inviati tramite la tastiera:  
  - `Ctrl+C`: Interrompe il comando corrente e mostra un nuovo prompt.  
  - `Ctrl+D`: Termina il programma.  
  - `Ctrl+\`: Non dovrebbe fare nulla.  

---

### 11) Estratto
> Implement the following built-ins: echo (option -n only), exit, env (with no options or arguments), export (with no options), unset (with no options), cd, pwd.

#### Domanda:  
Che vuol dire built-in?  

#### Risposta:  
- **Built-in**: Comandi integrati nel shell, eseguiti direttamente dal programma anziché tramite un eseguibile esterno.  
  - Esempi richiesti:  
    - `echo -n`: Stampa testo senza andare a capo.  
    - `exit`: Termina il shell.  
    - `env`: Mostra le variabili d'ambiente.  
    - `export`: Aggiunge/modifica variabili d'ambiente.  
    - `unset`: Rimuove una variabile d'ambiente.  
    - `cd`: Cambia la directory corrente.  
    - `pwd`: Mostra la directory corrente.  
