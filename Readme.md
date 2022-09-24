# Atividade contínua de Framework Full stack

<p>Criação de um micro serviço que faz o registro e armazena dados de um produto e <i>conteinerizar.</i></p>

* Nome do produto
* Valor do produto 
* Categoria do produto

---

## Comandos utilizados

<p>Para subir as informações informadas no meu arquivo de Docker-compose: </p>

```docker-compose up```

<p>Para para acessar criar o Banco de dados:</p>

```docker exec -it s4fullstack_ac2-db-1 bin/bash```

<p>Criar esquema:</p>

```create schema AtividadeContinua;```

<p>Usar esquema:</p>

```use AtividadeContinua;```

<p>Criar tabela:</p>

```CREATE TABLE tabela_rena( id_produto BIGINT NOT NULL AUTO_INCREMENT, nome VARCHAR(20) NULL, preco VARCHAR(20) NULL, categoria VARCHAR(20) NULL, PRIMARY KEY (id_produto));```

<p>Criar procedure: </p>

```DELIMITER // CREATE PROCEDURE sp_createUser( IN p_nome VARCHAR(20), IN p_preco VARCHAR(20), IN p_categoria VARCHAR(20)) BEGIN IF ( select exists (select 1 from tabela_rena where p_preco = p_preco) ) THEN select 'preco já existe';ELSE insert into AtividadeContinua ( nome, preco, categoria ) values ( p_nome, p_preco, p_categoria ); END IF; END // DELIMITER ;```

---

## Para acessar ao Banco
<p>Usar esquema criado:</p>

```use AtividadeContinua;```

<p>Selectionar dados gravados:</p>

```select * from tabela_rena;```
