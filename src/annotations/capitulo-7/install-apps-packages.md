# Instalando pacotes e apps

Cada distribuição linux possui pacotes específicos

**Pacotes** conjunto de arquivos agrupados para facilitar a instalação e distribuição de programas

No "Ubuntu" os packages são baseados em Debian (.deb)

## Gerenciador APT

Advanced Package Tool

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

Apenas baixa o pacote sem o instalá-lo. Deixado-o no dir : /var/cache/apt/archives/
```shell
sudo apt install -d nome_do_pacote
```

Retorna dados do programa que especificando, podendo gerenciá-lo com comandos
- {start|stop|restart|reload|force-reload|status}
```shell
sudo service programa
```