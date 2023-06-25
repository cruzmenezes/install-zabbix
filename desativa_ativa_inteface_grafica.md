# DESATIVANDO/ATIVANDO INTERFACE GRÁFICA OU MODO TEXTO COM SYSTEMD

##### Dica simples e rápida de como desativar a interface gráfica e ficar apenas modo texto ou vice-versa em distribuições com SystemD.

1. DESCOBRIR A CONFIGURAÇÃO ATUAL.
   
       $ systemctl get-default

#### Se a saída for:

       $ graphical.target

#### Você possui um interface gráfica habilitada.

#### Se a saída for:

       $ multi-user.target

#### Então está apenas em modo texto.

2. ALTERAR DE MODO GRÁFICO PARA APENAS TEXTO
Execute:

       $ sudo systemctl set-default multi-user.target

#### Feito isso, reinicie a máquina.

3. ALTERAR DE MODO TEXTO PARA INTERFACE GRÁFICA
Execute:

       $ systemctl set-default graphical.target

### Feito isso, reinicie a máquina.



