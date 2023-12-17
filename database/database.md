# Database

## { First Version }

 

```sql
-- Criação e utilização do Database.

CREATE DATABASE PI_BAH;

USE PI_BAH;

-- Criação da tabela 'users'

CREATE TABLE users (
	userID INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
	user_name VARCHAR(50) NOT NULL,
	address VARCHAR(50) NOT NULL,
	phone_number VARCHAR(11) NOT NULL,
	cpf VARCHAR(11) NOT NULL UNIQUE,
	registration_date DATETIME NOT NULL
	);
	
-- Criação da tabela 'emergency_requests'	
	
CREATE TABLE emergency_requests (
	requestID INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
	userID INT NOT NULL,
	request_time DATETIME NOT NULL,
  notification_message TEXT NOT NULL,
	latitude DOUBLE NOT NULL,
	longitude DOUBLE NOT NULL,
	statusID INT NOT NULL,
	FOREIGN KEY (userID) REFERENCES users (userID),
	FOREIGN KEY (statusID) REFERENCES emergency_request_status (statusID)
	);
	
-- Criação da tabela 'contacts'	
	
CREATE TABLE contacts (
	contactID INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
	userID INT NOT NULL,
	contact_name VARCHAR(50) NOT NULL,
	contact_phone VARCHAR(11) NOT NULL,
  contact_type ENUM('Familiar', 'Amigo', 'Vizinho'),
	FOREIGN KEY (userID) REFERENCES users (userID)
	);
	
f-- Criação da tabela 'emergency_request_status'	
	
CREATE TABLE emergency_request_status (
	statusID	INT NOT null AUTO_INCREMENT PRIMARY KEY,
	status_name ENUM('Concluído', 'Não Concluído', 'Em andamento', 'Cancelado')
	);	
	
-- População de todas as tabelas

INSERT INTO users (user_name, adress, phone_number, cpf, registration_date) VALUES
	('Mateus Cardozo', 'Rua A, 123', '987654321', '12345678901', '2023-08-14 10:00:00'),
	('Stefani Sebolt', 'Avenida B, 456', '987123456', '98765432101', '2023-08-14 11:30:00');
	
INSERT INTO emergency_requests (userID, request_time, latitude, longitude, emergency_service, statusID) VALUES
	(1, '2023-08-14 12:00:00', -23.5505, -46.6333, 'Ambulance', 1),
	(2, '2023-08-14 13:15:00', -23.5607, -46.6504, 'Police', 2);
	
INSERT INTO contacts (userID, contact_name, contact_phone, contact_type) VALUES
	(1, 'João Luís', '987654321', 'Amigo'),
	(1, 'Júlio Machado', '987987654', 'Familiar'),
	(2, 'Juliana Machado', '987111222', 'Amigo'),
	(2, 'Taila Martins', '987222333', 'Familiar');
	
INSERT INTO emergency_request_status (status_name) VALUES
	('Pendente'),
	('Em Processamento'),
	('Concluído'),
	('Cancelado');
	

```

## { NEW VERSION }

```sql
-- Criação e utilização do Database.

CREATE DATABASE PI_BAH;

USE PI_BAH;

-- Criação da tabela 'users'

CREATE TABLE users (
	userID INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
	user_name VARCHAR(50) NOT NULL,
	address VARCHAR(50) NOT NULL,
	phone_number VARCHAR(11) NOT NULL,
	cpf VARCHAR(11) NOT NULL UNIQUE,
	registration_date DATETIME NOT NULL
	);

-- Criação da tabela 'emergency_request_status'	
	
CREATE TABLE emergency_request_status (
	statusID	INT NOT null AUTO_INCREMENT PRIMARY KEY,
	status_name ENUM('Concluído', 'Não Concluído', 'Em andamento', 'Cancelado')
	);	
	
-- Criação da tabela 'emergency_requests'	
	
CREATE TABLE emergency_requests (
	requestID INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
	userID INT NOT NULL,
	request_time DATETIME NOT NULL,
  notification_message TEXT NOT NULL,
	latitude DOUBLE NOT NULL,
	longitude DOUBLE NOT NULL,
	statusID INT NOT NULL,
	FOREIGN KEY (userID) REFERENCES users (userID),
	FOREIGN KEY (statusID) REFERENCES emergency_request_status (statusID)
	);
	
-- Criação da tabela 'contacts'	
	
CREATE TABLE contacts (
	contactID INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
	userID INT NOT NULL,
	contact_name VARCHAR(50) NOT NULL,
	contact_phone VARCHAR(11) NOT NULL,
  contact_type ENUM('Familiar', 'Amigo', 'Vizinho'),
	FOREIGN KEY (userID) REFERENCES users (userID)
	);
	
```