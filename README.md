CREATE TABLE estudio(
    cod int(2) primary key not null,
    nome varchar(45),
    propriedades varchar(45),
    faturamento_anterios decimal(10,2),
    datafundacao date
);

INSERT INTO estudio VALUES (1,'Center Filmes','João',200000.00,'1980-01-29'),
(2,'MGM','Michael',178000.00,'1990-01-23'),
(3,'Universal','Douglas',12000.00,'2000-01-21'),
(4,'Disney','Lucas',500000.00,'1980-12-31'),
(5,'Argentina Filmes','Maradona',38700.43,'2005-10-10');

CREATE TABLE filmes (
    cod int(2) primary key not null, 
    meses int(2),
    nome varchar(45),
    anolacamento year,
    custototal decimal(10,2),
    codestudio int,
    foreign key (codestudio) REFERENCES estudio
);

INSERT INTO filmes VALUES (1,20,'Tropa de elite',2010,200000.00,1),
(2,12,'Elysium',2014,650000.00,4),
(3,15,'MIB',2007,500000.00,2),
(4,9,'A procura da felicidade',2009,300000.00,2),
(5,4,'Malévola',2014,178000.00,4),
(6,7,'O Procurado',2008,243000.00,1),
(7,12,'Central do Brasil',1998,80000.00,3),
(8,3,'O auto da compadecida',2000,112777.00,5),
(9,21,'Homem de Ferro',2008,1000000.00,5),
(10,36,'Sherlock Holmes',2009,999999.00,3);

CREATE TABLE atores (
    cod int(2) primary key not null,
    Nome vachar(45),
    Nacionalidade varchar (45),
    idade int(2),
    sexo char(1)
);

INSERT INTO atores VALUES (1,'Lucas Melo','americana',35,'m'),
(2,'Angelina jolie','americana',34,'f'),
(3,'Fernanda Montenegro','brasileira',70,'f'),
(4,'Wagner Moura','brasileira',36,'m'),
(5,'Roberto Downey Jr','americana',42,'m');

CREATE TABLE atuam(
    cod int(2) primary key not null,
    codatores int,
    codfilme int,
    cache decimal(10,2),
    personagem varchar(45),
    foreign key (codatores) REFERENCES atores,
    foreign key (codfilme) REFERENCES filmes
    
);

INSERT INTO `atuam` VALUES (1,4,1,100000.00,'Capitão Nascimento'),
(2,4,2,18000.00,'John'),
(3,1,3,200000.00,'Will'),
(4,1,4,250000.00,'Stanley'),
(5,2,5,350000.00,'Malévola'),(
6,2,6,333000.00,'Mary'),
(7,3,7,50000.00,'Fernanda'),
(8,3,8,55000.00,'Maria'),
(9,5,9,700000.00,'Tony Starks'),
(10,5,10,660000.00,'Sherlock Holmes');

