# Flight Path Analysis

## Creating the Flight Tables

```
-- CREATING THE TABLES
CREATE SCHEMA path_analysis;

DROP TABLE path_analysis.path_series;

CREATE TABLE path_analysis.path_series		
(		
	id	INT
,	path	VARCHAR
,	sequence	INT
, 	sequence_1 INT
)		
DISTRIBUTE BY HASH (id)		
;		

INSERT INTO path_analysis.path_series VALUES	
	(0,'Belgium',1,1)
,	(0,'Argentina',2,2)
,	(0,'Finland',3,3)
,	(0,'Argentina',4,4)
,	(0,'Slovakia',5,5)
,	(1,'Indonesia',1,1)
,	(1,'Morocco',2,2)
,	(2,'Argentina',1,1)
,	(2,'Finland',2,1)
,	(3,'India',1,1)
,	(4,'Slovakia',1,1)
,	(4,'Taiwan',2,2)
,	(4,'Switzerland',3,2)
,	(4,'Estonia',4,2)
,	(5,'Netherlands',1,1)
,	(5,'Chile',2,2)
,	(6,'Slovakia',1,1)
,	(6,'United Kingdom',2,2)
,	(6,'Italy',3,3)
,	(6,'Morocco',4,4)
,	(6,'Brazil',5,4)
,	(7,'Germany',1,1)
,	(7,'Italy',2,1)
,	(7,'Taiwan',3,2)
,	(8,'Latvia',1,1)
,	(8,'Lithuania',2,2)
,	(8,'Slovenia',3,3)
,	(8,'Latvia',4,4)
,	(8,'Estonia',5,5)
,	(8,'Chile',6,6)
,	(8,'Brazil',7,7)
,	(8,'Taiwan',8,8)
,	(8,'Brazil',9,9)
,	(8,'US',10,10)
,	(8,'New Zealand',11,11)
,	(8,'Malta',12,12)
,	(8,'Canada',13,12)
,	(8,'Netherlands',14,13)
,	(9,'Malaysia',1,1)
,	(9,'Australia',2,2)
,	(9,'Netherlands',3,3)
,	(9,'Germany',4,4)
,	(9,'Morocco',5,5)
,	(10,'Portugal',1,1)
,	(10,'United Kingdom',2,2)
,	(11,'Portugal',1,1)
,	(11,'US',2,2)
,	(11,'Canada',3,3)
,	(11,'Chile',4,4)
,	(11,'Spain',5,4)
,	(11,'Poland',6,5)
,	(11,'Malta',7,6)
,	(11,'Indonesia',8,7)
,	(11,'Spain',9,8)
,	(12,'Greece',1,1)
,	(13,'Spain',1,1)
,	(13,'Mexico',2,1)
,	(13,'Portugal',3,2)
,	(13,'Estonia',4,3)
,	(14,'Switzerland',1,1)
,	(14,'Peru',2,1)
,	(14,'Mexico',3,1)
,	(15,'Philippines',1,1)
,	(15,'Philippines',2,1)
,	(15,'Spain',3,1)
,	(15,'Lithuania',4,1)
,	(15,'New Zealand',5,1)
,	(15,'India',6,2)
,	(16,'US',1,1)
,	(16,'Slovakia',2,2)
,	(16,'Indonesia',3,3)
,	(16,'Brazil',4,4)
,	(16,'Germany',5,5)
,	(16,'Peru',6,6)
,	(16,'Poland',7,6)
,	(16,'Malta',8,7)
,	(17,'Philippines',1,1)
,	(17,'Greece',2,2)
,	(17,'Chile',3,2)
,	(17,'Estonia',4,3)
,	(17,'Taiwan',5,3)
,	(18,'Portugal',1,1)
,	(18,'United Kingdom',2,1)
,	(19,'Malaysia',1,1)
,	(19,'Malaysia',2,2)
,	(19,'Philippines',3,2)
,	(19,'Croatia',4,3)
,	(19,'Turkey',5,4)
,	(19,'Austria',6,4)
,	(19,'New Zealand',7,5)
,	(19,'Brazil',8,5)
,	(19,'Brazil',9,6)
,	(20,'Peru',1,1)
,	(20,'United Kingdom',2,2)
,	(20,'Brazil',3,3)
,	(20,'Austria',4,4)
,	(20,'Greece',5,4)
,	(20,'Estonia',6,5)
,	(20,'Romania',7,5)
,	(20,'Estonia',8,6)
,	(20,'New Zealand',9,6)
,	(20,'Malta',10,7)
,	(21,'Canada',1,1)
,	(21,'Austria',2,1)
,	(21,'Slovakia',3,1)
,	(21,'Australia',4,1)
,	(21,'Romania',5,2)
,	(21,'Slovakia',6,2)
,	(21,'Lithuania',7,2)
,	(21,'Portugal',8,2)
,	(21,'Spain',9,3)
,	(22,'Australia',1,1)
,	(22,'Switzerland',2,1)
,	(22,'Malaysia',3,2)
,	(22,'Brazil',4,3)
,	(22,'Indonesia',5,4)
,	(23,'Germany',1,1)
,	(24,'US',1,1)
,	(24,'Spain',2,1)
,	(25,'Chile',1,1)
,	(25,'Morocco',2,1)
,	(26,'Morocco',1,1)
,	(26,'Spain',2,2)
,	(26,'Greece',3,3)
,	(27,'Portugal',1,1)
,	(28,'Latvia',1,1)
,	(28,'Malta',2,1)
,	(28,'Mexico',3,1)
,	(28,'Taiwan',4,2)
,	(29,'Estonia',1,1)
,	(29,'Mexico',2,1)
,	(29,'Estonia',3,1)
,	(30,'Indonesia',1,1)
,	(31,'France',1,1)
,	(31,'Mexico',2,2)
,	(31,'Malta',3,3)
,	(32,'Greece',1,1)
,	(32,'Japan',2,2)
,	(32,'Greece',3,3)
,	(32,'United Kingdom',4,3)
,	(32,'New Zealand',5,3)
,	(33,'Malta',1,1)
,	(34,'Philippines',1,1)
,	(34,'Lithuania',2,2)
,	(34,'Serbia',3,2)
,	(34,'Australia',4,3)
,	(34,'Indonesia',5,3)
,	(34,'Romania',6,4)
,	(34,'Brazil',7,5)
,	(35,'Italy',1,1)
,	(35,'Japan',2,2)
,	(36,'Taiwan',1,1)
,	(36,'Philippines',2,1)
,	(36,'Philippines',3,1)
,	(36,'Slovenia',4,2)
,	(36,'Peru',5,3)
,	(36,'Romania',6,4)
,	(36,'Chile',7,5)
,	(36,'Latvia',8,6)
,	(36,'Mexico',9,7)
,	(36,'United Kingdom',10,7)
,	(36,'Belgium',11,8)
,	(36,'Estonia',12,8)
,	(36,'France',13,9)
,	(36,'Spain',14,9)
,	(36,'Chile',15,10)
,	(36,'Morocco',16,10)
,	(37,'Portugal',1,1)
,	(38,'Germany',1,1)
,	(39,'Indonesia',1,1)
,	(39,'Morocco',2,1)
,	(39,'Croatia',3,2)
,	(39,'Slovakia',4,3)
,	(39,'Peru',5,3)
,	(39,'Germany',6,4)
,	(39,'France',7,4)
,	(39,'Greece',8,4)
,	(39,'Chile',9,5)
,	(39,'Japan',10,5)
,	(39,'Mexico',11,6)
,	(39,'United Kingdom',12,7)
,	(39,'Greece',13,8)
,	(39,'Lithuania',14,9)
,	(39,'Spain',15,10)
,	(39,'Netherlands',16,11)
,	(40,'Romania',1,1)
,	(40,'Turkey',2,1)
,	(40,'Romania',3,2)
,	(40,'Morocco',4,3)
,	(40,'Slovenia',5,3)
,	(40,'Taiwan',6,3)
,	(40,'Germany',7,3)
,	(40,'Finland',8,4)
,	(41,'United Kingdom',1,1)
,	(41,'Indonesia',2,2)
,	(41,'Australia',3,2)
,	(41,'Greece',4,2)
,	(42,'Lithuania',1,1)
,	(42,'Turkey',2,2)
,	(42,'Taiwan',3,3)
,	(43,'Netherlands',1,1)
,	(43,'Estonia',2,2)
,	(43,'Latvia',3,2)
,	(43,'Finland',4,3)
,	(43,'Portugal',5,4)
,	(43,'Canada',6,5)
,	(43,'Switzerland',7,5)


INSERT INTO path_analysis.path_series VALUES	
	(0,'a',1)
,	(0,'b',2)
,	(0,'c',3)
,	(0,'d',4)
,	(1,'a',1)
,	(1,'b',2)
,	(1,'d',3)
,	(2,'a',1)
,	(2,'c',2)
,	(2,'d',3)
,	(2,'e',4)
,	(2,'f',5)
;
```
## Top Destinations

