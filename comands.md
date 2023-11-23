# Comandos

## conhecendo o shell
**history** apresenta o histórico de comandos utilizados no shell

Comando navegará para a pasta raiz(root)
```shell
cd /
```
Comando navegará para diretório do user atual
```shell
cd ~
```
Comando retorna para último diretório que esteve
```shell
cd -
```
Comando volta uma hierarquia de diretório
```shell
cd ..
```

**ls** lista os arquivos e diretórios no diretório atual

Exibe a lista de dir e arquivos incluindo arquivos ocultos
pattern de arquivos ocultos é iniciar com um '.' como prefixo
```shell
ls -a
```

Comando exibe arquivos ocultos de forma mais detalhada, contendo informações adicionais
```shell
ls -la
ll # mesma função de exibição detalhada
```
**clear ou control+l** limpa o console

**mkdir** cria novo diretório

Comando cria diretório com nome de *app*
```shell
mkdir apps
```

**mv** move ou renomeia arquivo/diretório

Comando move arquivo my_archive para diretório my_dir
```shell
mv my_archive ~/my_dir
```
Comando renomeia o arquivo
```shell
mv my_archive my_archive2
```

**cp** comando para copiar arquivos ou dir

Comando copia my_archive para o dir other_dir
```shell
cp my_archive ~/dir/other_dir
```
Comando copia um dir para outro, necessitando do param **-r** para fazer
essa operação, se tratando de uma atividade recursiva
```shell
cp -r my_dir ~/other_dir 
```

Comando copia my_archive para o dir que estou '.', '..'
- **.** dir atual
- **..** dir anterior ao dir atual(Father)
```shell
cp cp dir/sub_dir/my_archive .
```

**echo** comando para print de dados em arquivos ou no console
Printa na saida do console a mensagem
```shell
echo "Hello World!"
```

Com o param '>' é desviado a saída do console para o arquivo especifica
```shell
echo "Hello World!" > my_archive.txt
```
Printa a mensagem existente dentro do arquivo
```shell
cat my_archive.txt
```

**file** comando retorna o tipo do arquivo especificado
```shell
file my_archive.txt
```
**rm** usado para deletar/remover arquivos do sistema
-r Recursividade
```shell
rm -r dir/ # remove o dir e todos os subDirs e arquivos(recursivo)
```
**rmdir** usado para remover dir(apenas dir vazios)

**help** usado para obter informações sobre um comando
retorna um manual referencial ao comando ls.
```shell
help ls
```
Param --help retorna informações sobre o comando especificado
```shell
ls --help
```

**man** retorna o manual do comando especificado
```shell
man ls
```

no ambiente do man podemos utilizar comandos de navegação e pesquisa

**h** um help, entre em um manual util de navegação, pesquisa, etc..., do man

**q** sair do man

**\text** search no man

**f** avança page do man

**b** retorna page do man

**whatis** comando breve descrição do que o comando especificado faz
```shell
whatis ls
```

**find** permite localizar arquivos no sistema por suas características
busca todos os arquivos com extensão txt no dir atual e sub dirs
```shell
find -name /*.txt
```


Buscar arquivos no dir e sub-dir modificados a mais de um dia
```shell
find /dir -name *.name -atime +1
```

Buscar arquivos no dir e sub-dir modificados em menos de um dia
```shell
find /dir -name *.name -atime -1
```

## Manipulação de arquivos

**VI** ou **VIM** abre o aplicativo vim
utilizamos a tecla ESC para entrar com comandos, todos os comandos são precedidos
de ':'
**:q** sair do vim
**:w** (salva/atualiza/cria) arquivo


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
9. **Navegação**
10. **h** move para esquerda
11. **l** move para direita
12. **j** move para baixo
13. **k** move para cima
14. **G** move cursos para última linha
15. **gg** move cursos para primeira linha
16. **0** move cursos para o início da linha
17. **$** move cursos para o final da linha
18. **i** inserir texto antes do cursor
19. **a** inserir texto depois do cursor
20. **A** inserir texto no final de uma linha
21. **I** inserir texto no início de uma linha
22. **o** inserir linha abaixo da linha atual
23. **O** inserir linha acima da linha atual
24. **x** deleta o caractere onde estar o cursor
25. **dd** deleta linha atual
26. **u** desfaz a última modificação no arquivo
27. **yy** copia uma linha
28. **p** cola a linha copiada
29. **/word** pesquisa pela word no texto

## CAT
Criamos um arquivo chamado archive. Após executar o comando é aberto area de digitação,
podemos inserir dados e com **control+d** sai da inserção e salva o arquivo
```shell
cat > archive
```

Mostra conteúdo do arquivo com characters que representam -e quebra de linha e -t tabulação
```shell
cat -et archive
```

**head & tail** mostra head ou tail do arquivo default de linhas é 10, mas podemos definir com
o param -n
```shell
tail n-2 my_arqchive.txt ## retorna 2 últimas linas
head n-2 my_arqchive.txt ## retorna 2 primeiras linas
```

## Compactação e descompactação
**.tar** Agrupar vários arquivos em um. Realiza cópia sem compactação

-c: cria um tar, -f direcionando destino do arquivo criado inserindo todos os arquivos de
extensão .txt do dir atual
```shell
# gerando arquivo .tar no dir atual com todos arquivos do dir atual com extensão .txt
tar -cf name-archive.tar *.txt
```

Cria na pasta root (~) my_archive.tar com agrupamento dos arquivos especificados
-v: verbose, vai printar o nome de todos os arquivos adicionados apos o processo
```shell
tar -cvf ~/archive.tar my_archive1 my_archive2 my_archive3 my_archiven
```

desagrupo o .tar. -x extrair -v verbose -f dir
```shell
tar -xvf archive.tar 
```

**tar.gz** Cria um agrupamento e compacta com tar.gz
-z indica compactação em tar.gz. Os demais comandos já são introduzidos |^
```shell
tar -zcvf archive.tar.gz *.txt
```
descompactar tar.gz
```shell
tar -zxvf archive.tar.gz
```
**tar.bz2** Cria um agrupamento e compacta com bzip2. Bzip dois é mais eficiente em abundância
de dados do que tar.gz.

-j indica compactação em bzip2. Os demais comandos já são introduzidos |^
```shell
tar -jcvf archive.tar.bz2 *.txt
```

descompactar .bz2
```shell
tar -jxvf archive.tar.bz2
```


**du** verifica tamanho de arquivos especificados
retorna no console o tamanho do arquivo em bytes.
1. -b: bytes
2. -m: megas
```shell
du -b arquive
```