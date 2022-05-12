# Comandos SQL para modelagem fisica

## Criar Bancos de dados
CREATE DATABASE vendas_jessica CHARACTER SET utf8mb4;

## Entrar no banco de dados criado
USE DATABASE vendas_jessica

## Criar tabela fabricantes
CREATE TABLE fabricantes(
    id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(45) NOT NULL
);

## Criar tabela de produtos
CREATE TABLE produtos(
    id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(45) NOT NULL,
    preco DECIMAL (8,2) NOT NULL,
    quantidade SMALLINT NULL,
    descricao TEXT (1000) NOT NULL,
    fabricante_id INT NOT NULL


);

## Alterando a tabela para criar um relacionamento através da chave estrangeira
ALTER TABLE produtos
    ADD CONSTRAINT fk_produtos_fabricantes
    FOREIGN KEY (fabricante_id) REFERENCES fabricantes (id);

