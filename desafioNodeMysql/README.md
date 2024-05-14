### Solução Desafio Node.js + MySQL

Segue a lista do que fiz para resolver esse desafio 

1.	Criação de network fullcycle_ para fazer a comunicação dos containers
2.	Troquei a versão do MySQL para a 5.7 para suportar a biblioteca JS ‘MYSQl’ como cliente
3.	Adicionei uma porta de exposição ao container do db
4.	Modifique o comando test: [] no healthcheck do container db
5.	Adicionado Script no index.js para criar tabela People antes de inserir os dados


### Desafio Node.js + MySQL

O objetivo desse desafio é que ao rodar o comando `docker compose up` a aplicação `node` deve funcionar por completa. Investigue os arquivos do projeto, os arquivos de configuração e faça o fix necessário.

### Restrições
- A versão do `Node.js` deve ser mantida
- As libs já presentes devem permanecer as mesmas
- Você poderá trocar as versões das libs já presentes

---

### Correção do desafio:
Para verificar se está tudo funcionando, você deverá rodar o projeto segundo os passos abaixo:

Rode o comando:

```bash
docker compose up
```

Acesse a rota abaixo e uma lista de nomes deve ser impressa na tela:

```
localhost:8080
```
