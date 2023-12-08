# Manipulando arquivos
Utilizando VIM para manipular aquivos

**VI** ou **VIM** abre o aplicativo vim
utilizamos a tecla ESC para entrar com comandos, todos comandos são precedidos
de ':'
**:q** sair do vim
**:w** (salva/atualiza/cria) arquivo

Abre um arquivo especificado do dir atual, caso o arquivo não exista o VIM o cria.
```shell
vim archive.txt
```

**i** ou **tecla-insert** com um arquivo aberto no vim, entre para o modo de inserção, ESC para sair 

 **Navegação**
1. **h** move para esquerda
2. **l** move para direita
3. **j** move para baixo
4. **k** move para cima
5. **G** move cursos para última linha 
6. **gg** move cursos para primeira linha 
7. **0** move cursos para o início da linha 
8. **$** move cursos para o final da linha 
9. **i** inserir texto antes do cursor
10. **a** inserir texto depois do cursor
11. **A** inserir texto no final de uma linha
12. **I** inserir texto no início de uma linha
13. **o** inserir linha abaixo da linha atual
14. **O** inserir linha acima da linha atual
15. **x** deleta o caractere onde estar o cursor
16. **dd** deleta linha atual
17. **u** desfaz a última modificação no arquivo
18. **yy** copia uma linha
19. **p** cola a linha copiada
20. **/word** pesquisa pela word no texto


**Cat**
podemos criar arquivos com o cat
criamos um arquivo chamado archive. Após executar o comando é aberto area de digitação,
podemos inserir dados e com **control+d** sai da inserção e salva o arquivo
```shell
cat > archive
```

Mostra conteúdo do arquivo com characters que representam -e quebra de linha e -t tabulação
```shell
cat -et archive
```

Concatena 2 ou mais arquivos em um novo arquivo
```shell
cat arquive1 arquive2 ... arquiven > name-new-arquive-concate
```

**head & tail** mostra head ou tail do arquivo default de linhas é 10, mas podemos definir com
o param -n
```shell
tail n-2 my_arqchive.txt ## retorna 2 últimas linas
head n-2 my_arqchive.txt ## retorna 2 primeiras linas
```
