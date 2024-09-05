CREATE TABLE `tbl_role_access` (
    `id` int NOT NULL AUTO_INCREMENT PRIMARY KEY,
    `role_id` varchar(255) DEFAULT NULL,
    `access` varchar(255) DEFAULT NULL,
    `access_type` varchar(255) DEFAULT NULL,
    `institution_id` INT NOT NULL,
    ``
);
