# Compactação e descompactação de arquivos

## Tar
- tar.gz
- .tgz
- tar.bz2

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

**tar.gz** Cria um agrupamento e compacta com gzip
-z indica compactação em gzip. Os demais comandos já são introduzidos |^
```shell
tar -zcvf archive.tar.gz *.txt
```

descompactar gzip
```shell
tar -zxvf archive.tar.gz
```

**tar.bz2** Cria um agrupamento e compacta com bzip2. Bzip dois é mais eficiente em abundância 
de dados do que gzip.

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


na proxima aula pag 51.