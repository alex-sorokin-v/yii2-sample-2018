Используя Yii2 необходимо реализовать форму регистрации пользователя с условием типа физ./юр. лицо. 
Для физ. лица необходимо заполнить: почту, ФИО и в случае ИП - ИНН, а для юр. лица: почту, ФИО, название организации и инн.
Внешний вид значения не имеет.

Таблицы доступны в миграциях.

CREATE TABLE `customer` (
	`id` INT(10) UNSIGNED NOT NULL AUTO_INCREMENT,
	`firstName` VARCHAR(255) NULL DEFAULT '0',
	`secondName` VARCHAR(255) NULL DEFAULT '0',
	`lastName` VARCHAR(255) NULL DEFAULT '0',
	`email` VARCHAR(255) NULL DEFAULT '0',
	PRIMARY KEY (`id`),
	UNIQUE INDEX `idx_email` (`email`)
)
ENGINE=InnoDB;

CREATE TABLE `customer_type` (
	`id` INT(10) UNSIGNED NOT NULL AUTO_INCREMENT,
	`customerId` INT(10) UNSIGNED NULL DEFAULT '0',
	`customerType` TINYINT(3) UNSIGNED NULL DEFAULT '0',
	`inn` VARCHAR(255) NULL DEFAULT '0',
	`companyName` VARCHAR(255) NULL DEFAULT '0',
	PRIMARY KEY (`id`)
)
ENGINE=InnoDB;