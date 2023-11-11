# GIT

## Tabela de Conteúdos
- [GIT](#git)
  - [Tabela de Conteúdos](#tabela-de-conteúdos)
    - [Criar chave ssh](#criar-chave-ssh)
    - [UNPROTECTED PRIVATE KEY FILE](#unprotected-private-key-file)
  

### Criar chave ssh 

Para criar uma chave ssh para acesso ao 

### UNPROTECTED PRIVATE KEY FILE
**[⬆ Topo](#tabela-de-conteúdos)**

Se esta ocorrendo o erro ` WARNING: UNPROTECTED PRIVATE KEY FILE!   ` quando você tenta clonar um repositorio no Linux.
Povavelmente redefiniram as permissões em seu diretório `.ssh` oculto em sua pasta de usuário e suas chaves não funcionarão mais. É muito importante que esses arquivos não possam ser gravados por qualquer pessoa com login, então o `openssh` apresentará um erro se você tentar usá-los.

```bash
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Permissions 0444 for '/home/natanfiuza/.ssh/id_ed25519' are too open.
It is required that your private key files are NOT accessible by others.
This private key will be ignored.
Load key "/home/natanfiuza/.ssh/id_ed25519": bad permissions
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
```

Para corrigir isso, você precisará redefinir as permissões para o padrão:
```bash 
sudo chmod 600 ~ /.ssh/id_ed25519
```

Se você estiver recebendo outro erro como:

```bash
Are you sure you want to continue connecting (yes/no)? yes
Failed to add the host to the list of known hosts (/home/natanfiuza/.ssh/known_hosts).
```
