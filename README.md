CREATE TABLE `tbl_roles` (
    `id` int NOT NULL AUTO_INCREMENT PRIMARY KEY,
    `role_name` varchar(255) DEFAULT NULL,
    `institution_id` INT NOT NULL
);

ALTER TABLE tbl_roles
ADD CONSTRAINT fk_institution_roles FOREIGN KEY (institution_id) REFERENCES tbl_institution_profile (pro_id);
