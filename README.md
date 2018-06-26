# SQL_SERVER

This is use for loop in registers the table 
FOR _table2 in (SELECT ID FROM tb_2 WHERE NOME = 'AAA')

LOOP

   INSERT INTO tb_3 (tb_1_id,tb_2_id) VALUES(SELECT MAX(ID) FROM tb_1,_table2.id)

END LOOP;
