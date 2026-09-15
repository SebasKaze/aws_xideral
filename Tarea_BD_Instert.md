
# Tarea. Creacion y funciones de MYSQL
## CREATE TABLE
Se usa CREATE TABLE para crear una tabla con los requerimientos necesarios
```sql
CREATE TABLE peliculas_sebastian(
	id_peli INT AUTO_INCREMENT PRIMARY KEY,
	titulo VARCHAR(255) NOT NULL,
	genero VARCHAR(255) NOT NULL,
	ano_estreno DATE NOT NULL,
	duracion DECIMAL(4,1) NOT NULL,
	calificacion INT NOT NULL,
    clasi VARCHAR(255) NOT NULL
	disponible BOOLEAN NOT NULL
);
```

## INSERT
Se usa INSERT para insertar datos de prueba en base a la tabla creada
```sql

INSERT INTO peliculas_sebastian (titulo, genero, ano_estreno, duracion, calificacion, clasi, disponible) VALUES
('El Padrino', 'Drama', '1972-03-24', 175.0, 10, 'C', TRUE),
('Matrix', 'Ciencia Ficción', '1999-03-31', 136.0, 9, 'B', TRUE),
('Toy Story', 'Animación', '1995-11-22', 81.0, 8, 'AA', TRUE),
('El Señor de los Anillos: La Comunidad del Anillo', 'Fantasía', '2001-12-19', 178.0, 7, 'B', FALSE),
('Pulp Fiction', 'Crimen', '1994-10-14', 154.0, 7, 'C', TRUE),
('Coco', 'Animación', '2017-11-22', 105.0, 2, 'AA', TRUE),
('Inception', 'Ciencia Ficción', '2010-07-16', 148.0, 2, 'B', TRUE),
('El Caballero de la Noche', 'Acción', '2008-07-18', 152.0, 6, 'B15', FALSE),
('Parásitos', 'Suspenso', '2019-05-30', 132.0, 0, 'D', TRUE),
('La La Land', 'Terror', '2016-12-09', 128.0, 2, 'AA', TRUE),
('Gladiador', 'Acción', '2000-05-05', 155.0, 9, 'B15', TRUE),
('Interstellar', 'Ciencia Ficción', '2014-11-07', 169.0, 10, 'B', TRUE),
('Shrek', 'Animación', '2001-05-18', 90.0, 9, 'AA', TRUE),
('El Club de la Pelea', 'Drama', '1999-10-15', 139.0, 8, 'C', FALSE),
('Spiderman: Into the Spider-Verse', 'Animación', '2018-12-14', 117.0, 9, 'A', TRUE),
('El Resplandor', 'Terror', '1980-05-23', 146.0, 8, 'C', TRUE),
('Forrest Gump', 'Drama', '1994-07-06', 142.0, 10, 'B', TRUE),
('Psycho', 'Suspenso', '1960-09-08', 109.0, 9, 'B15', FALSE),
('Avengers: Endgame', 'Acción', '2019-04-26', 181.0, 8, 'B', TRUE),
('Viaje de Chihiro', 'Animación', '2001-07-20', 125.0, 9, 'AA', TRUE);
```

## Funciones de SELECT 
Se usan diferentes maneras de utilizar SELECT dependiendo de las necesidades y de lo que se este buscando
```sql
SELECT * FROM peliculas_sebastian;
SELECT titulo, genero, ano_estreno FROM peliculas_sebastian;
SELECT * FROM peliculas_sebastian WHERE disponible = 1;
SELECT * FROM peliculas_sebastian WHERE genero = 'Suspenso';
SELECT * FROM peliculas_sebastian WHERE ano_estreno > '2015-01-01';
SELECT * FROM peliculas_sebastian WHERE calificacion > 8;
SELECT * FROM peliculas_sebastian ORDER BY ano_estreno ASC;
SELECT * FROM peliculas_sebastian ORDER BY calificacion DESC LIMIT 1;
```

## Funciones adicionales
Se utilizan las funciones AVG() y COUNT() para el promedio y un conteo respectivamente.
```sql
SELECT AVG(duracion) as Promedio_duracion FROM peliculas_sebastian;
SELECT COUNT(genero) as total_genero, genero FROM peliculas_sebastian GROUP BY genero;
```

## LIKE
Se usa LIKE como condicion flexible ya que permite buscar por palabras que contengan una letra o numero
```sql
SELECT * FROM peliculas_sebastian WHERE genero LIKE 'A%';
```


## UPDATE
Se usa UPDATE para la modificacion de elementos en base a una condicion
```sql
UPDATE peliculas_sebastian SET disponible = 'FALSE' WHERE titulo = 'Matrix';
```
