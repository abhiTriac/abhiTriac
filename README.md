CREATE TABLE `tbl_role_access` (
    `id` int NOT NULL AUTO_INCREMENT PRIMARY KEY,
    `role_id` varchar(255) DEFAULT NULL,
    `access` varchar(255) DEFAULT NULL,
    `access_type` varchar(255) DEFAULT NULL,
    `institution_id` INT NOT NULL,
    `tab` null
);
CREATE TABLE `tbl_roles` (
    `id` int NOT NULL AUTO_INCREMENT PRIMARY KEY,
    `role_name` varchar(255) DEFAULT NULL,
    `institution_id` INT NOT NULL
);

CREATE TABLE `tbl_user_role` (
    `user_id` INT NOT NULL,
    `role_id` INT NOT NULL,
    PRIMARY KEY (user_id, role_id),
    UNIQUE KEY unique_user_role (user_id, role_id)
);
