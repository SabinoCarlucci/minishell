FONTI DA CONSULTARE

Abstract syntax tree
https://en.wikipedia.org/wiki/Abstract_syntax_tree

https://stackoverflow.com/questions/52666511/create-an-ast-from-bash-in-c

----

Casi particolari

- ec"ho" ciao
- ec"ho ciao"
- echo abc$USERabc
- echo abc"$USER"abc
- echo "'$USER'"
- cat | cat | ls (e' nel foglio correzione)
https://stackoverflow.com/questions/76020074/understanding-how-pipelines-work-in-bash-cat-cat-ls-pipeline-hangs-until-tw
- echo ciao >prova.txt | <prova2.txt cat (redirect-in ha precedenza su pipe)

----

42DOCS: guida su come fare
https://harm-smits.github.io/42docs/projects/minishell

----

articolo di uno che l'ha fatto
https://m4nnb3ll.medium.com/minishell-building-a-mini-bash-a-42-project-b55a10598218

suo minishell
https://github.com/m4nnb3ll/minishell

teoria sul metodo per procedere secondo tale articolo
https://eli.thegreenplace.net/2012/08/02/parsing-expressions-by-precedence-climbing

----

fonti consigliate da Tjaz
https://github.com/n1smm/mini_shell/blob/main/links.txt

sito mandato da Julio su gruppo minishell
https://minishell.simple.ink/building-a-linux-shell-f52cadb5145b44b5b34ac4eb84b21593

