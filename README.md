
# SQL_SERVER
Using system tables for identification property coluns and cells.

This instruction for use the generate dictionary off date in SQL Server.

------------------------------------

SELECT
  S.name AS 'Schema',
  T.name AS Tabela,
  C.name AS Coluna,
  TY.name AS Tipo,
  C.max_length AS 'Tamanho Máximo', -- Tamanho em bytes, para nvarchar normalmente se divide este valor por 2
  C.precision AS 'Precisão', -- Para tipos numeric e decimal (tamanho)
  C.scale AS 'Escala' -- Para tipos numeric e decimal (números após a virgula)
  ,*
FROM sys.columns C
INNER JOIN sys.tables T
  ON T.object_id = C.object_id
INNER JOIN sys.types TY
  ON TY.user_type_id = C.user_type_id
LEFT JOIN sys.schemas S
  ON T.schema_id = S.schema_id
  ------------------------------------------




This is use for loop in registers the table 
FOR _table2 in (SELECT ID FROM tb_2 WHERE NOME = 'AAA')

LOOP

   INSERT INTO tb_3 (tb_1_id,tb_2_id) VALUES(SELECT MAX(ID) FROM tb_1,_table2.id)

END LOOP;
