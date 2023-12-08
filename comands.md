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
Descompactar tar.gz
```shell
tar -zxvf archive.tar.gz
```

Descompactar tar.gz e os demais apontando para um dir especifico
```shell
tar -zxvf archive.tar.gz -C dir/
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

**GZIP** compactação gerar um '.gz'. No caso de arquivo de texto, o gzip concatena tudo
em um único arquivo
-cr cria e compactar
```shell
gzip -cr *.txt > archive.gz
```

Extrai e deleta o arquivo '.gz' de extração
```shell
gunzip archive.gz
```

**ZIP** compacta uma extensão '.zip'
param: nome do arquivo, arquivos a serem compactados
```shell
zip archive.zip *.txt #compacta 
unzip archive.zip #descompacta 
```

## ADM de Users
**sudo** usamos sempre que precisamos executar comandos que necessitam do
superUser

Comando para listar dados de forma detalhada, inclui as permissões.
```shell
ls -l #[long listing]
```
**chmdo** comando para atribuir permissões, atuando diretamente nos níveis de dono, grupo e outros

Adiciona permissão de leitura e escrita para dono, grupo, outros
Obs: sem espaço após a virgúla.
```shell
sudo chmod u=rw,g=rw,o=rw 
```
r,w,x

| BIN | OCTA |
|-----|------|
| 000 | 0    |
| 001 | 1    |
| 010 | 2    |
| 011 | 3    |
| 100 | 4    |
| 101 | 5    |
| 110 | 6    |

Adiciona a mesma permissão utilizando notação OCTAL
```shell
sudo chmod 666 archive #110=6,110=6,110=6 -rw-rw-rw-
```

executa de forma recursiva
```shell
chmod -R 777 /dir
```

**addgroup**
Adiciona novo grupo
```shell
sudo addgroup group_name
```

Adicionando novo user
cria um user e group automaticamente
```shell
sudo adduser user_name
```

Adiciona user ao group se o group não existe ele é criado
```shell
sudo add group user group
```

mostra o group do user
```shell
groups user
```


Cria user e ja o adiciona a um group(group precisa pre-existir)
```shell
adduser user group
```

muda o grupo do arquivo ou dir
```shell
sudo chgrp group archive_or_dir
```

muda o dono do arquivo ou dir
```shell
sudo chown user archive_or_dir
```

deleta group
```shell
sudo groudel group
```

deleta user
```shell
sudo userdel user
```

# Instalando Packages APT(Advanced Package Tool)
Atualiza a lista de packages
```shell
sudo apt update
```

Atualiza o sistema
```shell
sudo apt upgrade
```

Instala um pacote
```shell
sudo apt install package_name
```

Remove um pacote
```shell
sudo apt remove package_name
```

Retorna dados do programa que especificando, podendo gerenciá-lo com comandos
- {start|stop|restart|reload|force-reload|status}
```shell
sudo service programa
```

**ps** comando para ver os processos em execução

- **a**: lista todos os processos existentes
- **u**: exibe nome do user dono do processo
- **x**: lista processos que não possuem relação com o terminal
- **m**: exibe a quantidade de memória consumida por cada processo

```shell
ps auxm
```

**wc** comando usado para contabilizar dados de output
Comando utiliza o pipe '|' para combinar os comandos. Assim posso contar o número de processos.
```shell
ps aux | wc -l
```

**grep** comando para filtrar uma saida e retorna rows que corresponde a palavra outra frase de filtro
retorna as rows que tem nome
```shell
ps -A | grep process_name
```

**top** comando retorna uma lista de processo que se atualiza constantemente. Contém dados estatísticos
com uso de memória, processamento, etc.


- **KILL**
- **TERM**
- **STOP**
- **CONT**
- 
  PID = número do processo
```shell
sudo kill -STOP PID
```

Para todos os processo referente ao nome
```shell
killall -STOP name-process
```
Muda a prioridade na execução de processos
```shell
sudo renice -19 PID
```

## Shell

```shell
# primeira linha informa onde será executado o bash. qual dir
#! /bin/bash  
echo "Contando linhas ..."

# comando para o console dormir por 5 segundos
sleep 5 

#salva o retorno do comando em uma var chamada LINHAS
LINHAS=`cat ~/workspace-stdy/lab/teste-script.txt | wc -l` 

#referenciar a var
echo "Existem $LINHAS linhas o arquivo."

```


```shell
echo "Informe o nome do arquivo que deseja buscar"

#ler arquivo e armazena na var ARCHIVE
read ARCHIVE

# armazena os retornos do output do comando
#formas possíveis
#VAR=`comandos script`
#VAR=$(comandos script)
CONSULTAR=$(ls ~ | grep $ARCHIVE)

# o if é bem claro em sua definição. O param -z | -d pergunta se existe valor na var
if [ -z $CONSULTAR ]; then
        echo "$ARCHIVE não foi encontrado!"
else
        echo "Arquivo encontado"
fi

```
## Cron

Lista se existe tarefas agendadas para o usuário especificado
```shell
crontab -u user-name -l
```

Permite criar tarefas para usuários especificado
```shell
crontab -u user-name -e
```

Carrega as configurações do arquivo (.bashrc) para o shell atual
```shell
source .bashrc
```

Comando faz download do arquivo referenciado no link
param -c é para continuar o download caso tenha sido interrompido
```shell
wget -c link-download
```
