# FantaSanremo

## Possibili combinazioni di squadre senza considerare i baudi
- N° squadre: 30
- Elementi in squadra: 5

Calcolo del Coefficiente binomiale 30 su 5

#142506#

## Possibili combinazioni di squadre considerando i baudi <= 100

```SQL
CREATE TABLE dbo.Fantasanremo
(
  id int NOT NULL IDENTITY(1, 1),
  name  VARCHAR(20)     NOT NULL,
  baudi int NOT NULL,  
  CONSTRAINT PK_Fantasanremo PRIMARY KEY(id)
);
GO

INSERT INTO dbo.Fantasanremo VALUES
('Alessandra Amoroso', 23),
('Alfa', 20),
('Angelina Mango', 23),
('Annalisa', 23),
('BigMama', 17),
('bnkr44', 16),
('CLARA', 16),
('Dargen D''Amico', 22),
('Diodato', 21),
('Emma', 23),
('Fiorella Mannoia', 20),
('Fred De Palma', 18),
('Gazzelle', 19),
('Geolier', 22),
('Ghali', 20),
('Il Tre', 17),
('Il Volo', 20),
('Irama', 19),
('La Sad', 19),
('Loredana Bertè', 18),
('Mahmood', 21),
('Mannini', 17),
('Mr.Rain', 21),
('Negramaro', 22),
('Renga e Nek', 20),
('Ricchi e Poveri', 18),
('Rose Villain', 19),
('sangiovanni', 21),
('SANTI FRANCESI', 16),
('The Kolors', 22)
GO

SELECT A.name, B.name, C.name, D.name, E.name, A.baudi + B.baudi + C.baudi + D.baudi + E.baudi AS Somma
from dbo.Fantasanremo AS A
CROSS JOIN dbo.Fantasanremo AS B
CROSS JOIN dbo.Fantasanremo AS C
CROSS JOIN dbo.Fantasanremo AS D
CROSS JOIN dbo.Fantasanremo AS E
WHERE A.id < B.id AND C.id < A.id AND D.id < c.id AND E.id < D.id 
AND (A.baudi + B.baudi + C.baudi + D.baudi + E.baudi) <= 100
```

#90503#

## Possibili combinazioni di squadre considerando i baudi = 100
Come query precedente con clausola `AND (A.baudi + B.baudi + C.baudi + D.baudi + E.baudi) = 100`

#11780#