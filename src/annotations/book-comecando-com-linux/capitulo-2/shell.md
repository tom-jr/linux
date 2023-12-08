# Shell

## Primeiro contato com shell

<img src="2023-11-21 06-38-16.png" style="width:600px;">

- **tom-jr**: nome de usuário
- **@pc**: nome do host
- **~**: abreviação para pasta do usuário
- **$**: indica que o user não possui podes administrativos

**history** apresenta o histórico de comandos utilizados no shell
**cd** comando para navegar entre diretórios

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
ll
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

Comando copia um dir para outro necessitando do param **-r** para fazer
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

**cat** comando printa no console dados de um arquivo especificado
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

busca todos os arquivos com extensão html no dir especifica e sub dirs
```shell
find /dir/sub-dir -name *.html
```

Buscar arquivos no dir e sub-dir modificados a mais de um dia
```shell
find /dir -name *.name -atime +1
```

Buscar arquivos no dir e sub-dir modificados em menos de um dia
```shell
find /dir -name *.name -atime -1
```
