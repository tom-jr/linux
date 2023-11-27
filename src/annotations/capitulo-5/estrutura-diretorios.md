# Estrutura de diretórios

dir '/' root

- **/bin** armazena arquivos executáveis binários, comandos base para execução do sistema. É um dir
público. Qualquer user pode usar os comandos de lá
- **/boot** contém arquivos de inicialização do sistema, onde está o gerenciador de boot do sistema
app que carrega o sistema operacional na inicialização
- **/etc** ficam os arquivos de configuração do sistema, scripts de inicialização, configuração de 
users e programas que são instalados
- **/lib** bibliotécas e módulos do kernel essenciais para o funcionamento do sistema. Libs são
funções compartilhadas que podem ser usadas por diversos programas
- **/media** matém os pontos de montagens. Quando inserimos um penDriver, é nesse dir que ele fica
temporariamente 
- **/mnt** usado para montagem temporária do sistema de arquivos de(HD, pendrives). Pode ser usado
da mesma forma que o **/media**
- **/opt** normalmente onde se instala programas que não fazem parte da distribuição.
- **/sbin** ficam os comando para inicialização, restauração e recuperação do sistema, é um dir de 
comandos especiais. Apenas o root pode acessar
- **/svr** mantém dados de serviços disponíveis pelo sistema
- **/temp** ficam armazenados arquivos temporários
- **/usr** mantidos programas essenciais para o funcionamento do sistema, programas instalados pelos 
users como editores, programas gráficos
- **/var** arquivos de dados variáveis [logs, arquivos de banco de dados e mensagens de emails]

 ## Dirs opcionais

- **/home** e **/root** são opcionais. Home armazena dados dos users. root é a pasta pessoal do super
user

## Dirs proc e sys

- **/proc** contém arquivos temporários de processos e execução no system. Um dir virtual utilizado pelo
kernel. Mantido configurações atuais do system e dados estatísticos 
- **/sys** como proc, mantém dados do system, porém é de forma mais organizada, para melhor administrar