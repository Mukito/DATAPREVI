## Arquitetura TCP/IP

### Aplicação
Utilizada pelo programa para enviar e receber informações;

### Transporte
Recebe os dados, verifica a integridade e os divide em pacotes. Considera
apenas a origem e o destino (segmentos)

### Rede (Internet)
Realiza o reteamento da mensagem (pacotes/datagramas)

### Acesso ao meio
envia o datagrama pela camada inter-rede(quadro/bit)

## Protocolos de Aplicação
  * Padronizam a comunicação
  * Atuam junto com os protocolos da camada de transporte
  * Tem o seu funcionamento descrito em RFC (Request for Comments)
  * Possuem portas

-----------------------------------------

## Camada de Aplicação - Protocolo
  * **SMTP** - Envio de e-mails (**25**);
  * **HTTP** - utilizado por sistemas de informação de hipermídia distribuídos e colaborativos (**80**)
  * **HTTPS** - adiciona segurança ao protocolo HTTP (**443**)
  * **LDAP** - serviços de informação de diretorio distribuído (**389**)
  * **NFS** - sistema de arquivo distribuído (**111**)
  * **SMB** - compartilhamento de arquivos de rede (**139**)
  * **POP3** - baixar mensagens da caixa de correio eletrônico (**110**)
  * **IMAP** - permite o acesso de vários clientes à mesma caixa de correio eletrônico. As mensagens são mantidas o servidor(**143**)
  * **FTP** - transferência de quivos (21)
  * **SNMP** - gerenciamento de redes. facilita o intercâmbio de informações entre dispositivo (**161**)
  * **DHCP** - configuração dinâmica de terminais (**67/68**)
  * **TELNET** - interface entre terminais e aplicações através da internet. mesmo sem conhecer as caracteristicas (**23**)
  * **SSH** - acesso remoto seguro (@2)
  * **DNS** - sistema de nomes de domínio (**UDP/53**)
