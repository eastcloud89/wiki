# mysql to rds
	sudo mysqldump -u [userId] --databases [db] 
	--single-transaction --compress --order-by-primary -p'[local_pasword]' | 
	mysql -u [userId] --port=3306 --host=[endpoint] -p'[password]'