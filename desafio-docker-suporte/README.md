### Solução Desafio Docker

Segue a lista do que fiz para resolver esse desafio

1. Criado network Docker.
2. Criado um volume que inicia o InitFile para criar tabela no db.
3. Adicionado Comando para compilar o ts no dockerfile.
4. Adicionado linha no Dockerfile que Instala os pacotes netcat-openbsd e default-mysql-client. 
O netcat-openbsd é uma ferramenta de rede que pode ser usada para verificação de porta, enquanto 
default-mysql-client é o cliente MySQL padrão para interagir com um servidor MySQL.
5. Criado dentro do CMD do Dockerfile um comando para verificar se a tabela do banco de dados já foi
criada antes de inicializar o container. 
Uma solução mais adequada seria criar um Script de inicialização, mas como parte do desafio era alterar
apenas o Dockerfile e compose, fiz dessa forma.
6. Adicionado HealthCheck para erificar a saude do container mysql.
7. Adicionado porta de exposição no container do db.

(OBS: Pode ser que assim que acessar http://localhost:8080/ no primeiro momento aparece erro 502, mas
é porque o container do app só inicia depois do banco de dados ler o volume do arquivo init. Então é
recomendado esperar os containers iniciarem por completo antes de abrir no navegador) 😀

## Desafio Docker

O objetivo desse desafio é que ao executar `docker compose up` tudo deve ser criado por completo e os containers precisam depender um do outro para subirem.

Este projeto base possui diversos erros de Docker, por isso os ajustes estão apenas nos arquivos:
- Dockerfile
- docker-compose.yaml

Analise os dois arquivos, verifique o que está impedindo a execução dos containers e faça o fix necessário.

---

### Correção do desafio:

Para verificar se está tudo funcionando, você deverá rodar o projeto via docker-compose e posteriomente acessar o seu ambiente local:

Rode o comando:

```bash
docker compose up
```

Acesse a rota abaixo e uma lista de nomes deve ser impressa na tela:

```
localhost:8080
```