```
-- Top Destinations
SELECT path, COUNT(*) FROM path_analysis.path_series
GROUP BY 1 ORDER BY 2 DESC
```

## Basic Flight Paths (Nonoverlapping)

```
-- CREATE BASIC PATH

SELECT * FROM npath		
	(	
	on path_analysis.path_series
	PARTITION BY id
	ORDER BY sequence	
	MODE(nonoverlapping)	
	PATTERN('X*')	
	SYMBOLS(TRUE as X)	
	RESULT	
		(
		first(id of ANY(X)) as id,
		accumulate(path of ANY(X)) as path,
		count(* of ANY(X)) as cnt
		)
	)	
	ORDER BY cnt DESC	
; 		

## Basic Flight Paths (overlapping)

-- CREATE BASIC PATH

SELECT * FROM npath		
	(	
	on path_analysis.path_series
	PARTITION BY id
	ORDER BY sequence	
	MODE(overlapping)	
	PATTERN('X*')	
	SYMBOLS(TRUE as X)	
	RESULT	
		(
		first(id of ANY(X)) as id,
		accumulate(path of ANY(X)) as path,
		count(* of ANY(X)) as cnt
		)
	)	
	ORDER BY cnt DESC	
; 		
```

## Get path from Philippines


```
-- PATH FROM 'Philippines'

SELECT * FROM npath		
	(	
	on path_analysis.path_series
	PARTITION BY id
	ORDER BY sequence	
	MODE(overlapping)	
	PATTERN('X.*Y')	
	SYMBOLS(path = 'Philippines' as X, TRUE as Y)	
	RESULT	
		(
		first(id of ANY(X,Y)) as id,
		accumulate(path of ANY(X,Y)) as path,
		count(* of ANY(X,Y)) as cnt
		)
	)	
	ORDER BY cnt DESC	
; 		

## Get path to Philippines
```

