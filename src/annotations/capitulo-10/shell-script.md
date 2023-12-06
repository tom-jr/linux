# Shell Scripts

Salvamos os scripts em aquivos de extensão **.sh**

```shell
# primeira linha informa onde será executado o bash. qual dir
#! /bin/bash  
echo "Contando linhas ..."

# comando para o console prar por 5 segundos
sleep 5 

#salva o retorno do comando em uma var chamada LINHAS
LINHAS=`cat ~/workspace-stdy/lab/teste-script.txt | wc -l` 

#referencia a var
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

ESTAMOS NA PG 107
