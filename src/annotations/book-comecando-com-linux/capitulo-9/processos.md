# Processos

Processos possuem estados
- execução
- pronto/espera
- bloqueado

Um processo consegue criar outros processos. Se transformando em pai de outros processos.
Cada processo recebe u PID(id dado pelo sistema)

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

## Sinais de processos

- **KILL** sinal com função de encerrar um processo;
- **TERM** termina o processo após ele finalizar uma tarefa;
- **STOP** interrompe a execução de um processo;
- **CONT** ativa a execução de um processo que foi interrompido.

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