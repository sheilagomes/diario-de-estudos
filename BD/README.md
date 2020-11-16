# Banco de dados

- [Documentação MySQL](https://dev.mysql.com/doc/refman/8.0/en/)

## Dicas gerais
* Diferença entre char e varchar: o primeiro usa todos os caracteres e preenche com espaços, o segundo só usa o que for ocupado

## Comandos MySQL
* Para criar BD com codificação utf8:
    create database mars_rover_db default character set utf8 default collate utf8_general_ci;

* Exemplo de criação de tabela com chave primária 
```
create table estudo (
id int not null auto_increment,
descricao varchar(30) not null,
nascimento date,
sexo enum('M', 'F'),
peso decimal(5,2),
altura decimal(3,2),
nacionalidade varchar(20) default 'Brasil',
primary key (id)
) default charset = utf8;
```

* Para inserir dados:
```
insert into pessoas values (default, 'Claudio', '1975-4-22', 'M', '99', '2.15', default), ('Pedro', '1999-12-3', 'M', '87', '2'), (default, 'Janaina', '1987-11-2', 'F', '75.4', '1.66', 'EUA');
```
* Para conferir a inserção:
`select * from pessoas;`
* Para ver a estrutura da tabela:
`describe pessoas;   //ou desc pessoas;`
* Para alterar a tabela e adicionar colunas:
```
alter table pessoas
add column profissao varchar(10);
```
* Para alterar a tabela e adicionar colunas em posição específica:
```
alter table pessoas
add column profissao varchar(10) after nome;
```
* Para alterar a tabela e adicionar colunas na primeira posição:
```
alter table pessoas
add codigo int first;
```
* Para alterar a tabela e adicionar chave primária:
`alter table cursos add primary key(idcursos);`
* Para alterar a tabela e excluir colunas:
```    
alter table pessoas
drop column profissao;
```
* Para alterar a tabela, alterar colunas e deixar vazias:
```
alter table pessoas
modify column profissao varchar(20) not null default '';
```
* Para alterar a tabela e renomear colunas:
```
alter table pessoas
change column profissao prof varchar(20);
```
* Para renomear a tabela:
```
alter table pessoas
rename to gafanhotos;
```
* Exemplo de criação de tabela com verificação de existência, e de valor único e números absolutos nos tipos:
```
create table if not exists cursos (
nome varchar(30) not null unique,
descricao text,
carga int unsigned,
totaulas int unsigned,
ano year default '2020'
) default charset = utf8;
```
* Para apagar tabelas ou bancos de dados:
```
drop table cursos;
drop database cadastro;
```
* Para atualizar a tabela e alterar por registros:
```
update cursos
set nome = 'html5'
where idcursos = '1';
```
* Para atualizar a tabela e excluir por registros:
`delete from evento where id = '7';`
* Para excluir todos os dados de uma tabela:
`truncate cursos;`
* Para mostrar dados em ordem crescente:
```
select * from cursos
order by nome;
```
* Para mostrar dados em ordem decrescente:
```
select * from cursos
order by nome desc;
```
* Para filtrar por colunas:
`select nome, ano, carga from cursos;`
* Para filtrar por colunas em ordem:
```
select nome, ano, carga from cursos
order by ano, nome;
```
* Para filtrar por linhas em ordem:
```
select * from cursos
where ano = '2016'
order by nome;
```
*(O que aparece como resultado do select é o result set)*
* Para filtrar por intervalo e com ordens diferentes:
```
select * from cursos
where ano between 2016 and 2018
order by ano desc, nome;
```
* Para filtrar por intervalo com in e operador lógicode outro jeito:
```
select * from cursos
where ano in (2016, 2018, 2020) and totaulas < 20
order by nome;
```
* Para filtrar por parte do que se procura (mostra tudo que começa com P e é case insensitive, o % seleciona nenhum ou vários caracteres):
```
select * from cursos
where nome like 'p%';
```
*Outras opções: '%p'  '%p%'  'ph%p_'  'p__t%' , onde cada sublinhado exige um caractere qualquer*
* Para filtrar sem repetição:
`select distinct carga from cursos;`
- Para contar registros dentro de certas condições:
`select count(*) from cursos where carga > 40;`
- Para saber o maior valor dentro de uma coluna, funciona tb para letras, vai por ordem alfabética:
`select max(carga) from cursos;`
* Para saber o menor valor dentro de uma coluna, funciona tb para letras, vai por ordem alfabética:
`select min(carga) from cursos;`
* Para somar os valores dentro de uma coluna:
`select sum(carga) from cursos;`
* Para fazer a média dos valores dentro de uma coluna:
`select avg(carga) from cursos;`
* Para agrupar e contar por colunas, selecionar internamente e depois ordenar decrescente (o having só pode usar a coluna do group):
```
select carga, count(*) from cursos
group by carga
having carga > 30
order by count(*) desc;
```
* Para agrupar e contar por colunas e selecionar internamente com group e having, que só vai mostrar dentro do atributo a condição especificada:
```
select carga, count(*) from cursos
where ano > 2015
group by carga
having carga > (select avg(carga) from cursos);
```
* Para inicializar o mysql no terminal:
`mysql -h localhost -u root -p`

[Markdown](https://guides.github.com/features/mastering-markdown/) / [ResizeImage](https://resizeimage.net/)
