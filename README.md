
## Passo 1
Passando seu e-mail

`ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`
ssh-keygen -t rsa -b 4096 -C "vinicius.morais@quickdigital.com.br"

## Passo 2

Após isso 2 prompts aparecem. O primeiro solicitando o arquivo no qual vc vai salvar a chave, e o local dele se desejar.

o segundo, é para a fase secreta para a camada de segurançã adicional.


### Passo 3 - Adicione a chave SSH ao ssh-agent.

*O ssh-agent é responsável por manter as chaves privadas. Pense nisso como um chaveiro.*


Antes de adicionar a nova chave SSH ao ssh-agent, primeiro verifique se o ssh-agent está sendo executado ao executar:

$ eval "$(ssh-agent -s)"
> Agent pid 59566
Quando o ssh-agent estiver em execução, o comando a seguir vai adicionar a nova chave SSH ao agente SSH local.

ssh-add -K /Users/you/.ssh/id_rsa
A nova chave SSH agora está registrada e pronta para uso!


## Passo 4
Com o token criado

https://bitbucket.org/account/settings/ssh-keys/
- clicar no btn add Key
  - de um label
  - cole a Key no campo 
    - modelo de chave: 
      ssh-rsa [.....KEY]vinicius.morais@quickdigital.com.br

  - só salvar

---
Tomei esse erro:
Enter PIN for authenticator:
Provider "internal" returned failure -1
Unable to load resident keys: invalid format
---

### Sucesso
Se sucesso, você recebe um e-mail também com a chave adicionada na conta



Links uiteis
[Doc Oficial](https://www.atlassian.com/br/git/tutorials/git-ssh)
[TroubleShooting](https://confluence.atlassian.com/bbkb/troubleshooting-ssh-issues-302811847.html)


