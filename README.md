# minishell

Per testare, apri terminale e scrivi bash.

Prova su bash i comandi che devi eseguire su minishell, ma non usarlo come riferimento per i leak.

-----
questo e' lo schema di Sasha sul come dovrebbe funzionare la comunicazione dei commandi in pipeline.
P.s. manca la gestione dei redirect di input (< e <<) e quelli di output (> e >>) che se esistono allora si deve fare il dup2 con questi, e le pipe vengono ignorate.