-- PATH TO 'Philippines'

SELECT * FROM npath		
	(	
	on path_analysis.path_series
	PARTITION BY id
	ORDER BY sequence	
	MODE(overlapping)	
	PATTERN('Y*.X')	
	SYMBOLS(path = 'Philippines' as X, TRUE as Y)	
	RESULT	
		(
		first(id of ANY(X,Y)) as id,
		accumulate(path of ANY(X,Y)) as path,
		count(* of ANY(X,Y)) as cnt
		)
	)	
	ORDER BY cnt DESC	
; 		
```

## Any 3 destinations

```
-- CREATE ANY 3 DESTINATION OVERLAPPING

SELECT * FROM npath		
	(	
	on path_analysis.path_series
	PARTITION BY id
	ORDER BY sequence	
	MODE(overlapping)	
	PATTERN('X.X.X')	
	SYMBOLS(TRUE as X)	
	RESULT	
		(
		first(id of ANY(X)) as id,
		accumulate(path of ANY(X)) as path,
		count(* of ANY(X)) as cnt
		)
	)	
	ORDER BY cnt DESC	
; 		

## 3 Destinations from Philippines

```
-- CREATE ANY 3 DESTINATION FROM 'Philippines'

SELECT * FROM npath		
	(	
	on path_analysis.path_series
	PARTITION BY id
	ORDER BY sequence	
	MODE(nonoverlapping)	
	PATTERN('Y.X.X')	
	SYMBOLS(TRUE as X, path = 'Philippines' as Y)	
	RESULT	
		(
		first(id of ANY(X, Y)) as id,
		accumulate(path of ANY(X, Y)) as path,
		count(* of ANY(X, Y)) as cnt
		)
	)	
	ORDER BY cnt DESC	
; 		
```

## Any 3 destinations to Philippines

```
-- CREATE ANY 3 DESTINATION TO 'Philippines'

SELECT * FROM npath		
	(	
	on path_analysis.path_series
	PARTITION BY id
	ORDER BY sequence	
	MODE(nonoverlapping)	
	PATTERN('X.X.Y')	
	SYMBOLS(TRUE as X, path = 'Philippines' as Y)	
	RESULT	
		(
		first(id of ANY(X, Y)) as id,
		accumulate(path of ANY(X, Y)) as path,
		count(* of ANY(X, Y)) as cnt
		)
	)	
	ORDER BY cnt DESC	
; 		
```

## Any destination from and to Estonia

```
-- CREATE ANY DESTINATIONS BETWEEN 'Estonia'

SELECT * FROM npath		
	(	
	on path_analysis.path_series
	PARTITION BY id
	ORDER BY sequence	
	MODE(overlapping)	
	PATTERN('Y.X.Y')	
	SYMBOLS(TRUE as X, path = 'Estonia' as Y)	
	RESULT	
		(
		first(id of ANY(X, Y)) as id,
		accumulate(path of ANY(X, Y)) as path,
		count(* of ANY(X, Y)) as cnt
		)
	)	
	ORDER BY cnt DESC	
; 		
```