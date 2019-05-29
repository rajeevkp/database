# mysql database ** with multiple TIMESTAMP

CREATE TABLE GeoIP(
	id int auto_increment primary key,
	subnet_ip varchar(35),
	country_name varchar(20),
	state_name varchar(20),
	city_name varchar(20),
	latitude varchar(20),
	longitude varchar(20),
	country_code varchar(10),
	state_code varchar(10),
	city_code varchar(10),
	continent_code varchar(10),
	created_at TIMESTAMP,
	updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
	deleted_at TIMESTAMP NULL
);



