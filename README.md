# SSH Keys

*se windows: Rodar comandos dentro do Git BASH esses comandos abaixo*


## Passo 1 - Passando seu e-mail como categoria

Rodar o comando </br>
`ssh-keygen -t rsa -b 4096 -C "your_email@example.com"` </br>
`ssh-keygen -t rsa -b 4096 -C "vinicius.morais@quickdigital.com.br"`

## Passo 2 - Prompts

Após isso 2 prompts aparecem. O primeiro solicitando o arquivo no qual vc vai salvar a chave, e o local dele se desejar.

o segundo, é para a fase secreta para a camada de segurança adicional.

### Passo 3 - Adicione a chave SSH ao ssh-agent.

*O ssh-agent é responsável por manter as chaves privadas. Pense nisso como um chaveiro.*


Antes de adicionar a nova chave SSH ao ssh-agent, primeiro verifique se o ssh-agent está sendo executado ao executar:

$ eval "$(ssh-agent -s)"
> Agent pid 59566
Quando o ssh-agent estiver em execução, o comando a seguir vai adicionar a nova chave SSH ao agente SSH local.

ssh-add -K /Users/you/.ssh/id_rsa
A nova chave SSH agora está registrada e pronta para uso!

### Tomei esse erro de inicio:</br>
> Enter PIN for authenticator: </br>
Provider "internal" returned failure -1</br>
Unable to load resident keys: invalid format

</br>
ssh-add -vvv /Users/you/.ssh/id_rsa **foi o que passou**


## Passo 4 - Bitbucket
Com o token criado, acesse as configurações no Bitbucket.
https://bitbucket.org/account/settings/ssh-keys/

1. clicar no btn add Key
  - de um label
  - cole a Key no campo 
    - modelo de chave: 
      ssh-rsa [.....KEY]vinicius.morais@quickdigital.com.br

  - salvar

### Sucesso
Se sucesso, você recebe um e-mail também com a chave adicionada na conta


### Se outro arquivo/key
![a](https://raw.githubusercontent.com/vinimorais2399/how-set-ssh/main/assets/image.png)<br>


### Links úteis
<br>

[MadeWith](https://readme.so/pt/editor)
[Doc Oficial](https://www.atlassian.com/br/git/tutorials/git-ssh) <br>
[TroubleShooting](https://confluence.atlassian.com/bbkb/troubleshooting-ssh-issues-302811847.html)


