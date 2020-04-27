# CentosAD

  O script sera disponibilizado em modulos, caso você queira utiliza-los individualmente sugiro que siga as intruções e modifique de acordo com a necessidade de sua infraestrutura!
  
  Obs: Script desenvolvido para as versões centos 6 & 7.


# Gerando arquivo OVPN

* Primeiro gerar o arquivo ovpn. (instruções de uso no script);
* Na máquina cliente instalar o pacote openvpn de acordo com a versão do seu linux;
* Fazer o download do arquivo .gz gerado pelo script, dentro de /etc/openvpn;
* Ao descompactar note 2 arquivos o pass.txt e o ovpn.conf;
* Inicie o serviço, e veja se o túnel atribuiu algum endereço ip;

# Ingressando a máquina no domínio

* Primeiro faça as adequações necessárias no script. (instruções de uso no script);
* Instruções a mais:

  Centos 7:
Para remover a máquina do domínio:

realm leave

  Centos 6:
 
 Basta remover o arquivo rm -rf /et/krb5.keytab

Obs: Não esqueça de reiniciar os serviços sssd e winbind

  ATENÇÃO:

  Ao remove-la o arquivo sshd.conf, fica com a linha "use_fully_qualified_names = True" troque para "use_fully_qualified_names = False", pois assim poderam logar sem declarar o domínio
 
   O netbios do windows aceita até 14 caracteres, não colocar mais que isso, pois irá comprometer o arquivo do kerberos, é uma chave criptografada para cominição entre o cliente e o domínio.
   
   COMANDOS ÚTEIS:
  
  Verificar se está logando no dominio:
  
  kinit usuário (AD)
   
   Verificar se o dominio esta configurado corretamente:
   
  Klist

# Entrada Dns 
