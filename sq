-- MySQL dump 10.13  Distrib 8.0.36, for Win64 (x86_64)
--
-- Host: localhost    Database: real_trac_db
-- ------------------------------------------------------
-- Server version	8.0.36

-- drop database real_trac_db;

create database real_trac_db;

use real_trac_db;

/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */
;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */
;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */
;
/*!50503 SET NAMES utf8 */
;
/*!40103 SET @OLD_TIME_ZONE=@@TIME_ZONE */
;
/*!40103 SET TIME_ZONE='+00:00' */
;
/*!40014 SET @OLD_UNIQUE_CHECKS=@@UNIQUE_CHECKS, UNIQUE_CHECKS=0 */
;
/*!40014 SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0 */
;
/*!40101 SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='NO_AUTO_VALUE_ON_ZERO' */
;
/*!40111 SET @OLD_SQL_NOTES=@@SQL_NOTES, SQL_NOTES=0 */
;

--
-- Table structure for table `tbl_accounts`
--

DROP TABLE IF EXISTS `tbl_accounts`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_accounts` (
    `acc_id` int NOT NULL AUTO_INCREMENT,
    `acc_name` varchar(255) NOT NULL,
    `acc_type_id` varchar(50) NOT NULL,
    `acc_type_name` varchar(255) DEFAULT NULL,
    `acc_code` varchar(100) DEFAULT NULL,
    `party_type` enum(
        'general',
        'wholesaler',
        'retailer',
        'distributor',
        'no',
        'corporate'
    ) NOT NULL DEFAULT 'no',
    `location_id` int NOT NULL DEFAULT '0',
    `acc_type_label` varchar(255) DEFAULT NULL,
    `institution_name` varchar(255) DEFAULT NULL,
    `address` text,
    `contact_no` varchar(100) DEFAULT NULL,
    `email_address` varchar(255) DEFAULT NULL,
    `opening_balance` double NOT NULL DEFAULT '0',
    `credit_limit` double NOT NULL DEFAULT '0',
    `bank_acc_number` varchar(255) DEFAULT NULL,
    `bank_acc_name` varchar(255) DEFAULT NULL,
    `bank_branch` varchar(255) DEFAULT NULL,
    `bank_acc_type` varchar(25) DEFAULT NULL,
    `creation_date` varchar(30) DEFAULT NULL,
    `create_by` int NOT NULL DEFAULT '0',
    `branch_id` int NOT NULL,
    `status` enum('a', 'd', 'r', 'p') NOT NULL DEFAULT 'a',
    `employee_id` int NOT NULL DEFAULT '0',
    `conversation` text,
    `profession` varchar(255) DEFAULT NULL,
    `expectation_per` varchar(10) DEFAULT NULL,
    `contact_person` varchar(50) DEFAULT NULL,
    `group_id` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`acc_id`)
) ENGINE = InnoDB AUTO_INCREMENT = 16 DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_accounts`
--

LOCK TABLES `tbl_accounts` WRITE;
/*!40000 ALTER TABLE `tbl_accounts` DISABLE KEYS */
;

INSERT INTO
    `tbl_accounts`
VALUES (
        1,
        'Discount on sale',
        'direct_expense',
        'Direct Expense',
        NULL,
        'no',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        0,
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        1,
        1,
        'a',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        0
    ),
    (
        2,
        'Discount on service',
        'direct_expense',
        'Direct Expense',
        NULL,
        'no',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        0,
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        1,
        1,
        'a',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        0
    ),
    (
        3,
        'Transport Cost on Purchase',
        'direct_expense',
        'Direct Expense',
        NULL,
        'no',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        0,
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        1,
        1,
        'a',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        0
    ),
    (
        4,
        'Sales',
        'sale_account',
        'Sales Accounts',
        NULL,
        'no',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        0,
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        1,
        1,
        'a',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        0
    ),
    (
        5,
        'Sales Return',
        'sale_return',
        'Sales Return',
        NULL,
        'no',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        0,
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        1,
        1,
        'a',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        0
    ),
    (
        6,
        'Discount on purchase',
        'direct_income',
        'Direct Incomes',
        NULL,
        'no',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        0,
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        1,
        1,
        'a',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        0
    ),
    (
        7,
        'Transport Cost on Sales ',
        'direct_income',
        'Direct Incomes',
        NULL,
        'no',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        0,
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        1,
        1,
        'a',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        0
    ),
    (
        8,
        'Vat & Tax Account',
        'dutie_&_tax',
        'Duties & Taxes',
        NULL,
        'no',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        0,
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        1,
        1,
        'a',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        0
    ),
    (
        9,
        'Purchase',
        'purchase_account',
        'Purchase Accounts',
        NULL,
        'no',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        0,
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        1,
        1,
        'a',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        0
    ),
    (
        10,
        'Purchase Return',
        'purchase_return',
        'Purchases Return',
        NULL,
        'no',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        0,
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        1,
        1,
        'a',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        0
    ),
    (
        11,
        'Salary',
        'indirect_expense',
        'Salary',
        NULL,
        'no',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        0,
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        1,
        1,
        'a',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        0
    ),
    (
        12,
        'Cash',
        'cash_in_hand',
        'Cash-in-Hand',
        NULL,
        'no',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        0,
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        1,
        1,
        'a',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        0
    ),
    (
        13,
        'Capital Account',
        'capital',
        'Capital',
        NULL,
        'no',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        0,
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        1,
        1,
        'a',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        0
    ),
    (
        14,
        'Services Account',
        'service_account',
        'Services Account',
        NULL,
        'no',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        0,
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        1,
        1,
        'a',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        0
    ),
    (
        15,
        'Service Expense Account',
        'service_expense_account',
        'Service Expense Account',
        NULL,
        'no',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        0,
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        NULL,
        1,
        1,
        'a',
        0,
        NULL,
        NULL,
        NULL,
        NULL,
        0
    );
/*!40000 ALTER TABLE `tbl_accounts` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_adjustment_details`
--

DROP TABLE IF EXISTS `tbl_adjustment_details`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_adjustment_details` (
    `adjust_d_id` int NOT NULL AUTO_INCREMENT,
    `adjust_id` int NOT NULL,
    `item_id` int NOT NULL DEFAULT '0',
    `warehouse_id` int NOT NULL DEFAULT '0',
    `item_qty` double NOT NULL DEFAULT '0',
    `retail_qty` double NOT NULL DEFAULT '0',
    `item_rate` text NOT NULL,
    `adjust_qty` double NOT NULL DEFAULT '0',
    `adjust_rate` text NOT NULL,
    `adjust_type` enum('add_stock', 'damage_stock') NOT NULL,
    `item_total` double NOT NULL DEFAULT '0',
    `serials` text,
    `created_date` varchar(30) DEFAULT NULL,
    `branch_id` int NOT NULL,
    `status` enum('a', 'd', 'p') NOT NULL DEFAULT 'a',
    `per_unit_id` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`adjust_d_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_adjustment_details`
--

LOCK TABLES `tbl_adjustment_details` WRITE;
/*!40000 ALTER TABLE `tbl_adjustment_details` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_adjustment_details` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_adjustment_master`
--

DROP TABLE IF EXISTS `tbl_adjustment_master`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_adjustment_master` (
    `adjust_id` int NOT NULL AUTO_INCREMENT,
    `adjust_voucher_no` varchar(100) DEFAULT NULL,
    `is_serial` enum('yes', 'no') NOT NULL,
    `sub_total` double NOT NULL DEFAULT '0',
    `total_amount` double NOT NULL DEFAULT '0',
    `created_date` varchar(30) DEFAULT NULL,
    `narration` text,
    `created_by` int NOT NULL DEFAULT '0',
    `branch_id` int NOT NULL,
    `status` enum('a', 'd', 'p') NOT NULL DEFAULT 'a',
    PRIMARY KEY (`adjust_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_adjustment_master`
--

LOCK TABLES `tbl_adjustment_master` WRITE;
/*!40000 ALTER TABLE `tbl_adjustment_master` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_adjustment_master` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_advance_transactions`
--

DROP TABLE IF EXISTS `tbl_advance_transactions`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_advance_transactions` (
    `tran_id` int NOT NULL AUTO_INCREMENT,
    `acc_id` int NOT NULL,
    `tran_acc_id` int NOT NULL,
    `tran_type` enum('payment', 'receive') NOT NULL,
    `acc_type` enum('debitor', 'creditor') NOT NULL,
    `tran_date` varchar(30) NOT NULL,
    `tran_amount` double NOT NULL DEFAULT '0',
    `created_by` int NOT NULL,
    `branch_id` int NOT NULL,
    `tran_status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `narration` text,
    PRIMARY KEY (`tran_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_advance_transactions`
--

LOCK TABLES `tbl_advance_transactions` WRITE;
/*!40000 ALTER TABLE `tbl_advance_transactions` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_advance_transactions` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_branch_transactions`
--

DROP TABLE IF EXISTS `tbl_branch_transactions`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_branch_transactions` (
    `tran_id` int NOT NULL AUTO_INCREMENT,
    `tran_date` varchar(30) NOT NULL,
    `tran_code` varchar(100) NOT NULL,
    `to_branch_id` int NOT NULL,
    `from_branch_id` int NOT NULL,
    `branch_id` int NOT NULL,
    `creation_by` int NOT NULL DEFAULT '0',
    `status` enum('a', 'd', 'p') NOT NULL DEFAULT 'p',
    `narration` text,
    `tran_amount` double NOT NULL DEFAULT '0',
    `to_acc_id` int NOT NULL,
    `from_acc_id` int NOT NULL,
    PRIMARY KEY (`tran_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_branch_transactions`
--

LOCK TABLES `tbl_branch_transactions` WRITE;
/*!40000 ALTER TABLE `tbl_branch_transactions` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_branch_transactions` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_branches`
--

DROP TABLE IF EXISTS `tbl_branches`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_branches` (
    `branch_id` int NOT NULL AUTO_INCREMENT,
    `branch_name` varchar(255) NOT NULL,
    `branch_title` text NOT NULL,
    `branch_address` text NOT NULL,
    `branch_created_isodt` varchar(30) DEFAULT NULL,
    `branch_updated_isodt` varchar(30) DEFAULT NULL,
    `branch_created_by` int NOT NULL DEFAULT '0',
    `branch_updated_by` int NOT NULL DEFAULT '0',
    `branch_status` enum(
        'active',
        'deactivated',
        'pending'
    ) DEFAULT 'active',
    PRIMARY KEY (`branch_id`)
) ENGINE = InnoDB AUTO_INCREMENT = 2 DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_branches`
--

LOCK TABLES `tbl_branches` WRITE;
/*!40000 ALTER TABLE `tbl_branches` DISABLE KEYS */
;

INSERT INTO
    `tbl_branches`
VALUES (
        1,
        'RealTrac',
        'RealTrac',
        'Dubai',
        '2024-02-14T18:34:30.722Z',
        NULL,
        1,
        1,
        'active'
    );
/*!40000 ALTER TABLE `tbl_branches` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_categories`
--

DROP TABLE IF EXISTS `tbl_categories`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_categories` (
    `category_id` int NOT NULL AUTO_INCREMENT,
    `category_name` varchar(255) NOT NULL,
    `create_by` int NOT NULL,
    `branch_id` int NOT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    PRIMARY KEY (`category_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_categories`
--

LOCK TABLES `tbl_categories` WRITE;
/*!40000 ALTER TABLE `tbl_categories` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_categories` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_collection_groups`
--

DROP TABLE IF EXISTS `tbl_collection_groups`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_collection_groups` (
    `group_id` int NOT NULL AUTO_INCREMENT,
    `group_name` varchar(255) NOT NULL,
    `employee_ids` text,
    `component_name` varchar(200) NOT NULL,
    `metting_day` varchar(30) DEFAULT NULL,
    `metting_place` text,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `create_by` int NOT NULL,
    `branch_id` int NOT NULL,
    `employee_id` int NOT NULL DEFAULT '0',
    `acc_id` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`group_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_collection_groups`
--

LOCK TABLES `tbl_collection_groups` WRITE;
/*!40000 ALTER TABLE `tbl_collection_groups` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_collection_groups` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_contra_trans`
--

DROP TABLE IF EXISTS `tbl_contra_trans`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_contra_trans` (
    `contra_id` int NOT NULL AUTO_INCREMENT,
    `from_acc_id` int NOT NULL,
    `to_acc_id` int NOT NULL,
    `tran_amount` double NOT NULL DEFAULT '0',
    `narration` text,
    `creation_date` varchar(30) NOT NULL,
    `creation_by` int NOT NULL DEFAULT '0',
    `branch_id` int NOT NULL DEFAULT '0',
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `contra_code` varchar(50) DEFAULT NULL,
    PRIMARY KEY (`contra_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_contra_trans`
--

LOCK TABLES `tbl_contra_trans` WRITE;
/*!40000 ALTER TABLE `tbl_contra_trans` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_contra_trans` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_conversations`
--

DROP TABLE IF EXISTS `tbl_conversations`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_conversations` (
    `id` int NOT NULL AUTO_INCREMENT,
    `customer_id` int NOT NULL,
    `text` text NOT NULL,
    `created_date` varchar(30) DEFAULT NULL,
    `user_id` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_conversations`
--

LOCK TABLES `tbl_conversations` WRITE;
/*!40000 ALTER TABLE `tbl_conversations` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_conversations` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_creditor_pay_details`
--

DROP TABLE IF EXISTS `tbl_creditor_pay_details`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_creditor_pay_details` (
    `pay_d_id` int NOT NULL AUTO_INCREMENT,
    `pay_id` int NOT NULL,
    `from_acc_id` int NOT NULL,
    `to_acc_id` int NOT NULL,
    `discount_amount` double NOT NULL DEFAULT '0',
    `tax_amount` double NOT NULL DEFAULT '0',
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `direct_income_id` int NOT NULL DEFAULT '0',
    `current_liability_id` int NOT NULL DEFAULT '0',
    `pay_amount` double NOT NULL DEFAULT '0',
    `pay_total` double NOT NULL DEFAULT '0',
    `voucher_no` varchar(100) DEFAULT NULL,
    PRIMARY KEY (`pay_d_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_creditor_pay_details`
--

LOCK TABLES `tbl_creditor_pay_details` WRITE;
/*!40000 ALTER TABLE `tbl_creditor_pay_details` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_creditor_pay_details` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_creditor_payments`
--

DROP TABLE IF EXISTS `tbl_creditor_payments`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_creditor_payments` (
    `pay_id` int NOT NULL AUTO_INCREMENT,
    `pay_code` varchar(50) DEFAULT NULL,
    `creation_date` varchar(30) DEFAULT NULL,
    `narration` text,
    `discount_total` double NOT NULL DEFAULT '0',
    `tax_total` double NOT NULL DEFAULT '0',
    `pay_total` double NOT NULL DEFAULT '0',
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `branch_id` int NOT NULL,
    `creation_by` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`pay_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_creditor_payments`
--

LOCK TABLES `tbl_creditor_payments` WRITE;
/*!40000 ALTER TABLE `tbl_creditor_payments` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_creditor_payments` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_debitor_receipt_details`
--

DROP TABLE IF EXISTS `tbl_debitor_receipt_details`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_debitor_receipt_details` (
    `rcv_d_id` int NOT NULL AUTO_INCREMENT,
    `rcv_id` int NOT NULL,
    `from_acc_id` int NOT NULL,
    `into_acc_id` int NOT NULL,
    `discount_amount` double NOT NULL DEFAULT '0',
    `tax_amount` double NOT NULL DEFAULT '0',
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `direct_income_id` int NOT NULL DEFAULT '0',
    `current_liability_id` int NOT NULL DEFAULT '0',
    `rcv_amount` double NOT NULL DEFAULT '0',
    `rcv_total` double NOT NULL DEFAULT '0',
    `voucher_no` varchar(100) DEFAULT NULL,
    `emi_id` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`rcv_d_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_debitor_receipt_details`
--

LOCK TABLES `tbl_debitor_receipt_details` WRITE;
/*!40000 ALTER TABLE `tbl_debitor_receipt_details` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_debitor_receipt_details` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_debitor_receipts`
--

DROP TABLE IF EXISTS `tbl_debitor_receipts`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_debitor_receipts` (
    `rcv_id` int NOT NULL AUTO_INCREMENT,
    `rcv_code` varchar(100) DEFAULT NULL,
    `creation_date` varchar(30) DEFAULT NULL,
    `narration` text,
    `discount_total` double NOT NULL DEFAULT '0',
    `tax_total` double NOT NULL DEFAULT '0',
    `rcv_total` double NOT NULL DEFAULT '0',
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `branch_id` int NOT NULL DEFAULT '0',
    `creation_by` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`rcv_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_debitor_receipts`
--

LOCK TABLES `tbl_debitor_receipts` WRITE;
/*!40000 ALTER TABLE `tbl_debitor_receipts` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_debitor_receipts` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_debtor_collections`
--

DROP TABLE IF EXISTS `tbl_debtor_collections`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_debtor_collections` (
    `coll_id` int NOT NULL AUTO_INCREMENT,
    `acc_id` int NOT NULL DEFAULT '0',
    `created_date` varchar(30) DEFAULT NULL,
    `amount` double NOT NULL DEFAULT '0',
    `created_by` int NOT NULL DEFAULT '0',
    `branch_id` int NOT NULL DEFAULT '0',
    `into_acc_id` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`coll_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_debtor_collections`
--

LOCK TABLES `tbl_debtor_collections` WRITE;
/*!40000 ALTER TABLE `tbl_debtor_collections` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_debtor_collections` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_departments`
--

DROP TABLE IF EXISTS `tbl_departments`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_departments` (
    `id` int NOT NULL AUTO_INCREMENT,
    `name` varchar(255) NOT NULL,
    `created_by` int NOT NULL DEFAULT '0',
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `branch_id` int NOT NULL,
    PRIMARY KEY (`id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_departments`
--

LOCK TABLES `tbl_departments` WRITE;
/*!40000 ALTER TABLE `tbl_departments` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_departments` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_designations`
--

DROP TABLE IF EXISTS `tbl_designations`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_designations` (
    `id` int NOT NULL AUTO_INCREMENT,
    `name` varchar(255) NOT NULL,
    `created_by` int NOT NULL DEFAULT '0',
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `branch_id` int NOT NULL,
    PRIMARY KEY (`id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_designations`
--

LOCK TABLES `tbl_designations` WRITE;
/*!40000 ALTER TABLE `tbl_designations` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_designations` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_emis`
--

DROP TABLE IF EXISTS `tbl_emis`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_emis` (
    `emi_id` int NOT NULL AUTO_INCREMENT,
    `emi_no` varchar(100) NOT NULL,
    `from_date` varchar(30) NOT NULL,
    `last_date` varchar(30) NOT NULL,
    `amount` double NOT NULL DEFAULT '0',
    `cus_id` int NOT NULL DEFAULT '0',
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `branch_id` int NOT NULL,
    `sale_id` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`emi_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_emis`
--

LOCK TABLES `tbl_emis` WRITE;
/*!40000 ALTER TABLE `tbl_emis` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_emis` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_emp_attendance_details`
--

DROP TABLE IF EXISTS `tbl_emp_attendance_details`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_emp_attendance_details` (
    `att_d_id` int NOT NULL AUTO_INCREMENT,
    `attendance` enum(
        'precent',
        'absence',
        'leave_with_pay',
        'leave_without_pay'
    ) NOT NULL,
    `emp_id` int NOT NULL,
    `attendance_date` varchar(30) NOT NULL,
    `month` varchar(10) NOT NULL,
    `month_day` int NOT NULL,
    `year` varchar(4) NOT NULL,
    `branch_id` int NOT NULL,
    PRIMARY KEY (`att_d_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_emp_attendance_details`
--

LOCK TABLES `tbl_emp_attendance_details` WRITE;
/*!40000 ALTER TABLE `tbl_emp_attendance_details` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_emp_attendance_details` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_employee_pay_details`
--

DROP TABLE IF EXISTS `tbl_employee_pay_details`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_employee_pay_details` (
    `pay_d_id` int NOT NULL AUTO_INCREMENT,
    `pay_id` int NOT NULL,
    `to_acc_id` int NOT NULL,
    `pay_type` enum(
        'Basic Salary',
        'Advance Salary',
        'Overtime',
        'Commission',
        'Bonus',
        'Deduction',
        'conveyance',
        'TA',
        'DA',
        'MA'
    ) NOT NULL,
    `pay_amount` double NOT NULL DEFAULT '0',
    `status` enum('a', 'd', 'p') NOT NULL,
    PRIMARY KEY (`pay_d_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_employee_pay_details`
--

LOCK TABLES `tbl_employee_pay_details` WRITE;
/*!40000 ALTER TABLE `tbl_employee_pay_details` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_employee_pay_details` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_employee_pays`
--

DROP TABLE IF EXISTS `tbl_employee_pays`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_employee_pays` (
    `pay_id` int NOT NULL AUTO_INCREMENT,
    `salary_acc_id` int NOT NULL,
    `from_acc_id` int NOT NULL,
    `pay_total` double NOT NULL DEFAULT '0',
    `creation_date` varchar(30) NOT NULL,
    `year` varchar(4) NOT NULL,
    `month` varchar(10) NOT NULL,
    `pay_code` varchar(100) DEFAULT NULL,
    `narration` text,
    `status` enum('a', 'd', 'p') NOT NULL DEFAULT 'a',
    `creation_by` int NOT NULL,
    `branch_id` int NOT NULL,
    PRIMARY KEY (`pay_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_employee_pays`
--

LOCK TABLES `tbl_employee_pays` WRITE;
/*!40000 ALTER TABLE `tbl_employee_pays` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_employee_pays` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_employees`
--

DROP TABLE IF EXISTS `tbl_employees`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_employees` (
    `employee_id` int NOT NULL AUTO_INCREMENT,
    `employee_code` varchar(100) DEFAULT NULL,
    `employee_name` varchar(255) NOT NULL,
    `ifsc_code` varchar(255) DEFAULT NULL,
    `bank_acc_number` varchar(255) DEFAULT NULL,
    `bank_acc_name` varchar(255) DEFAULT NULL,
    `bank_branch` varchar(255) DEFAULT NULL,
    `zip_code` varchar(255) DEFAULT NULL,
    `present_address` text,
    `permanent_address` text,
    `contact_no` varchar(100) DEFAULT NULL,
    `joining_date` varchar(30) DEFAULT NULL,
    `email_address` varchar(100) DEFAULT NULL,
    `gender_type` enum(
        'male',
        'fmale',
        'others',
        'no'
    ) NOT NULL,
    `marital_type` enum('single', 'married', 'no') NOT NULL,
    `basic_salary` double NOT NULL DEFAULT '0',
    `national_id_no` varchar(255) DEFAULT NULL,
    `father_name` varchar(255) DEFAULT NULL,
    `mother_name` varchar(255) DEFAULT NULL,
    `department_id` int NOT NULL DEFAULT '0',
    `designation_id` int NOT NULL DEFAULT '0',
    `status` enum('a', 'd') NOT NULL,
    `branch_id` int NOT NULL,
    `created_by` int NOT NULL,
    `target_amount` double NOT NULL DEFAULT '0',
    `commission_per` double NOT NULL DEFAULT '0',
    `leave_days` int NOT NULL DEFAULT '0',
    `month` varchar(10) DEFAULT NULL,
    `year` varchar(4) DEFAULT NULL,
    `update_salary` double NOT NULL DEFAULT '0',
    PRIMARY KEY (`employee_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_employees`
--

LOCK TABLES `tbl_employees` WRITE;
/*!40000 ALTER TABLE `tbl_employees` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_employees` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_expense_details`
--

DROP TABLE IF EXISTS `tbl_expense_details`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_expense_details` (
    `exp_d_id` int NOT NULL AUTO_INCREMENT,
    `exp_id` int NOT NULL DEFAULT '0',
    `to_acc_id` int NOT NULL DEFAULT '0',
    `exp_amount` double NOT NULL DEFAULT '0',
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `branch_id` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`exp_d_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_expense_details`
--

LOCK TABLES `tbl_expense_details` WRITE;
/*!40000 ALTER TABLE `tbl_expense_details` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_expense_details` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_expense_recognition`
--

DROP TABLE IF EXISTS `tbl_expense_recognition`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_expense_recognition` (
    `recog_id` int NOT NULL AUTO_INCREMENT,
    `creation_date` varchar(30) NOT NULL,
    `total_amount` double NOT NULL DEFAULT '0',
    `narration` text,
    `creation_by` int NOT NULL,
    `branch_id` int NOT NULL,
    `status` enum('a', 'd', 'p') NOT NULL DEFAULT 'a',
    PRIMARY KEY (`recog_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_expense_recognition`
--

LOCK TABLES `tbl_expense_recognition` WRITE;
/*!40000 ALTER TABLE `tbl_expense_recognition` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_expense_recognition` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_expense_recognition_details`
--

DROP TABLE IF EXISTS `tbl_expense_recognition_details`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_expense_recognition_details` (
    `recog_d_id` int NOT NULL AUTO_INCREMENT,
    `recog_id` int NOT NULL,
    `description` varchar(255) DEFAULT NULL,
    `remark` varchar(255) DEFAULT NULL,
    `amount` double NOT NULL DEFAULT '0',
    `status` enum('a', 'd', 'p') NOT NULL DEFAULT 'a',
    PRIMARY KEY (`recog_d_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_expense_recognition_details`
--

LOCK TABLES `tbl_expense_recognition_details` WRITE;
/*!40000 ALTER TABLE `tbl_expense_recognition_details` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_expense_recognition_details` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_expenses`
--

DROP TABLE IF EXISTS `tbl_expenses`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_expenses` (
    `exp_id` int NOT NULL AUTO_INCREMENT,
    `from_acc_id` int NOT NULL DEFAULT '0',
    `exp_code` varchar(50) DEFAULT NULL,
    `exp_total` double NOT NULL DEFAULT '0',
    `creation_date` varchar(30) DEFAULT NULL,
    `narration` text,
    `branch_id` int NOT NULL DEFAULT '0',
    `creation_by` int NOT NULL DEFAULT '0',
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `employee_id` int NOT NULL DEFAULT '0',
    `pay_to` varchar(255) DEFAULT NULL,
    PRIMARY KEY (`exp_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_expenses`
--

LOCK TABLES `tbl_expenses` WRITE;
/*!40000 ALTER TABLE `tbl_expenses` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_expenses` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_given_items`
--

DROP TABLE IF EXISTS `tbl_given_items`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_given_items` (
    `replace_d_id` int NOT NULL AUTO_INCREMENT,
    `replace_id` int NOT NULL,
    `warehouse_id` int NOT NULL DEFAULT '0',
    `item_id` int NOT NULL DEFAULT '0',
    `item_percentage` double NOT NULL DEFAULT '0',
    `item_qty` double NOT NULL DEFAULT '0',
    `retail_qty` double NOT NULL DEFAULT '0',
    `item_rate` double NOT NULL DEFAULT '0',
    `given_qty` double NOT NULL DEFAULT '0',
    `given_rate` double NOT NULL DEFAULT '0',
    `item_total` double NOT NULL DEFAULT '0',
    `serials` text,
    `created_date` varchar(30) NOT NULL,
    `branch_id` int NOT NULL DEFAULT '0',
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `per_unit_id` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`replace_d_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_given_items`
--

LOCK TABLES `tbl_given_items` WRITE;
/*!40000 ALTER TABLE `tbl_given_items` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_given_items` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_groups`
--

DROP TABLE IF EXISTS `tbl_groups`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_groups` (
    `group_id` int NOT NULL AUTO_INCREMENT,
    `group_name` varchar(25) NOT NULL,
    `create_by` int NOT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `branch_id` int NOT NULL,
    PRIMARY KEY (`group_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_groups`
--

LOCK TABLES `tbl_groups` WRITE;
/*!40000 ALTER TABLE `tbl_groups` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_groups` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_income_details`
--

DROP TABLE IF EXISTS `tbl_income_details`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_income_details` (
    `inc_d_id` int NOT NULL AUTO_INCREMENT,
    `inc_id` int NOT NULL DEFAULT '0',
    `from_acc_id` int NOT NULL DEFAULT '0',
    `inc_amount` double NOT NULL DEFAULT '0',
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `branch_id` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`inc_d_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_income_details`
--

LOCK TABLES `tbl_income_details` WRITE;
/*!40000 ALTER TABLE `tbl_income_details` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_income_details` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_incomes`
--

DROP TABLE IF EXISTS `tbl_incomes`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_incomes` (
    `inc_id` int NOT NULL AUTO_INCREMENT,
    `into_acc_id` int NOT NULL,
    `inc_code` varchar(50) DEFAULT NULL,
    `inc_total` double NOT NULL DEFAULT '0',
    `creation_date` varchar(30) DEFAULT NULL,
    `narration` text,
    `branch_id` int NOT NULL DEFAULT '0',
    `creation_by` int NOT NULL DEFAULT '0',
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    PRIMARY KEY (`inc_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_incomes`
--

LOCK TABLES `tbl_incomes` WRITE;
/*!40000 ALTER TABLE `tbl_incomes` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_incomes` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_institution_profile`
--

DROP TABLE IF EXISTS `tbl_institution_profile`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_institution_profile` (
    `pro_id` int NOT NULL AUTO_INCREMENT,
    `pro_name` text,
    `pro_desc` text,
    `pro_logo` text,
    `pro_print_type` enum('a4', 'pos', '1/2a4') NOT NULL DEFAULT 'a4',
    `pro_updated_by` int NOT NULL,
    `pro_branch_id` int NOT NULL,
    `is_warehouse` enum('yes', 'no') NOT NULL DEFAULT 'no',
    `is_cal_type` enum('on_total', 'individual') NOT NULL DEFAULT 'individual',
    `is_serial` enum('yes', 'no') NOT NULL DEFAULT 'no',
    `currency` varchar(10) NOT NULL DEFAULT 'BDT',
    `is_voucher_receipt` enum('yes', 'no') NOT NULL DEFAULT 'no',
    `pad_status` enum('yes', 'no') NOT NULL DEFAULT 'no',
    `is_auto_challan` enum('yes', 'no') CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci NOT NULL DEFAULT 'yes',
    `is_minus_stock_sale` enum('yes', 'no') CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci NOT NULL DEFAULT 'no',
    PRIMARY KEY (`pro_id`)
) ENGINE = InnoDB AUTO_INCREMENT = 2 DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_institution_profile`
--

LOCK TABLES `tbl_institution_profile` WRITE;
/*!40000 ALTER TABLE `tbl_institution_profile` DISABLE KEYS */
;

INSERT INTO
    `tbl_institution_profile`
VALUES (
        1,
        'RealTrac',
        'Dubai',
        'pro_logo-1707935762510.png',
        'a4',
        1,
        1,
        'no',
        'on_total',
        'no',
        'TK.',
        'no',
        'no',
        'yes',
        'no'
    );
/*!40000 ALTER TABLE `tbl_institution_profile` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_item_average_rate`
--

DROP TABLE IF EXISTS `tbl_item_average_rate`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_item_average_rate` (
    `id` int NOT NULL AUTO_INCREMENT,
    `item_id` int NOT NULL,
    `branch_id` int NOT NULL,
    `warehouse_id` int NOT NULL DEFAULT '0',
    `average_rate` text,
    PRIMARY KEY (`id`),
    KEY `item_average_rate` (
        `item_id`,
        `branch_id`,
        `warehouse_id`
    )
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_item_average_rate`
--

LOCK TABLES `tbl_item_average_rate` WRITE;
/*!40000 ALTER TABLE `tbl_item_average_rate` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_item_average_rate` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_item_current_stock`
--

DROP TABLE IF EXISTS `tbl_item_current_stock`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_item_current_stock` (
    `stock_id` int NOT NULL AUTO_INCREMENT,
    `item_id` int NOT NULL,
    `branch_id` int NOT NULL,
    `warehouse_id` int NOT NULL DEFAULT '0',
    `sale_qty` double NOT NULL DEFAULT '0',
    `sale_return_qty` double NOT NULL DEFAULT '0',
    `purchase_qty` double NOT NULL DEFAULT '0',
    `purchase_return_qty` double NOT NULL DEFAULT '0',
    `production_qty` double NOT NULL DEFAULT '0',
    `damage_qty` double NOT NULL DEFAULT '0',
    `consume_qty` double NOT NULL DEFAULT '0',
    `transfer_in_qty` double NOT NULL DEFAULT '0',
    `transfer_out_qty` double NOT NULL DEFAULT '0',
    `replace_return_qty` double NOT NULL DEFAULT '0',
    `replace_given_qty` double NOT NULL DEFAULT '0',
    `opening_qty` double DEFAULT '0',
    PRIMARY KEY (`stock_id`),
    KEY `current_stock_index` (
        `item_id`,
        `branch_id`,
        `warehouse_id`
    )
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_item_current_stock`
--

LOCK TABLES `tbl_item_current_stock` WRITE;
/*!40000 ALTER TABLE `tbl_item_current_stock` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_item_current_stock` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_item_serials`
--

DROP TABLE IF EXISTS `tbl_item_serials`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_item_serials` (
    `serial_id` int NOT NULL AUTO_INCREMENT,
    `item_id` int NOT NULL,
    `serial_number` varchar(100) DEFAULT NULL,
    `warehouse_id` int NOT NULL DEFAULT '0',
    `branch_id` int NOT NULL,
    `status` enum('in', 'out', 'ordered') NOT NULL,
    PRIMARY KEY (`serial_id`),
    KEY `item_serials` (
        `item_id`,
        `serial_number`,
        `warehouse_id`,
        `branch_id`
    )
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_item_serials`
--

LOCK TABLES `tbl_item_serials` WRITE;
/*!40000 ALTER TABLE `tbl_item_serials` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_item_serials` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_item_units`
--

DROP TABLE IF EXISTS `tbl_item_units`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_item_units` (
    `unit_id` int NOT NULL AUTO_INCREMENT,
    `unit_name` varchar(255) NOT NULL,
    `unit_symbol` varchar(255) DEFAULT NULL,
    `is_multi_unit` enum('yes', 'no') NOT NULL DEFAULT 'no',
    `conversion` double NOT NULL DEFAULT '1',
    `base_unit_id` int NOT NULL DEFAULT '0',
    `create_by` int NOT NULL,
    `branch_id` int NOT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    PRIMARY KEY (`unit_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_item_units`
--

LOCK TABLES `tbl_item_units` WRITE;
/*!40000 ALTER TABLE `tbl_item_units` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_item_units` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_items`
--

DROP TABLE IF EXISTS `tbl_items`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_items` (
    `item_id` int NOT NULL AUTO_INCREMENT,
    `item_code` varchar(100) DEFAULT NULL,
    `item_barcode` varchar(100) DEFAULT NULL,
    `item_name` varchar(255) NOT NULL,
    `group_id` int NOT NULL,
    `category_id` int NOT NULL,
    `unit_id` int NOT NULL,
    `narration` text,
    `min_sale_qty` double NOT NULL DEFAULT '0',
    `min_sale_rate` double NOT NULL DEFAULT '0',
    `purchase_rate` double NOT NULL DEFAULT '0',
    `sale_rate` double NOT NULL DEFAULT '0',
    `wholesaler_rate` double NOT NULL DEFAULT '0',
    `retailer_rate` double NOT NULL DEFAULT '0',
    `distributor_rate` double NOT NULL DEFAULT '0',
    `corporate_rate` double NOT NULL DEFAULT '0',
    `discount_per` double NOT NULL DEFAULT '0',
    `tax_acc_id` int NOT NULL DEFAULT '0',
    `is_serial` enum('yes', 'no') NOT NULL DEFAULT 'no',
    `is_service` enum('yes', 'no') NOT NULL DEFAULT 'no',
    `create_by` int NOT NULL,
    `branch_ids` text NOT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `tax_per` double NOT NULL DEFAULT '0',
    `origin_id` int NOT NULL DEFAULT '0',
    `model_id` int NOT NULL DEFAULT '0',
    `photo` varchar(100) DEFAULT NULL,
    `opening_qty` double DEFAULT '0',
    `opening_rate` double DEFAULT '0',
    PRIMARY KEY (`item_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_items`
--

LOCK TABLES `tbl_items` WRITE;
/*!40000 ALTER TABLE `tbl_items` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_items` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_journal_details`
--

DROP TABLE IF EXISTS `tbl_journal_details`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_journal_details` (
    `jrn_d_id` int NOT NULL AUTO_INCREMENT,
    `jrn_id` int NOT NULL,
    `debit_amount` double NOT NULL DEFAULT '0',
    `credit_amount` double NOT NULL DEFAULT '0',
    `acc_id` int NOT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    PRIMARY KEY (`jrn_d_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_journal_details`
--

LOCK TABLES `tbl_journal_details` WRITE;
/*!40000 ALTER TABLE `tbl_journal_details` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_journal_details` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_journals`
--

DROP TABLE IF EXISTS `tbl_journals`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_journals` (
    `jrn_id` int NOT NULL AUTO_INCREMENT,
    `jrn_code` varchar(255) DEFAULT NULL,
    `creation_date` varchar(30) NOT NULL,
    `debit_total` double NOT NULL DEFAULT '0',
    `credit_total` double NOT NULL DEFAULT '0',
    `narration` text,
    `branch_id` int NOT NULL,
    `create_by` int NOT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    PRIMARY KEY (`jrn_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_journals`
--

LOCK TABLES `tbl_journals` WRITE;
/*!40000 ALTER TABLE `tbl_journals` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_journals` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_locations`
--

DROP TABLE IF EXISTS `tbl_locations`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_locations` (
    `location_id` int NOT NULL AUTO_INCREMENT,
    `location_name` varchar(255) NOT NULL,
    `create_by` int NOT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `branch_id` int NOT NULL,
    PRIMARY KEY (`location_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_locations`
--

LOCK TABLES `tbl_locations` WRITE;
/*!40000 ALTER TABLE `tbl_locations` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_locations` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_manufactured_items`
--

DROP TABLE IF EXISTS `tbl_manufactured_items`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_manufactured_items` (
    `mf_d_id` int NOT NULL AUTO_INCREMENT,
    `mf_id` int NOT NULL,
    `warehouse_id` int NOT NULL DEFAULT '0',
    `item_id` int NOT NULL DEFAULT '0',
    `item_percentage` double NOT NULL DEFAULT '0',
    `item_qty` double NOT NULL DEFAULT '0',
    `retail_qty` double NOT NULL DEFAULT '0',
    `item_rate` double NOT NULL DEFAULT '0',
    `pd_qty` double NOT NULL DEFAULT '0',
    `pd_rate` double NOT NULL DEFAULT '0',
    `item_total` double NOT NULL DEFAULT '0',
    `serials` text,
    `created_date` varchar(30) NOT NULL,
    `branch_id` int NOT NULL DEFAULT '0',
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `per_unit_id` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`mf_d_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_manufactured_items`
--

LOCK TABLES `tbl_manufactured_items` WRITE;
/*!40000 ALTER TABLE `tbl_manufactured_items` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_manufactured_items` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_manufacturing_consume_items`
--

DROP TABLE IF EXISTS `tbl_manufacturing_consume_items`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_manufacturing_consume_items` (
    `mf_c_id` int NOT NULL AUTO_INCREMENT,
    `mf_id` int NOT NULL DEFAULT '0',
    `warehouse_id` int NOT NULL DEFAULT '0',
    `item_id` int NOT NULL DEFAULT '0',
    `raw_item_qty` double NOT NULL DEFAULT '0',
    `raw_retail_qty` double NOT NULL DEFAULT '0',
    `raw_item_rate` int NOT NULL,
    `raw_qty` double NOT NULL DEFAULT '0',
    `raw_rate` double NOT NULL DEFAULT '0',
    `serials` text,
    `created_date` varchar(30) NOT NULL,
    `branch_id` int NOT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `raw_item_total` double NOT NULL DEFAULT '0',
    `per_unit_id` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`mf_c_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_manufacturing_consume_items`
--

LOCK TABLES `tbl_manufacturing_consume_items` WRITE;
/*!40000 ALTER TABLE `tbl_manufacturing_consume_items` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_manufacturing_consume_items` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_manufacturing_master`
--

DROP TABLE IF EXISTS `tbl_manufacturing_master`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_manufacturing_master` (
    `mf_id` int NOT NULL AUTO_INCREMENT,
    `mf_voucher_no` varchar(255) DEFAULT NULL,
    `is_serial` enum('yes', 'no') NOT NULL,
    `narration` text,
    `labour_cost` double NOT NULL DEFAULT '0',
    `others_cost` double NOT NULL DEFAULT '0',
    `total_cost` double NOT NULL DEFAULT '0',
    `created_date` varchar(30) NOT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `created_by` int NOT NULL DEFAULT '0',
    `branch_id` int NOT NULL DEFAULT '0',
    `orderId` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`mf_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_manufacturing_master`
--

LOCK TABLES `tbl_manufacturing_master` WRITE;
/*!40000 ALTER TABLE `tbl_manufacturing_master` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_manufacturing_master` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_models`
--

DROP TABLE IF EXISTS `tbl_models`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_models` (
    `model_id` int NOT NULL AUTO_INCREMENT,
    `model_name` varchar(255) DEFAULT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `create_by` int NOT NULL DEFAULT '0',
    `branch_id` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`model_id`)
) ENGINE = MyISAM DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_models`
--

LOCK TABLES `tbl_models` WRITE;
/*!40000 ALTER TABLE `tbl_models` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_models` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_origins`
--

DROP TABLE IF EXISTS `tbl_origins`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_origins` (
    `origin_id` int NOT NULL AUTO_INCREMENT,
    `origin_name` varchar(255) DEFAULT NULL,
    `create_by` int NOT NULL DEFAULT '0',
    `branch_id` int NOT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    PRIMARY KEY (`origin_id`)
) ENGINE = MyISAM DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_origins`
--

LOCK TABLES `tbl_origins` WRITE;
/*!40000 ALTER TABLE `tbl_origins` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_origins` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_payment_details`
--

DROP TABLE IF EXISTS `tbl_payment_details`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_payment_details` (
    `pay_d_id` int NOT NULL AUTO_INCREMENT,
    `pay_id` int NOT NULL,
    `pur_vch_no` varchar(30) DEFAULT NULL,
    `pay_from` int NOT NULL,
    `pay_to` int NOT NULL,
    `pay_amount` double NOT NULL DEFAULT '0',
    PRIMARY KEY (`pay_d_id`)
) ENGINE = InnoDB DEFAULT CHARSET = ucs2;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_payment_details`
--

LOCK TABLES `tbl_payment_details` WRITE;
/*!40000 ALTER TABLE `tbl_payment_details` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_payment_details` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_payments`
--

DROP TABLE IF EXISTS `tbl_payments`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_payments` (
    `pay_id` int NOT NULL AUTO_INCREMENT,
    `pay_vch_no` varchar(30) NOT NULL,
    `creation_date` varchar(10) NOT NULL,
    `pay_total` double NOT NULL,
    `narration` text,
    `create_by` int NOT NULL,
    `branch_id` int NOT NULL,
    PRIMARY KEY (`pay_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_payments`
--

LOCK TABLES `tbl_payments` WRITE;
/*!40000 ALTER TABLE `tbl_payments` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_payments` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_purchase_details`
--

DROP TABLE IF EXISTS `tbl_purchase_details`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_purchase_details` (
    `pur_d_id` int NOT NULL AUTO_INCREMENT,
    `pur_id` int NOT NULL,
    `warehouse_id` int NOT NULL DEFAULT '0',
    `item_id` int NOT NULL DEFAULT '0',
    `item_qty` double NOT NULL DEFAULT '0',
    `retail_qty` double NOT NULL DEFAULT '0',
    `item_rate` text NOT NULL,
    `pur_qty` double NOT NULL DEFAULT '0',
    `pur_rate` text NOT NULL,
    `item_discount` double NOT NULL DEFAULT '0',
    `item_discount_per` double NOT NULL DEFAULT '0',
    `item_tax` double NOT NULL DEFAULT '0',
    `item_tax_per` double NOT NULL DEFAULT '0',
    `item_total` double NOT NULL DEFAULT '0',
    `discount_acc_id` int NOT NULL DEFAULT '0',
    `tax_acc_id` int NOT NULL DEFAULT '0',
    `serials` text,
    `created_date` varchar(30) DEFAULT NULL,
    `branch_id` int NOT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `order_id` int NOT NULL DEFAULT '0',
    `per_unit_id` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`pur_d_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_purchase_details`
--

LOCK TABLES `tbl_purchase_details` WRITE;
/*!40000 ALTER TABLE `tbl_purchase_details` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_purchase_details` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_purchase_master`
--

DROP TABLE IF EXISTS `tbl_purchase_master`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_purchase_master` (
    `pur_id` int NOT NULL AUTO_INCREMENT,
    `purchase_acc_id` int NOT NULL,
    `is_serial` enum('yes', 'no') NOT NULL,
    `is_cal_type` enum('on_total', 'individual') NOT NULL,
    `acc_id` int NOT NULL DEFAULT '0',
    `tax_acc_id` int NOT NULL DEFAULT '0',
    `discount_acc_id` int NOT NULL DEFAULT '0',
    `transport_acc_id` int NOT NULL DEFAULT '0',
    `pur_voucher_no` varchar(100) DEFAULT NULL,
    `total_tax` double NOT NULL DEFAULT '0',
    `total_discount` double NOT NULL DEFAULT '0',
    `total_transport_cost` double NOT NULL DEFAULT '0',
    `total_tax_per` double NOT NULL DEFAULT '0',
    `total_discount_per` double NOT NULL DEFAULT '0',
    `sub_total` double NOT NULL DEFAULT '0',
    `total_amount` double NOT NULL DEFAULT '0',
    `paid_amount` double NOT NULL DEFAULT '0',
    `due_amount` double NOT NULL DEFAULT '0',
    `created_date` varchar(30) DEFAULT NULL,
    `narration` text,
    `created_by` int NOT NULL DEFAULT '0',
    `branch_id` int NOT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `order_id` double NOT NULL DEFAULT '0',
    PRIMARY KEY (`pur_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_purchase_master`
--

LOCK TABLES `tbl_purchase_master` WRITE;
/*!40000 ALTER TABLE `tbl_purchase_master` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_purchase_master` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_purchase_order_details`
--

DROP TABLE IF EXISTS `tbl_purchase_order_details`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_purchase_order_details` (
    `pur_d_id` int NOT NULL AUTO_INCREMENT,
    `pur_o_id` int NOT NULL,
    `warehouse_id` int NOT NULL DEFAULT '0',
    `item_id` int NOT NULL DEFAULT '0',
    `item_qty` double NOT NULL DEFAULT '0',
    `retail_qty` double NOT NULL DEFAULT '0',
    `item_rate` text NOT NULL,
    `pur_qty` double NOT NULL DEFAULT '0',
    `pur_rate` text NOT NULL,
    `item_discount` double NOT NULL DEFAULT '0',
    `item_discount_per` double NOT NULL DEFAULT '0',
    `item_tax` double NOT NULL DEFAULT '0',
    `item_tax_per` double NOT NULL DEFAULT '0',
    `item_total` double NOT NULL DEFAULT '0',
    `discount_acc_id` int NOT NULL DEFAULT '0',
    `tax_acc_id` int NOT NULL DEFAULT '0',
    `serials` text,
    `created_date` varchar(30) DEFAULT NULL,
    `branch_id` int NOT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `per_unit_id` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`pur_d_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_purchase_order_details`
--

LOCK TABLES `tbl_purchase_order_details` WRITE;
/*!40000 ALTER TABLE `tbl_purchase_order_details` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_purchase_order_details` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_purchase_order_master`
--

DROP TABLE IF EXISTS `tbl_purchase_order_master`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_purchase_order_master` (
    `pur_o_id` int NOT NULL AUTO_INCREMENT,
    `is_serial` enum('yes', 'no') NOT NULL,
    `is_cal_type` enum('on_total', 'individual') NOT NULL,
    `acc_id` int NOT NULL DEFAULT '0',
    `tax_acc_id` int NOT NULL DEFAULT '0',
    `discount_acc_id` int NOT NULL DEFAULT '0',
    `transport_acc_id` int NOT NULL DEFAULT '0',
    `pur_order_no` varchar(100) DEFAULT NULL,
    `total_tax` double NOT NULL DEFAULT '0',
    `total_discount` double NOT NULL DEFAULT '0',
    `total_transport_cost` double NOT NULL DEFAULT '0',
    `total_tax_per` double NOT NULL DEFAULT '0',
    `total_discount_per` double NOT NULL DEFAULT '0',
    `sub_total` double NOT NULL DEFAULT '0',
    `total_amount` double NOT NULL DEFAULT '0',
    `created_date` varchar(30) DEFAULT NULL,
    `narration` text,
    `created_by` int NOT NULL DEFAULT '0',
    `branch_id` int NOT NULL,
    `status` enum('a', 'd', 'c') NOT NULL DEFAULT 'a',
    PRIMARY KEY (`pur_o_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_purchase_order_master`
--

LOCK TABLES `tbl_purchase_order_master` WRITE;
/*!40000 ALTER TABLE `tbl_purchase_order_master` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_purchase_order_master` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_purchase_return_details`
--

DROP TABLE IF EXISTS `tbl_purchase_return_details`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_purchase_return_details` (
    `pur_r_d_id` int NOT NULL AUTO_INCREMENT,
    `pur_r_id` int NOT NULL,
    `warehouse_id` int NOT NULL DEFAULT '0',
    `item_id` int NOT NULL DEFAULT '0',
    `item_qty` double NOT NULL DEFAULT '0',
    `retail_qty` double NOT NULL DEFAULT '0',
    `item_rate` text NOT NULL,
    `pur_r_qty` double NOT NULL DEFAULT '0',
    `pur_r_rate` text NOT NULL,
    `item_discount` double NOT NULL DEFAULT '0',
    `item_discount_per` double NOT NULL DEFAULT '0',
    `item_tax` double NOT NULL DEFAULT '0',
    `item_tax_per` double NOT NULL DEFAULT '0',
    `item_total` double NOT NULL DEFAULT '0',
    `discount_acc_id` int NOT NULL DEFAULT '0',
    `tax_acc_id` int NOT NULL DEFAULT '0',
    `serials` text,
    `created_date` varchar(30) DEFAULT NULL,
    `branch_id` int NOT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `order_id` int NOT NULL DEFAULT '0',
    `per_unit_id` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`pur_r_d_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_purchase_return_details`
--

LOCK TABLES `tbl_purchase_return_details` WRITE;
/*!40000 ALTER TABLE `tbl_purchase_return_details` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_purchase_return_details` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_purchase_return_master`
--

DROP TABLE IF EXISTS `tbl_purchase_return_master`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_purchase_return_master` (
    `pur_r_id` int NOT NULL AUTO_INCREMENT,
    `purchase_return_acc_id` int NOT NULL,
    `is_serial` enum('yes', 'no') NOT NULL,
    `is_cal_type` enum('on_total', 'individual') NOT NULL,
    `acc_id` int NOT NULL DEFAULT '0',
    `tax_acc_id` int NOT NULL DEFAULT '0',
    `discount_acc_id` int NOT NULL DEFAULT '0',
    `transport_acc_id` int NOT NULL DEFAULT '0',
    `pur_r_voucher_no` varchar(100) DEFAULT NULL,
    `total_tax` double NOT NULL DEFAULT '0',
    `total_discount` double NOT NULL DEFAULT '0',
    `total_transport_cost` double NOT NULL DEFAULT '0',
    `total_tax_per` double NOT NULL DEFAULT '0',
    `total_discount_per` double NOT NULL DEFAULT '0',
    `sub_total` double NOT NULL DEFAULT '0',
    `total_amount` double NOT NULL DEFAULT '0',
    `created_date` varchar(30) DEFAULT NULL,
    `narration` text,
    `created_by` int NOT NULL DEFAULT '0',
    `branch_id` int NOT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `order_id` double NOT NULL DEFAULT '0',
    PRIMARY KEY (`pur_r_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_purchase_return_master`
--

LOCK TABLES `tbl_purchase_return_master` WRITE;
/*!40000 ALTER TABLE `tbl_purchase_return_master` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_purchase_return_master` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_receipt_details`
--

DROP TABLE IF EXISTS `tbl_receipt_details`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_receipt_details` (
    `rcv_d_id` int NOT NULL AUTO_INCREMENT,
    `rcv_id` int NOT NULL,
    `sale_vch_no` varchar(100) DEFAULT NULL,
    `rcv_amount` double NOT NULL,
    `rcv_from` int NOT NULL,
    `rcv_into` int NOT NULL,
    PRIMARY KEY (`rcv_d_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_receipt_details`
--

LOCK TABLES `tbl_receipt_details` WRITE;
/*!40000 ALTER TABLE `tbl_receipt_details` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_receipt_details` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_receipts`
--

DROP TABLE IF EXISTS `tbl_receipts`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_receipts` (
    `rcv_id` int NOT NULL AUTO_INCREMENT,
    `rcv_vch_no` varchar(30) NOT NULL,
    `creation_date` varchar(10) NOT NULL,
    `rcv_total` double NOT NULL,
    `narration` text,
    `create_by` int NOT NULL,
    `branch_id` int NOT NULL,
    PRIMARY KEY (`rcv_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_receipts`
--

LOCK TABLES `tbl_receipts` WRITE;
/*!40000 ALTER TABLE `tbl_receipts` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_receipts` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_replace_master`
--

DROP TABLE IF EXISTS `tbl_replace_master`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_replace_master` (
    `replace_id` int NOT NULL AUTO_INCREMENT,
    `customer_id` int NOT NULL DEFAULT '0',
    `voucher_no` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
    `is_serial` enum('yes', 'no') NOT NULL,
    `narration` text,
    `labour_cost` double NOT NULL DEFAULT '0',
    `others_cost` double NOT NULL DEFAULT '0',
    `total_cost` double NOT NULL DEFAULT '0',
    `created_date` varchar(30) NOT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `created_by` int NOT NULL DEFAULT '0',
    `branch_id` int NOT NULL DEFAULT '0',
    `orderId` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`replace_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_replace_master`
--

LOCK TABLES `tbl_replace_master` WRITE;
/*!40000 ALTER TABLE `tbl_replace_master` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_replace_master` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_replace_return_items`
--

DROP TABLE IF EXISTS `tbl_replace_return_items`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_replace_return_items` (
    `replace_r_id` int NOT NULL AUTO_INCREMENT,
    `replace_id` int NOT NULL DEFAULT '0',
    `warehouse_id` int NOT NULL DEFAULT '0',
    `item_id` int NOT NULL DEFAULT '0',
    `return_item_qty` double NOT NULL DEFAULT '0',
    `return_retail_qty` double NOT NULL DEFAULT '0',
    `return_item_rate` int NOT NULL,
    `return_qty` double NOT NULL DEFAULT '0',
    `return_rate` double NOT NULL DEFAULT '0',
    `serials` text,
    `created_date` varchar(30) NOT NULL,
    `branch_id` int NOT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `return_item_total` double NOT NULL DEFAULT '0',
    `per_unit_id` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`replace_r_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_replace_return_items`
--

LOCK TABLES `tbl_replace_return_items` WRITE;
/*!40000 ALTER TABLE `tbl_replace_return_items` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_replace_return_items` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_sales_details`
--

DROP TABLE IF EXISTS `tbl_sales_details`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_sales_details` (
    `sale_d_id` int NOT NULL AUTO_INCREMENT,
    `sale_id` int NOT NULL,
    `warehouse_id` int NOT NULL DEFAULT '0',
    `item_id` int NOT NULL DEFAULT '0',
    `item_qty` double NOT NULL DEFAULT '0',
    `retail_qty` double NOT NULL DEFAULT '0',
    `item_rate` text NOT NULL,
    `sale_qty` double NOT NULL DEFAULT '0',
    `sale_rate` text NOT NULL,
    `item_discount` double NOT NULL DEFAULT '0',
    `item_discount_per` double NOT NULL DEFAULT '0',
    `item_tax` double NOT NULL DEFAULT '0',
    `item_tax_per` double NOT NULL DEFAULT '0',
    `item_total` double NOT NULL DEFAULT '0',
    `discount_acc_id` int NOT NULL DEFAULT '0',
    `tax_acc_id` int NOT NULL DEFAULT '0',
    `serials` text,
    `created_date` varchar(30) DEFAULT NULL,
    `branch_id` int NOT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `order_id` int NOT NULL DEFAULT '0',
    `purchase_average_rate` text NOT NULL,
    `serial_note` text,
    `per_unit_id` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`sale_d_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_sales_details`
--

LOCK TABLES `tbl_sales_details` WRITE;
/*!40000 ALTER TABLE `tbl_sales_details` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_sales_details` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_sales_master`
--

DROP TABLE IF EXISTS `tbl_sales_master`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_sales_master` (
    `sale_id` int NOT NULL AUTO_INCREMENT,
    `sales_acc_id` int NOT NULL,
    `is_serial` enum('yes', 'no') NOT NULL,
    `is_cal_type` enum('on_total', 'individual') NOT NULL,
    `acc_id` int NOT NULL DEFAULT '0',
    `tax_acc_id` int NOT NULL DEFAULT '0',
    `discount_acc_id` int NOT NULL DEFAULT '0',
    `transport_acc_id` int NOT NULL DEFAULT '0',
    `sale_voucher_no` varchar(100) DEFAULT NULL,
    `total_tax` double NOT NULL DEFAULT '0',
    `total_discount` double NOT NULL DEFAULT '0',
    `total_transport_cost` double NOT NULL DEFAULT '0',
    `total_tax_per` double NOT NULL DEFAULT '0',
    `total_discount_per` double NOT NULL DEFAULT '0',
    `sub_total` double NOT NULL DEFAULT '0',
    `total_amount` double NOT NULL DEFAULT '0',
    `paid_amount` double NOT NULL DEFAULT '0',
    `due_amount` double NOT NULL DEFAULT '0',
    `created_date` varchar(30) DEFAULT NULL,
    `narration` text,
    `created_by` int NOT NULL DEFAULT '0',
    `branch_id` int NOT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `order_id` double NOT NULL DEFAULT '0',
    `employee_id` int NOT NULL DEFAULT '0',
    `emi_month` int NOT NULL DEFAULT '0',
    `is_emi` enum('yes', 'no') NOT NULL DEFAULT 'no',
    `day_week` varchar(255) DEFAULT NULL,
    `emi_amount` double NOT NULL DEFAULT '0',
    `challan_text` text CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci,
    `is_condition_sale` enum('yes', 'no') DEFAULT 'no',
    PRIMARY KEY (`sale_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_sales_master`
--

LOCK TABLES `tbl_sales_master` WRITE;
/*!40000 ALTER TABLE `tbl_sales_master` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_sales_master` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_sales_order_details`
--

DROP TABLE IF EXISTS `tbl_sales_order_details`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_sales_order_details` (
    `sale_d_id` int NOT NULL AUTO_INCREMENT,
    `sale_o_id` int NOT NULL,
    `warehouse_id` int NOT NULL DEFAULT '0',
    `item_id` int NOT NULL DEFAULT '0',
    `item_qty` double NOT NULL DEFAULT '0',
    `retail_qty` double NOT NULL DEFAULT '0',
    `item_rate` text NOT NULL,
    `sale_qty` double NOT NULL DEFAULT '0',
    `sale_rate` text NOT NULL,
    `item_discount` double NOT NULL DEFAULT '0',
    `item_discount_per` double NOT NULL DEFAULT '0',
    `item_tax` double NOT NULL DEFAULT '0',
    `item_tax_per` double NOT NULL DEFAULT '0',
    `item_total` double NOT NULL DEFAULT '0',
    `discount_acc_id` int NOT NULL DEFAULT '0',
    `tax_acc_id` int NOT NULL DEFAULT '0',
    `serials` text,
    `created_date` varchar(30) DEFAULT NULL,
    `branch_id` int NOT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `per_unit_id` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`sale_d_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_sales_order_details`
--

LOCK TABLES `tbl_sales_order_details` WRITE;
/*!40000 ALTER TABLE `tbl_sales_order_details` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_sales_order_details` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_sales_order_master`
--

DROP TABLE IF EXISTS `tbl_sales_order_master`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_sales_order_master` (
    `sale_o_id` int NOT NULL AUTO_INCREMENT,
    `is_serial` enum('yes', 'no') NOT NULL,
    `is_cal_type` enum('on_total', 'individual') NOT NULL,
    `acc_id` int NOT NULL DEFAULT '0',
    `tax_acc_id` int NOT NULL DEFAULT '0',
    `discount_acc_id` int NOT NULL DEFAULT '0',
    `transport_acc_id` int NOT NULL DEFAULT '0',
    `sale_order_no` varchar(100) DEFAULT NULL,
    `total_tax` double NOT NULL DEFAULT '0',
    `total_discount` double NOT NULL DEFAULT '0',
    `total_transport_cost` double NOT NULL DEFAULT '0',
    `total_tax_per` double NOT NULL DEFAULT '0',
    `total_discount_per` double NOT NULL DEFAULT '0',
    `sub_total` double NOT NULL DEFAULT '0',
    `total_amount` double NOT NULL DEFAULT '0',
    `created_date` varchar(30) DEFAULT NULL,
    `narration` text,
    `created_by` int NOT NULL DEFAULT '0',
    `branch_id` int NOT NULL,
    `status` enum('a', 'd', 'c') NOT NULL DEFAULT 'a',
    PRIMARY KEY (`sale_o_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_sales_order_master`
--

LOCK TABLES `tbl_sales_order_master` WRITE;
/*!40000 ALTER TABLE `tbl_sales_order_master` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_sales_order_master` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_sales_quotation_details`
--

DROP TABLE IF EXISTS `tbl_sales_quotation_details`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_sales_quotation_details` (
    `sale_d_id` int NOT NULL AUTO_INCREMENT,
    `sale_o_id` int NOT NULL,
    `warehouse_id` int NOT NULL DEFAULT '0',
    `item_id` int NOT NULL DEFAULT '0',
    `item_qty` double NOT NULL DEFAULT '0',
    `retail_qty` double NOT NULL DEFAULT '0',
    `item_rate` text NOT NULL,
    `sale_qty` double NOT NULL DEFAULT '0',
    `sale_rate` text NOT NULL,
    `item_discount` double NOT NULL DEFAULT '0',
    `item_discount_per` double NOT NULL DEFAULT '0',
    `item_tax` double NOT NULL DEFAULT '0',
    `item_tax_per` double NOT NULL DEFAULT '0',
    `item_total` double NOT NULL DEFAULT '0',
    `discount_acc_id` int NOT NULL DEFAULT '0',
    `tax_acc_id` int NOT NULL DEFAULT '0',
    `serials` text,
    `created_date` varchar(30) DEFAULT NULL,
    `branch_id` int NOT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `per_unit_id` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`sale_d_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_sales_quotation_details`
--

LOCK TABLES `tbl_sales_quotation_details` WRITE;
/*!40000 ALTER TABLE `tbl_sales_quotation_details` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_sales_quotation_details` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_sales_quotation_master`
--

DROP TABLE IF EXISTS `tbl_sales_quotation_master`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_sales_quotation_master` (
    `sale_o_id` int NOT NULL AUTO_INCREMENT,
    `is_serial` enum('yes', 'no') NOT NULL,
    `is_cal_type` enum('on_total', 'individual') NOT NULL,
    `acc_id` int NOT NULL DEFAULT '0',
    `tax_acc_id` int NOT NULL DEFAULT '0',
    `discount_acc_id` int NOT NULL DEFAULT '0',
    `transport_acc_id` int NOT NULL DEFAULT '0',
    `sale_order_no` varchar(100) DEFAULT NULL,
    `total_tax` double NOT NULL DEFAULT '0',
    `total_discount` double NOT NULL DEFAULT '0',
    `total_transport_cost` double NOT NULL DEFAULT '0',
    `total_tax_per` double NOT NULL DEFAULT '0',
    `total_discount_per` double NOT NULL DEFAULT '0',
    `sub_total` double NOT NULL DEFAULT '0',
    `total_amount` double NOT NULL DEFAULT '0',
    `created_date` varchar(30) DEFAULT NULL,
    `narration` text,
    `created_by` int NOT NULL DEFAULT '0',
    `branch_id` int NOT NULL,
    `status` enum('a', 'd', 'c') NOT NULL DEFAULT 'a',
    PRIMARY KEY (`sale_o_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_sales_quotation_master`
--

LOCK TABLES `tbl_sales_quotation_master` WRITE;
/*!40000 ALTER TABLE `tbl_sales_quotation_master` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_sales_quotation_master` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_sales_return_details`
--

DROP TABLE IF EXISTS `tbl_sales_return_details`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_sales_return_details` (
    `sale_r_d_id` int NOT NULL AUTO_INCREMENT,
    `sale_r_id` int NOT NULL,
    `warehouse_id` int NOT NULL DEFAULT '0',
    `item_id` int NOT NULL DEFAULT '0',
    `item_qty` double NOT NULL DEFAULT '0',
    `retail_qty` double NOT NULL DEFAULT '0',
    `item_rate` text NOT NULL,
    `sale_r_qty` double NOT NULL DEFAULT '0',
    `sale_r_rate` text NOT NULL,
    `item_discount` double NOT NULL DEFAULT '0',
    `item_discount_per` double NOT NULL DEFAULT '0',
    `item_tax` double NOT NULL DEFAULT '0',
    `item_tax_per` double NOT NULL DEFAULT '0',
    `item_total` double NOT NULL DEFAULT '0',
    `discount_acc_id` int NOT NULL DEFAULT '0',
    `tax_acc_id` int NOT NULL DEFAULT '0',
    `serials` text,
    `created_date` varchar(30) DEFAULT NULL,
    `branch_id` int NOT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `order_id` int NOT NULL DEFAULT '0',
    `per_unit_id` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`sale_r_d_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_sales_return_details`
--

LOCK TABLES `tbl_sales_return_details` WRITE;
/*!40000 ALTER TABLE `tbl_sales_return_details` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_sales_return_details` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_sales_return_master`
--

DROP TABLE IF EXISTS `tbl_sales_return_master`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_sales_return_master` (
    `sale_r_id` int NOT NULL AUTO_INCREMENT,
    `sales_return_acc_id` int NOT NULL,
    `is_serial` enum('yes', 'no') NOT NULL,
    `is_cal_type` enum('on_total', 'individual') NOT NULL,
    `acc_id` int NOT NULL DEFAULT '0',
    `tax_acc_id` int NOT NULL DEFAULT '0',
    `discount_acc_id` int NOT NULL DEFAULT '0',
    `transport_acc_id` int NOT NULL DEFAULT '0',
    `sale_r_voucher_no` varchar(100) DEFAULT NULL,
    `total_tax` double NOT NULL DEFAULT '0',
    `total_discount` double NOT NULL DEFAULT '0',
    `total_transport_cost` double NOT NULL DEFAULT '0',
    `total_tax_per` double NOT NULL DEFAULT '0',
    `total_discount_per` double NOT NULL DEFAULT '0',
    `sub_total` double NOT NULL DEFAULT '0',
    `total_amount` double NOT NULL DEFAULT '0',
    `created_date` varchar(30) DEFAULT NULL,
    `narration` text,
    `created_by` int NOT NULL DEFAULT '0',
    `branch_id` int NOT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `order_id` double NOT NULL DEFAULT '0',
    PRIMARY KEY (`sale_r_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_sales_return_master`
--

LOCK TABLES `tbl_sales_return_master` WRITE;
/*!40000 ALTER TABLE `tbl_sales_return_master` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_sales_return_master` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_service_details`
--

DROP TABLE IF EXISTS `tbl_service_details`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_service_details` (
    `service_d_id` int NOT NULL AUTO_INCREMENT,
    `service_id` int NOT NULL,
    `warehouse_id` int NOT NULL DEFAULT '0',
    `item_id` int NOT NULL DEFAULT '0',
    `item_qty` double NOT NULL DEFAULT '0',
    `retail_qty` double NOT NULL DEFAULT '0',
    `item_rate` text NOT NULL,
    `service_qty` double NOT NULL DEFAULT '0',
    `service_rate` text NOT NULL,
    `item_discount` double NOT NULL DEFAULT '0',
    `item_discount_per` double NOT NULL DEFAULT '0',
    `item_tax` double NOT NULL DEFAULT '0',
    `item_tax_per` double NOT NULL DEFAULT '0',
    `item_total` double NOT NULL DEFAULT '0',
    `discount_acc_id` int NOT NULL DEFAULT '0',
    `tax_acc_id` int NOT NULL DEFAULT '0',
    `serials` text,
    `created_date` varchar(30) DEFAULT NULL,
    `branch_id` int NOT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `order_id` int NOT NULL DEFAULT '0',
    `per_unit_id` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`service_d_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_service_details`
--

LOCK TABLES `tbl_service_details` WRITE;
/*!40000 ALTER TABLE `tbl_service_details` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_service_details` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_service_expense_details`
--

DROP TABLE IF EXISTS `tbl_service_expense_details`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_service_expense_details` (
    `service_ex_d_id` int NOT NULL AUTO_INCREMENT,
    `service_ex_id` int NOT NULL,
    `warehouse_id` int NOT NULL DEFAULT '0',
    `item_id` int NOT NULL DEFAULT '0',
    `item_qty` double NOT NULL DEFAULT '0',
    `retail_qty` double NOT NULL DEFAULT '0',
    `item_rate` text NOT NULL,
    `service_ex_qty` double NOT NULL DEFAULT '0',
    `service_ex_rate` text NOT NULL,
    `item_discount` double NOT NULL DEFAULT '0',
    `item_discount_per` double NOT NULL DEFAULT '0',
    `item_tax` double NOT NULL DEFAULT '0',
    `item_tax_per` double NOT NULL DEFAULT '0',
    `item_total` double NOT NULL DEFAULT '0',
    `discount_acc_id` int NOT NULL DEFAULT '0',
    `tax_acc_id` int NOT NULL DEFAULT '0',
    `serials` text,
    `created_date` varchar(30) DEFAULT NULL,
    `branch_id` int NOT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `order_id` int NOT NULL DEFAULT '0',
    `per_unit_id` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`service_ex_d_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_service_expense_details`
--

LOCK TABLES `tbl_service_expense_details` WRITE;
/*!40000 ALTER TABLE `tbl_service_expense_details` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_service_expense_details` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_service_expense_master`
--

DROP TABLE IF EXISTS `tbl_service_expense_master`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_service_expense_master` (
    `service_ex_id` int NOT NULL AUTO_INCREMENT,
    `service_ex_acc_id` int NOT NULL,
    `is_serial` enum('yes', 'no') NOT NULL,
    `is_cal_type` enum('on_total', 'individual') NOT NULL,
    `acc_id` int NOT NULL DEFAULT '0',
    `tax_acc_id` int NOT NULL DEFAULT '0',
    `discount_acc_id` int NOT NULL DEFAULT '0',
    `transport_acc_id` int NOT NULL DEFAULT '0',
    `service_ex_voucher_no` varchar(100) DEFAULT NULL,
    `total_tax` double NOT NULL DEFAULT '0',
    `total_discount` double NOT NULL DEFAULT '0',
    `total_transport_cost` double NOT NULL DEFAULT '0',
    `total_tax_per` double NOT NULL DEFAULT '0',
    `total_discount_per` double NOT NULL DEFAULT '0',
    `sub_total` double NOT NULL DEFAULT '0',
    `total_amount` double NOT NULL DEFAULT '0',
    `paid_amount` double NOT NULL DEFAULT '0',
    `due_amount` double NOT NULL DEFAULT '0',
    `created_date` varchar(30) DEFAULT NULL,
    `narration` text,
    `created_by` int NOT NULL DEFAULT '0',
    `branch_id` int NOT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `order_id` double NOT NULL DEFAULT '0',
    PRIMARY KEY (`service_ex_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_service_expense_master`
--

LOCK TABLES `tbl_service_expense_master` WRITE;
/*!40000 ALTER TABLE `tbl_service_expense_master` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_service_expense_master` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_service_master`
--

DROP TABLE IF EXISTS `tbl_service_master`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_service_master` (
    `service_id` int NOT NULL AUTO_INCREMENT,
    `services_acc_id` int NOT NULL,
    `is_serial` enum('yes', 'no') NOT NULL,
    `is_cal_type` enum('on_total', 'individual') NOT NULL,
    `acc_id` int NOT NULL DEFAULT '0',
    `tax_acc_id` int NOT NULL DEFAULT '0',
    `discount_acc_id` int NOT NULL DEFAULT '0',
    `transport_acc_id` int NOT NULL DEFAULT '0',
    `service_voucher_no` varchar(100) DEFAULT NULL,
    `total_tax` double NOT NULL DEFAULT '0',
    `total_discount` double NOT NULL DEFAULT '0',
    `total_transport_cost` double NOT NULL DEFAULT '0',
    `total_tax_per` double NOT NULL DEFAULT '0',
    `total_discount_per` double NOT NULL DEFAULT '0',
    `sub_total` double NOT NULL DEFAULT '0',
    `total_amount` double NOT NULL DEFAULT '0',
    `paid_amount` double NOT NULL DEFAULT '0',
    `due_amount` double NOT NULL DEFAULT '0',
    `created_date` varchar(30) DEFAULT NULL,
    `narration` text,
    `created_by` int NOT NULL DEFAULT '0',
    `branch_id` int NOT NULL,
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    `order_id` double NOT NULL DEFAULT '0',
    PRIMARY KEY (`service_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_service_master`
--

LOCK TABLES `tbl_service_master` WRITE;
/*!40000 ALTER TABLE `tbl_service_master` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_service_master` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_transfer_details`
--

DROP TABLE IF EXISTS `tbl_transfer_details`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_transfer_details` (
    `t_d_id` int NOT NULL AUTO_INCREMENT,
    `t_id` int NOT NULL,
    `to_branch_id` int NOT NULL DEFAULT '0',
    `from_warehouse_id` int NOT NULL DEFAULT '0',
    `to_warehouse_id` int NOT NULL DEFAULT '0',
    `item_id` int NOT NULL DEFAULT '0',
    `item_qty` double NOT NULL DEFAULT '0',
    `retail_qty` double NOT NULL DEFAULT '0',
    `item_rate` text NOT NULL,
    `t_qty` double NOT NULL DEFAULT '0',
    `t_rate` text NOT NULL,
    `item_total` double NOT NULL DEFAULT '0',
    `serials` text,
    `created_date` varchar(30) DEFAULT NULL,
    `branch_id` int NOT NULL,
    `status` enum('a', 'd', 'p') NOT NULL DEFAULT 'a',
    `per_unit_id` int NOT NULL DEFAULT '0',
    PRIMARY KEY (`t_d_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_transfer_details`
--

LOCK TABLES `tbl_transfer_details` WRITE;
/*!40000 ALTER TABLE `tbl_transfer_details` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_transfer_details` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_transfer_master`
--

DROP TABLE IF EXISTS `tbl_transfer_master`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_transfer_master` (
    `t_id` int NOT NULL AUTO_INCREMENT,
    `is_serial` enum('yes', 'no') NOT NULL,
    `to_branch_id` int NOT NULL DEFAULT '0',
    `transport_acc_id` int NOT NULL DEFAULT '0',
    `t_voucher_no` varchar(100) DEFAULT NULL,
    `total_transport_cost` double NOT NULL DEFAULT '0',
    `sub_total` double NOT NULL DEFAULT '0',
    `total_amount` double NOT NULL DEFAULT '0',
    `created_date` varchar(30) DEFAULT NULL,
    `narration` text,
    `created_by` int NOT NULL DEFAULT '0',
    `branch_id` int NOT NULL,
    `status` enum('a', 'd', 'p') NOT NULL DEFAULT 'a',
    PRIMARY KEY (`t_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_transfer_master`
--

LOCK TABLES `tbl_transfer_master` WRITE;
/*!40000 ALTER TABLE `tbl_transfer_master` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_transfer_master` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_users`
--

DROP TABLE IF EXISTS `tbl_users`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_users` (
    `user_id` int NOT NULL AUTO_INCREMENT,
    `user_full_name` varchar(255) DEFAULT NULL,
    `user_name` varchar(255) NOT NULL,
    `user_label` varchar(30) DEFAULT NULL,
    `user_password` text NOT NULL,
    `user_email` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
    `user_role` enum(
        'super_admin',
        'admin',
        'user'
    ) DEFAULT NULL,
    `user_access` text,
    `user_created_iso_dt` varchar(50) DEFAULT NULL,
    `user_updated_iso_dt` varchar(50) DEFAULT NULL,
    `user_created_by` int NOT NULL,
    `user_updated_by` int DEFAULT NULL,
    `user_branch_id` int NOT NULL,
    `user_warehouse_id` int NOT NULL,
    `user_status` enum(
        'active',
        'deactivated',
        'pending'
    ) DEFAULT NULL,
    `customer_id` int NOT NULL DEFAULT '0',
    `acc_type` enum('user', 'customer') NOT NULL DEFAULT 'user',
    PRIMARY KEY (`user_id`)
) ENGINE = InnoDB AUTO_INCREMENT = 2 DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_users`
--

LOCK TABLES `tbl_users` WRITE;
/*!40000 ALTER TABLE `tbl_users` DISABLE KEYS */
;

INSERT INTO
    `tbl_users`
VALUES (
        1,
        'RealTrac',
        'RealTrac',
        'super admin',
        'eba45f0373edb392.ec83524e08b67f5c0df1955155c7a864f90f5cf91f0c170dbe4a84e15020811f624f2713f255b1005ffee154e42eb990c3d1c5411a7e937019eb3dc52e1c241f',
        '',
        'super_admin',
        '[\"sales_entry\",\"pos_entry\",\"customer_entry\",\"sales_record\",\"sales_voucher\",\"sales_return_voucher\",\"sales_return\",\"product_replace\",\"sales_return_record\",\"product_replace_record\",\"sales_order_entry\",\"purchase_order_entry\",\"purchase_order_voucher\",\"sales_order_voucher\",\"sales_order_record\",\"purchase_order_record\",\"service_entry\",\"service_expense_entry\",\"service_record\",\"service_expense_record\",\"service_voucher\",\"service_expense_voucher\",\"purchase_entry\",\"supplier_entry\",\"purchase_record\",\"purchase_voucher\",\"purchase_return_voucher\",\"purchase_return\",\"purchase_return_record\",\"salary_payment\",\"employee_entry\",\"department_entry\",\"designation_entry\",\"attendance_entry\",\"monthly_salary_report\",\"creditor_payment\",\"debtor_receipt\",\"expense_entry\",\"expense_recognition_entry\",\"income_entry\",\"advance_transaction_entry\",\"branch_tran\",\"contra_entry\",\"journal_entry\",\"account_entry\",\"location_entry\",\"item_stock_report\",\"item_ledger\",\"transfer_entry\",\"item_adjustment_entry\",\"transfer_record\",\"transfer_pending_record\",\"transfer_receive_record\",\"adjustment_record\",\"production_entry\",\"production_voucher\",\"production_record\",\"crm_customer_entry\",\"pending_customer_list\",\"approved_customer_list\",\"rejected_customer_list\",\"employee_wise_customer_list\",\"quotation_entry\",\"quotation_record\",\"balance_sheet\",\"trial_balance\",\"profit_loss\",\"item_wise_profit_loss\",\"cash_bank_balance\",\"loan_balance\",\"indirect_expense_balance\",\"indirect_income_balance\",\"fixed_asset_balance\",\"capital_balance\",\"debtor_balance\",\"branch_balance\",\"creditor_balance\",\"fixed_asset_ledger\",\"loan_ledger\",\"indirect_expense_ledger\",\"indirect_income_ledger\",\"cash_bank_ledger\",\"capital_ledger\",\"debtor_ledger\",\"creditor_ledger\",\"sales_ledger\",\"purchase_ledger\",\"service_expense_ledger\",\"service_ledger\",\"sales_return_ledger\",\"purchase_return_ledger\",\"tax_ledger\",\"direct_expense_ledger\",\"debtor_receipt_record\",\"creditor_payment_record\",\"expense_record\",\"expense_recognition_record\",\"income_record\",\"journal_record\",\"contra_record\",\"salary_report\",\"direct_expense_balance\",\"direct_income_balance\",\"direct_income_ledger\",\"branch_tran_pen_list\",\"branch_tran_rcv_list\",\"branch_tran_transfer_list\",\"branch_ledger\",\"daily_ledger\",\"collection_record\",\"advance_tran_record\",\"advance_debtor_balance\",\"advance_creditor_balance\",\"item_entry\",\"item_category\",\"group_entry\",\"model_manage\",\"origin_manage\",\"item_unit\",\"user_entry\",\"warehouse_entry\",\"branch_entry\",\"company_profile\",\"sms_sender\"]',
        '2024-02-14T18:34:53.830Z',
        '2024-02-14T18:34:53.830Z',
        1,
        NULL,
        1,
        0,
        'active',
        0,
        'user'
    );
/*!40000 ALTER TABLE `tbl_users` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_voucher_transactions`
--

DROP TABLE IF EXISTS `tbl_voucher_transactions`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_voucher_transactions` (
    `tran_id` int NOT NULL AUTO_INCREMENT,
    `voucher_type` enum(
        'purchase',
        'sale',
        'purchase_return',
        'sale_return',
        'service',
        'service_expense'
    ) NOT NULL,
    `voucher_id` int NOT NULL,
    `from_acc_id` int NOT NULL DEFAULT '0',
    `to_acc_id` int NOT NULL DEFAULT '0',
    `tran_amount` double NOT NULL DEFAULT '0',
    `status` enum('a', 'd') NOT NULL DEFAULT 'a',
    PRIMARY KEY (`tran_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_voucher_transactions`
--

LOCK TABLES `tbl_voucher_transactions` WRITE;
/*!40000 ALTER TABLE `tbl_voucher_transactions` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_voucher_transactions` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_warehouses`
--

DROP TABLE IF EXISTS `tbl_warehouses`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_warehouses` (
    `warehouse_id` int NOT NULL AUTO_INCREMENT,
    `warehouse_name` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci NOT NULL,
    `warehouse_title` text CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci NOT NULL,
    `warehouse_address` text CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci NOT NULL,
    `warehouse_created_isodt` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci DEFAULT NULL,
    `warehouse_updated_isodt` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci DEFAULT NULL,
    `warehouse_created_by` int NOT NULL DEFAULT '0',
    `warehouse_updated_by` int NOT NULL DEFAULT '0',
    `warehouse_status` enum(
        'active',
        'deactivated',
        'deleted'
    ) CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci NOT NULL DEFAULT 'active',
    PRIMARY KEY (`warehouse_id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb4 COLLATE = utf8mb4_general_ci;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_warehouses`
--

LOCK TABLES `tbl_warehouses` WRITE;
/*!40000 ALTER TABLE `tbl_warehouses` DISABLE KEYS */
;
/*!40000 ALTER TABLE `tbl_warehouses` ENABLE KEYS */
;

UNLOCK TABLES;

--
-- Table structure for table `tbl_watch_token`
--

DROP TABLE IF EXISTS `tbl_watch_token`;
/*!40101 SET @saved_cs_client     = @@character_set_client */
;
/*!50503 SET character_set_client = utf8mb4 */
;

CREATE TABLE `tbl_watch_token` (
    `id` int NOT NULL AUTO_INCREMENT,
    `token` text,
    PRIMARY KEY (`id`)
) ENGINE = InnoDB AUTO_INCREMENT = 2 DEFAULT CHARSET = utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */
;

--
-- Dumping data for table `tbl_watch_token`
--

LOCK TABLES `tbl_watch_token` WRITE;
/*!40000 ALTER TABLE `tbl_watch_token` DISABLE KEYS */
;

INSERT INTO
    `tbl_watch_token`
VALUES (
        1,
        'aafe68f9d5ee4de3.28ce8d11f26f36e098804b27a88a42548c1254d5ba5df74b98d1d89b62c3918fcce0548866afd2d36aaf66deae6b59de421551bebc12a94dc98a3a8e4d8a4ae2.2024-02-14T18:34:30.707Z'
    );
/*!40000 ALTER TABLE `tbl_watch_token` ENABLE KEYS */
;

UNLOCK TABLES;
/*!40103 SET TIME_ZONE=@OLD_TIME_ZONE */
;

/*!40101 SET SQL_MODE=@OLD_SQL_MODE */
;
/*!40014 SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS */
;
/*!40014 SET UNIQUE_CHECKS=@OLD_UNIQUE_CHECKS */
;
/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */
;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */
;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */
;
/*!40111 SET SQL_NOTES=@OLD_SQL_NOTES */
;

-- Dump completed on 2024-02-15  0:37:58

-- update employees table
ALTER TABLE tbl_employees
ADD COLUMN national_id_expiry varchar(30),
ADD COLUMN visa_no varchar(20),
ADD COLUMN visa_expiry varchar(30),
ADD COLUMN labour_contract_id varchar(20),
ADD COLUMN labour_contract_expiry varchar(30),
ADD COLUMN insurance_name varchar(20),
ADD COLUMN insurance_status varchar(20),
ADD COLUMN insurance_expiry varchar(30),
ADD COLUMN reminder varchar(30);

 -- update attandance table
ALTER TABLE `tbl_emp_attendance_details`
MODIFY `attendance_date` varchar(30) NULL,
MODIFY `month` varchar(10) NULL,
MODIFY `month_day` int NULL,
MODIFY `year` varchar(4) NULL,
MODIFY `branch_id` int NULL;

ALTER TABLE tbl_emp_attendance_details
ADD COLUMN user_id int NULL,
ADD COLUMN notes varchar(30);

ALTER TABLE `tbl_users`
MODIFY `acc_type` enum(
    'user',
    'customer',
    'employee'
) DEFAULT 'user';

ALTER TABLE `tbl_users` ADD column employee_id INT NULL;
-- add company on top of branches

ALTER TABLE tbl_users
ADD CONSTRAINT fk_user_employee FOREIGN KEY (employee_id) REFERENCES tbl_employees (employee_id);

ALTER TABLE tbl_branches ADD COLUMN institution_id INT NULL;

-- ALTER TABLE tbl_branches
-- ADD CONSTRAINT fk_institution_branch FOREIGN KEY (institution_id) REFERENCES tbl_institution_profile (pro_id);

-- delete this column later
ALTER TABLE tbl_institution_profile DROP COLUMN pro_branch_id;

CREATE TABLE `tbl_software_packages` (
    `id` int NOT NULL AUTO_INCREMENT,
    `name` varchar(30) NOT NULL,
    `max_no_of_branches` int NOT NULL,
    `max_no_of_users` int NOT NULL,
    PRIMARY KEY (`id`)
) ENGINE = InnoDB DEFAULT CHARSET = utf8mb4 COLLATE = utf8mb4_general_ci;

INSERT INTO `tbl_software_packages` VALUES (1, 'Basic', 5, 5);

INSERT INTO `tbl_software_packages` VALUES (2, 'Medium', 10, 10);

ALTER TABLE tbl_institution_profile
ADD COLUMN software_package_id INT NULL;

-- ALTER TABLE tbl_institution_profile
-- ADD CONSTRAINT fk_institution_software_pkg FOREIGN KEY (software_package_id) REFERENCES tbl_software_packages (id);

ALTER TABLE tbl_emp_attendance_details
ADD COLUMN ckeck_in varchar(10),
ADD COLUMN check_out varchar(10);
-- create table holidays

CREATE TABLE tbl_holidays (
    holiday_id int auto_increment primary key,
    holiday_type varchar(30) not null,
    holiday_name varchar(30),
    location varchar(30),
    user_branch_id int not null,
    notes varchar(50),
    holiday_date varchar(30) not null
);

ALTER TABLE tbl_emp_attendance_details
MODIFY attendance enum(
    'present',
    'absence',
    'leave_with_pay',
    'leave_without_pay',
    'sick_leave',
    'casual_leave'
) NOT NULL;

ALTER TABLE tbl_emp_attendance_details
ADD status enum('pending', 'approved');

ALTER TABLE tbl_accounts
ADD column cus_status enum('active', 'inactive') DEFAULT 'active',
ADD column selectedFromAcc varchar(30),
ADD column licence_no varchar(30),
ADD column licence_validity varchar(30),
ADD column trn_no varchar(30),
ADD column vat_no varchar(30),
ADD column credit_month varchar(5),
ADD column credit_day varchar(5);

ALTER TABLE tbl_institution_profile ADD column item_tax varchar(10);

ALTER TABLE tbl_employees ADD COLUMN first_reminder varchar(10);

ALTER TABLE tbl_employees ADD COLUMN second_reminder varchar(10);

-- company/role changes
CREATE TABLE `tbl_roles` (
    `id` int NOT NULL AUTO_INCREMENT PRIMARY KEY,
    `role_name` varchar(255) DEFAULT NULL,
    `institution_id` INT NOT NULL
);

ALTER TABLE tbl_roles
ADD CONSTRAINT fk_institution_roles FOREIGN KEY (institution_id) REFERENCES tbl_institution_profile (pro_id);

CREATE TABLE `tbl_role_access` (
    `id` int NOT NULL AUTO_INCREMENT PRIMARY KEY,
    `role_id` varchar(255) DEFAULT NULL,
    `access` varchar(255) DEFAULT NULL,
    `access_type` varchar(255) DEFAULT NULL,
    `institution_id` INT NOT NULL
);

CREATE TABLE `tbl_user_role` (
    `user_id` INT NOT NULL,
    `role_id` INT NOT NULL,
    PRIMARY KEY (user_id, role_id),
    UNIQUE KEY unique_user_role (user_id, role_id)
);

INSERT INTO `tbl_roles` VALUES (1, 'admin', 1);

INSERT INTO `tbl_roles` VALUES (2, 'user', 1);

INSERT INTO `tbl_roles` VALUES (3, 'accountant', 1);

INSERT INTO `tbl_roles` VALUES (4, 'read_only_user', 1);

-- attach roles to users
INSERT INTO `tbl_user_role` VALUES (1, 1);

INSERT INTO `tbl_user_role` VALUES (2, 1);

INSERT INTO `tbl_user_role` VALUES (3, 2);

INSERT INTO `tbl_user_role` VALUES (4, 2);

INSERT INTO `tbl_user_role` VALUES (5, 2);

INSERT INTO `tbl_user_role` VALUES (6, 2);

INSERT INTO `tbl_user_role` VALUES (7, 2);

INSERT INTO `tbl_user_role` VALUES (8, 2);

INSERT INTO `tbl_user_role` VALUES (9, 2);

-- Admin role
INSERT INTO
    `tbl_role_access`
VALUES (
        1,
        1,
        'sales_entry',
        'WRITE',
        1
    );

INSERT INTO `tbl_role_access` VALUES (2, 1, 'pos_entry', 'WRITE', 1);

INSERT INTO
    `tbl_role_access`
VALUES (
        3,
        1,
        'customer_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        4,
        1,
        'sales_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        5,
        1,
        'sales_voucher',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        6,
        1,
        'sales_return_voucher',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        7,
        1,
        'sales_return',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        8,
        1,
        'product_replace',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        9,
        1,
        'sales_return_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        10,
        1,
        'product_replace_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        11,
        1,
        'sales_order_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        12,
        1,
        'purchase_order_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        13,
        1,
        'purchase_order_voucher',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        14,
        1,
        'sales_order_voucher',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        15,
        1,
        'sales_order_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        16,
        1,
        'purchase_order_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        17,
        1,
        'service_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        18,
        1,
        'service_expense_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        19,
        1,
        'service_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        20,
        1,
        'service_expense_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        21,
        1,
        'service_voucher',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        22,
        1,
        'service_expense_voucher',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        23,
        1,
        'purchase_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        24,
        1,
        'supplier_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        25,
        1,
        'purchase_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        26,
        1,
        'purchase_voucher',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        27,
        1,
        'purchase_return_voucher',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        28,
        1,
        'purchase_return',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        29,
        1,
        'purchase_return_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        30,
        1,
        'salary_payment',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        31,
        1,
        'employee_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        32,
        1,
        'department_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        33,
        1,
        'designation_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        34,
        1,
        'attendance_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        35,
        1,
        'monthly_salary_report',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        36,
        1,
        'creditor_payment',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        37,
        1,
        'debtor_receipt',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        38,
        1,
        'expense_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        39,
        1,
        'expense_recognition_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        40,
        1,
        'income_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        41,
        1,
        'advance_transaction_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        42,
        1,
        'branch_tran',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        43,
        1,
        'contra_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        44,
        1,
        'journal_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        45,
        1,
        'account_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        46,
        1,
        'location_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        47,
        1,
        'item_stock_report',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        48,
        1,
        'item_ledger',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        49,
        1,
        'transfer_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        50,
        1,
        'item_adjustment_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        51,
        1,
        'transfer_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        52,
        1,
        'transfer_pending_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        53,
        1,
        'transfer_receive_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        54,
        1,
        'adjustment_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        55,
        1,
        'production_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        56,
        1,
        'production_voucher',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        57,
        1,
        'production_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        58,
        1,
        'crm_customer_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        59,
        1,
        'pending_customer_list',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        60,
        1,
        'approved_customer_list',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        61,
        1,
        'rejected_customer_list',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        62,
        1,
        'employee_wise_customer_list',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        63,
        1,
        'quotation_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        64,
        1,
        'quotation_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        65,
        1,
        'balance_sheet',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        66,
        1,
        'trial_balance',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        67,
        1,
        'profit_loss',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        68,
        1,
        'item_wise_profit_loss',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        69,
        1,
        'cash_bank_balance',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        70,
        1,
        'loan_balance',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        71,
        1,
        'indirect_expense_balance',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        72,
        1,
        'indirect_income_balance',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        73,
        1,
        'fixed_asset_balance',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        74,
        1,
        'capital_balance',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        75,
        1,
        'debtor_balance',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        76,
        1,
        'branch_balance',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        77,
        1,
        'creditor_balance',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        78,
        1,
        'fixed_asset_ledger',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        79,
        1,
        'loan_ledger',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        80,
        1,
        'indirect_expense_ledger',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        81,
        1,
        'indirect_income_ledger',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        82,
        1,
        'cash_bank_ledger',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        83,
        1,
        'capital_ledger',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        84,
        1,
        'debtor_ledger',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        85,
        1,
        'creditor_ledger',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        86,
        1,
        'sales_ledger',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        87,
        1,
        'purchase_ledger',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        88,
        1,
        'service_expense_ledger',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        89,
        1,
        'service_ledger',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        90,
        1,
        'sales_return_ledger',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        91,
        1,
        'purchase_return_ledger',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        92,
        1,
        'tax_ledger',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        93,
        1,
        'direct_expense_ledger',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        94,
        1,
        'debtor_receipt_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        95,
        1,
        'creditor_payment_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        96,
        1,
        'expense_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        97,
        1,
        'expense_recognition_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        98,
        1,
        'income_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        99,
        1,
        'journal_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        100,
        1,
        'contra_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        101,
        1,
        'salary_report',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        102,
        1,
        'direct_expense_balance',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        103,
        1,
        'direct_income_balance',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        104,
        1,
        'direct_income_ledger',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        105,
        1,
        'branch_tran_pen_list',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        106,
        1,
        'branch_tran_rcv_list',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        107,
        1,
        'branch_tran_transfer_list',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        108,
        1,
        'branch_ledger',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        109,
        1,
        'daily_ledger',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        110,
        1,
        'collection_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        111,
        1,
        'advance_tran_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        112,
        1,
        'advance_debtor_balance',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        113,
        1,
        'advance_creditor_balance',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        114,
        1,
        'item_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        115,
        1,
        'item_category',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        116,
        1,
        'group_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        117,
        1,
        'model_manage',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        118,
        1,
        'origin_manage',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        119,
        1,
        'item_unit',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        120,
        1,
        'user_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        121,
        1,
        'warehouse_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        122,
        1,
        'branch_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        123,
        1,
        'company_profile',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        124,
        1,
        'sms_sender',
        'WRITE',
        1
    );

-- normal user role
INSERT INTO
    `tbl_role_access`
VALUES (
        125,
        2,
        'sales_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        126,
        2,
        'pos_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        127,
        2,
        'customer_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        128,
        2,
        'sales_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        129,
        2,
        'sales_voucher',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        130,
        2,
        'sales_return_voucher',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        131,
        2,
        'sales_return',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        132,
        2,
        'product_replace',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        133,
        2,
        'sales_return_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        134,
        2,
        'sales_order_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        135,
        2,
        'purchase_order_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        136,
        2,
        'purchase_order_voucher',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        137,
        2,
        'sales_order_voucher',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        138,
        2,
        'sales_order_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        139,
        2,
        'purchase_order_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        140,
        2,
        'purchase_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        141,
        2,
        'supplier_entry',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        142,
        2,
        'purchase_record',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        143,
        2,
        'purchase_voucher',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        144,
        2,
        'purchase_return_voucher',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        145,
        2,
        'purchase_return',
        'WRITE',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        146,
        2,
        'purchase_return_record',
        'WRITE',
        1
    );

-- accountant user role
INSERT INTO
    `tbl_role_access`
VALUES (
        147,
        3,
        'sales_entry',
        'READ',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        148,
        3,
        'pos_entry',
        'READ',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        149,
        3,
        'customer_entry',
        'READ',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        150,
        3,
        'sales_record',
        'READ',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        151,
        3,
        'sales_voucher',
        'READ',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        152,
        3,
        'sales_return_voucher',
        'READ',
        1
    );

-- read only user role
INSERT INTO
    `tbl_role_access`
VALUES (
        153,
        4,
        'sales_entry',
        'READ',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        154,
        4,
        'pos_entry',
        'READ',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        155,
        4,
        'customer_entry',
        'READ',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        156,
        4,
        'sales_record',
        'READ',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        157,
        4,
        'sales_voucher',
        'READ',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        158,
        4,
        'sales_return_voucher',
        'READ',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        159,
        4,
        'sales_return',
        'READ',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        160,
        4,
        'product_replace',
        'READ',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        161,
        4,
        'sales_return_record',
        'READ',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        162,
        4,
        'sales_order_entry',
        'READ',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        163,
        4,
        'purchase_order_entry',
        'READ',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        164,
        4,
        'purchase_order_voucher',
        'READ',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        165,
        4,
        'sales_order_voucher',
        'READ',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        166,
        4,
        'sales_order_record',
        'READ',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        167,
        4,
        'purchase_order_record',
        'READ',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        168,
        4,
        'purchase_entry',
        'READ',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        169,
        4,
        'supplier_entry',
        'READ',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        170,
        4,
        'purchase_record',
        'READ',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        171,
        4,
        'purchase_voucher',
        'READ',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        172,
        4,
        'purchase_return_voucher',
        'READ',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        173,
        4,
        'purchase_return',
        'READ',
        1
    );

INSERT INTO
    `tbl_role_access`
VALUES (
        174,
        4,
        'purchase_return_record',
        'READ',
        1
    );

create table `tbl_notification` (
    `notification_id` int not null auto_increment primary key,
    `notification_name` varchar(30) NOT NULL,
    `notification_date` varchar(30) default null,
    `notification_created_date` varchar(30) default null,
    `user_branch_id` int not null
);

create table `tbl_activity` (
    `activity_id` int not null auto_increment primary key,
    `activity_name` varchar(30) NOT NULL,
    `type` enum('c', 'd', 'u') NOT NULL,
    `activity_created_by` varchar(30) default null,
    `created_at` varchar(30) default null,
    `user_branch_id` int not null
);

ALTER TABLE tbl_users MODIFY column employee_id int NULL;

ALTER TABLE tbl_institution_profile
add column trade_licence_no int,
add column trade_licence_expiry varchar(10),
add column vat_licence int;

INSERT INTO
    `tbl_employees`
VALUES (
        1,
        1,
        'RealTrac',
        'ABCD',
        '0123456789',
        'My Bank',
        'Dubai',
        '12345',
        'Dubai',
        'Dubai',
        '1234567890',
        '2024-02-14T18:34:53.830Z',
        'realtrac@triac.com',
        'male',
        'single',
        10000,
        '1234',
        'RealTrac-1',
        'RealTrac-2',
        1,
        1,
        'a',
        1,
        1,
        1000,
        100,
        10,
        'August',
        '2000',
        1200,
        '1234',
        'visa-1',
        '2024-02-14T18:34:53.830Z',
        '1',
        '1',
        'insurace',
        'available',
        '2024-02-14T18:34:53.830Z',
        'test',
        'testr-1',
        'test-2'
    );
    
    

UPDATE tbl_users SET employee_id = 1 WHERE user_name = 'RealTrac';

UPDATE tbl_branches
SET
    institution_id = 1
WHERE
    branch_title = 'RealTrac';

-- DB updated on 10-08-2024 12:50 IST


INSERT INTO
    `tbl_institution_profile`(pro_id,pro_name,pro_desc,pro_logo,pro_print_type,pro_updated_by,is_warehouse,is_cal_type,is_serial,currency,is_voucher_receipt,pad_status,is_auto_challan,is_minus_stock_sale,software_package_id,item_tax,trade_licence_no,trade_licence_expiry,vat_licence)
VALUES (
        2,
        'Triac',
        'Dubai',
        'pro_logo-1708101359779',
        'a4',
        1,
        'no',
        'on_total',
        'no',
        'AED',
        'no',
        'no',
        'yes',
        'no',
        1,
        6,
        0,
        '31-12-2026',
        8
    );

INSERT INTO
    `tbl_branches`
VALUES (
        2,
        'Triac-Dubai',
        'Triac-Dubai',
        'Dubai',
        '2024-02-14T18:34:30.722Z',
        NULL,
        1,
        1,
        'active',
        2 -- institution_id
    );

INSERT INTO
    `tbl_branches`
VALUES (
        3,
        'Triac-Abudhabi',
        'Triac-Abudhabi',
        'Abudhabi',
        '2024-02-14T18:34:30.722Z',
        NULL,
        1,
        1,
        'active',
        2 -- institution_id
    );

INSERT INTO
    `tbl_branches`
VALUES (
        4,
        'Triac-Ajman',
        'Triac-Ajman',
        'Ajman',
        '2024-02-14T18:34:30.722Z',
        NULL,
        1,
        1,
        'active',
        2 -- institution_id
    );

INSERT INTO
    `tbl_branches`
VALUES (
        5,
        'RealTrac-Dubai',
        'RealTrac-Dubai',
        'Dubai',
        '2024-02-14T18:34:30.722Z',
        NULL,
        1,
        1,
        'active',
        1 -- institution_id
    );

INSERT INTO
    `tbl_branches`
VALUES (
        6,
        'RealTrac-Ajman',
        'RealTrac-Ajman',
        'Dubai',
        '2024-02-14T18:34:30.722Z',
        NULL,
        1,
        1,
        'active',
        1 -- institution_id
    );

INSERT INTO
    `tbl_employees`
VALUES (
        2,
        2,
        'Triac-Dubai',
        'ABCD',
        '0123456789',
        'My Bank',
        'Dubai',
        '12345',
        'Dubai',
        'Dubai',
        '1234567890',
        '2024-02-14T18:34:53.830Z',
        'triac_dubai@triac.com',
        'male',
        'single',
        10000,
        '1234',
        'Triac-1',
        'Triac-2',
        1,
        1,
        'a',
        2, -- branch_id 
        1,
        1000,
        100,
        10,
        'August',
        '2000',
        1200,
        '1234',
        'visa-1',
        '2024-02-14T18:34:53.830Z',
        '1',
        '1',
        'insurace',
        'available',
        '2024-02-14T18:34:53.830Z',
        'test',
        'testr-1',
        'test-2'
    );

INSERT INTO
    `tbl_users`
VALUES (
        2,
        'Triac-Dubai',
        'Triac-Dubai',
        'super admin',
        'eba45f0373edb392.ec83524e08b67f5c0df1955155c7a864f90f5cf91f0c170dbe4a84e15020811f624f2713f255b1005ffee154e42eb990c3d1c5411a7e937019eb3dc52e1c241f',
        'triac@gmail.com',
        'super_admin',
        '[\"sales_entry\",\"pos_entry\",\"customer_entry\",\"sales_record\",\"sales_voucher\",\"sales_return_voucher\",\"sales_return\",\"product_replace\",\"sales_return_record\",\"product_replace_record\",\"sales_order_entry\",\"purchase_order_entry\",\"purchase_order_voucher\",\"sales_order_voucher\",\"sales_order_record\",\"purchase_order_record\",\"service_entry\",\"service_expense_entry\",\"service_record\",\"service_expense_record\",\"service_voucher\",\"service_expense_voucher\",\"purchase_entry\",\"supplier_entry\",\"purchase_record\",\"purchase_voucher\",\"purchase_return_voucher\",\"purchase_return\",\"purchase_return_record\",\"salary_payment\",\"employee_entry\",\"department_entry\",\"designation_entry\",\"attendance_entry\",\"monthly_salary_report\",\"creditor_payment\",\"debtor_receipt\",\"expense_entry\",\"expense_recognition_entry\",\"income_entry\",\"advance_transaction_entry\",\"branch_tran\",\"contra_entry\",\"journal_entry\",\"account_entry\",\"location_entry\",\"item_stock_report\",\"item_ledger\",\"transfer_entry\",\"item_adjustment_entry\",\"transfer_record\",\"transfer_pending_record\",\"transfer_receive_record\",\"adjustment_record\",\"production_entry\",\"production_voucher\",\"production_record\",\"crm_customer_entry\",\"pending_customer_list\",\"approved_customer_list\",\"rejected_customer_list\",\"employee_wise_customer_list\",\"quotation_entry\",\"quotation_record\",\"balance_sheet\",\"trial_balance\",\"profit_loss\",\"item_wise_profit_loss\",\"cash_bank_balance\",\"loan_balance\",\"indirect_expense_balance\",\"indirect_income_balance\",\"fixed_asset_balance\",\"capital_balance\",\"debtor_balance\",\"branch_balance\",\"creditor_balance\",\"fixed_asset_ledger\",\"loan_ledger\",\"indirect_expense_ledger\",\"indirect_income_ledger\",\"cash_bank_ledger\",\"capital_ledger\",\"debtor_ledger\",\"creditor_ledger\",\"sales_ledger\",\"purchase_ledger\",\"service_expense_ledger\",\"service_ledger\",\"sales_return_ledger\",\"purchase_return_ledger\",\"tax_ledger\",\"direct_expense_ledger\",\"debtor_receipt_record\",\"creditor_payment_record\",\"expense_record\",\"expense_recognition_record\",\"income_record\",\"journal_record\",\"contra_record\",\"salary_report\",\"direct_expense_balance\",\"direct_income_balance\",\"direct_income_ledger\",\"branch_tran_pen_list\",\"branch_tran_rcv_list\",\"branch_tran_transfer_list\",\"branch_ledger\",\"daily_ledger\",\"collection_record\",\"advance_tran_record\",\"advance_debtor_balance\",\"advance_creditor_balance\",\"item_entry\",\"item_category\",\"group_entry\",\"model_manage\",\"origin_manage\",\"item_unit\",\"user_entry\",\"warehouse_entry\",\"branch_entry\",\"company_profile\",\"sms_sender\"]',
        '2024-02-14T18:34:53.830Z',
        '2024-02-14T18:34:53.830Z',
        1,
        NULL,
        2, -- branch_id
        0,
        'active',
        2,
        'user',
        2 -- employee_id
    );

INSERT INTO
    `tbl_employees`
VALUES (
        3,
        3,
        'RealTrac-Dubai',
        'ABCD',
        '0123456789',
        'My Bank',
        'Dubai',
        '12345',
        'Dubai',
        'Dubai',
        '1234567890',
        '2024-02-14T18:34:53.830Z',
        'triac_dubai@triac.com',
        'male',
        'single',
        10000,
        '1234',
        'Triac-1',
        'Triac-2',
        1,
        1,
        'a',
        5, -- branch_id 
        1,
        1000,
        100,
        10,
        'August',
        '2000',
        1200,
        '1234',
        'visa-1',
        '2024-02-14T18:34:53.830Z',
        '1',
        '1',
        'insurace',
        'available',
        '2024-02-14T18:34:53.830Z',
        'test',
        'testr-1',
        'test-2'
    );

INSERT INTO
    `tbl_users`
VALUES (
        3,
        'RealTrac-Dubai',
        'RealTrac-Dubai',
        'super admin',
        'eba45f0373edb392.ec83524e08b67f5c0df1955155c7a864f90f5cf91f0c170dbe4a84e15020811f624f2713f255b1005ffee154e42eb990c3d1c5411a7e937019eb3dc52e1c241f',
        'triac@gmail.com',
        'super_admin',
        '[\"sales_entry\",\"pos_entry\",\"customer_entry\",\"sales_record\",\"sales_voucher\",\"sales_return_voucher\",\"sales_return\",\"product_replace\",\"sales_return_record\",\"product_replace_record\",\"sales_order_entry\",\"purchase_order_entry\",\"purchase_order_voucher\",\"sales_order_voucher\",\"sales_order_record\",\"purchase_order_record\",\"service_entry\",\"service_expense_entry\",\"service_record\",\"service_expense_record\",\"service_voucher\",\"service_expense_voucher\",\"purchase_entry\",\"supplier_entry\",\"purchase_record\",\"purchase_voucher\",\"purchase_return_voucher\",\"purchase_return\",\"purchase_return_record\",\"salary_payment\",\"employee_entry\",\"department_entry\",\"designation_entry\",\"attendance_entry\",\"monthly_salary_report\",\"creditor_payment\",\"debtor_receipt\",\"expense_entry\",\"expense_recognition_entry\",\"income_entry\",\"advance_transaction_entry\",\"branch_tran\",\"contra_entry\",\"journal_entry\",\"account_entry\",\"location_entry\",\"item_stock_report\",\"item_ledger\",\"transfer_entry\",\"item_adjustment_entry\",\"transfer_record\",\"transfer_pending_record\",\"transfer_receive_record\",\"adjustment_record\",\"production_entry\",\"production_voucher\",\"production_record\",\"crm_customer_entry\",\"pending_customer_list\",\"approved_customer_list\",\"rejected_customer_list\",\"employee_wise_customer_list\",\"quotation_entry\",\"quotation_record\",\"balance_sheet\",\"trial_balance\",\"profit_loss\",\"item_wise_profit_loss\",\"cash_bank_balance\",\"loan_balance\",\"indirect_expense_balance\",\"indirect_income_balance\",\"fixed_asset_balance\",\"capital_balance\",\"debtor_balance\",\"branch_balance\",\"creditor_balance\",\"fixed_asset_ledger\",\"loan_ledger\",\"indirect_expense_ledger\",\"indirect_income_ledger\",\"cash_bank_ledger\",\"capital_ledger\",\"debtor_ledger\",\"creditor_ledger\",\"sales_ledger\",\"purchase_ledger\",\"service_expense_ledger\",\"service_ledger\",\"sales_return_ledger\",\"purchase_return_ledger\",\"tax_ledger\",\"direct_expense_ledger\",\"debtor_receipt_record\",\"creditor_payment_record\",\"expense_record\",\"expense_recognition_record\",\"income_record\",\"journal_record\",\"contra_record\",\"salary_report\",\"direct_expense_balance\",\"direct_income_balance\",\"direct_income_ledger\",\"branch_tran_pen_list\",\"branch_tran_rcv_list\",\"branch_tran_transfer_list\",\"branch_ledger\",\"daily_ledger\",\"collection_record\",\"advance_tran_record\",\"advance_debtor_balance\",\"advance_creditor_balance\",\"item_entry\",\"item_category\",\"group_entry\",\"model_manage\",\"origin_manage\",\"item_unit\",\"user_entry\",\"warehouse_entry\",\"branch_entry\",\"company_profile\",\"sms_sender\"]',
        '2024-02-14T18:34:53.830Z',
        '2024-02-14T18:34:53.830Z',
        1,
        NULL,
        5, -- branch_id
        0,
        'active',
        2,
        'user',
        3 -- employee_id
    );

-- DB updated on 10-08-2024 14:50 IST

ALTER TABLE tbl_institution_profile
MODIFY column trade_licence_expiry varchar(30);

ALTER TABLE tbl_users MODIFY user_warehouse_id INT NULL;




-- DB updated on 13-08-2024 21:14 IST

update tbl_users
set
    user_access = '[\"sales_entry\",\"pos_entry\",\"customer_entry\",\"sales_record\",\"sales_voucher\",\"sales_return_voucher\",\"sales_return\",\"product_replace\",\"sales_return_record\",\"product_replace_record\",\"sales_order_entry\",\"purchase_order_entry\",\"purchase_order_voucher\",\"sales_order_voucher\",\"sales_order_record\",\"purchase_order_record\",\"service_entry\",\"service_expense_entry\",\"service_record\",\"service_expense_record\",\"service_voucher\",\"service_expense_voucher\",\"purchase_entry\",\"supplier_entry\",\"purchase_record\",\"purchase_voucher\",\"purchase_return_voucher\",\"purchase_return\",\"purchase_return_record\",\"salary_payment\",\"employee_entry\",\"department_entry\",\"designation_entry\",\"attendance_entry\",\"monthly_salary_report\",\"creditor_payment\",\"debtor_receipt\",\"expense_entry\",\"expense_recognition_entry\",\"income_entry\",\"advance_transaction_entry\",\"branch_tran\",\"contra_entry\",\"journal_entry\",\"account_entry\",\"location_entry\",\"item_stock_report\",\"item_ledger\",\"transfer_entry\",\"item_adjustment_entry\",\"transfer_record\",\"transfer_pending_record\",\"transfer_receive_record\",\"adjustment_record\",\"production_entry\",\"production_voucher\",\"production_record\",\"crm_customer_entry\",\"pending_customer_list\",\"approved_customer_list\",\"rejected_customer_list\",\"employee_wise_customer_list\",\"quotation_entry\",\"quotation_record\",\"balance_sheet\",\"trial_balance\",\"profit_loss\",\"item_wise_profit_loss\",\"cash_bank_balance\",\"loan_balance\",\"indirect_expense_balance\",\"indirect_income_balance\",\"fixed_asset_balance\",\"capital_balance\",\"debtor_balance\",\"branch_balance\",\"creditor_balance\",\"fixed_asset_ledger\",\"loan_ledger\",\"indirect_expense_ledger\",\"indirect_income_ledger\",\"cash_bank_ledger\",\"capital_ledger\",\"debtor_ledger\",\"creditor_ledger\",\"sales_ledger\",\"purchase_ledger\",\"service_expense_ledger\",\"service_ledger\",\"sales_return_ledger\",\"purchase_return_ledger\",\"tax_ledger\",\"direct_expense_ledger\",\"debtor_receipt_record\",\"creditor_payment_record\",\"expense_record\",\"expense_recognition_record\",\"income_record\",\"journal_record\",\"contra_record\",\"salary_report\",\"direct_expense_balance\",\"direct_income_balance\",\"direct_income_ledger\",\"branch_tran_pen_list\",\"branch_tran_rcv_list\",\"branch_tran_transfer_list\",\"branch_ledger\",\"daily_ledger\",\"collection_record\",\"advance_tran_record\",\"advance_debtor_balance\",\"advance_creditor_balance\",\"item_entry\",\"item_category\",\"group_entry\",\"model_manage\",\"origin_manage\",\"item_unit\",\"user_entry\",\"warehouse_entry\",\"branch_entry\",\"company_profile\",\"sms_sender\",\"attendance_overview\",\"user_role_manage\"]'
where
    user_id = 1;

-- DB updated on 26-08-2024 21:14 IST

update tbl_users
set
    user_access = '[\"sales_entry\",\"pos_entry\",\"customer_entry\",\"sales_record\",\"sales_voucher\",\"sales_return_voucher\",\"sales_return\",\"product_replace\",\"sales_return_record\",\"product_replace_record\",\"sales_order_entry\",\"purchase_order_entry\",\"purchase_order_voucher\",\"sales_order_voucher\",\"sales_order_record\",\"purchase_order_record\",\"service_entry\",\"service_expense_entry\",\"service_record\",\"service_expense_record\",\"service_voucher\",\"service_expense_voucher\",\"purchase_entry\",\"supplier_entry\",\"purchase_record\",\"purchase_voucher\",\"purchase_return_voucher\",\"purchase_return\",\"purchase_return_record\",\"salary_payment\",\"employee_entry\",\"department_entry\",\"designation_entry\",\"attendance_entry\",\"monthly_salary_report\",\"creditor_payment\",\"debtor_receipt\",\"expense_entry\",\"expense_recognition_entry\",\"income_entry\",\"advance_transaction_entry\",\"branch_tran\",\"contra_entry\",\"journal_entry\",\"account_entry\",\"location_entry\",\"item_stock_report\",\"item_ledger\",\"transfer_entry\",\"item_adjustment_entry\",\"transfer_record\",\"transfer_pending_record\",\"transfer_receive_record\",\"adjustment_record\",\"production_entry\",\"production_voucher\",\"production_record\",\"crm_customer_entry\",\"pending_customer_list\",\"approved_customer_list\",\"rejected_customer_list\",\"employee_wise_customer_list\",\"quotation_entry\",\"quotation_record\",\"balance_sheet\",\"trial_balance\",\"profit_loss\",\"item_wise_profit_loss\",\"cash_bank_balance\",\"loan_balance\",\"indirect_expense_balance\",\"indirect_income_balance\",\"fixed_asset_balance\",\"capital_balance\",\"debtor_balance\",\"branch_balance\",\"creditor_balance\",\"fixed_asset_ledger\",\"loan_ledger\",\"indirect_expense_ledger\",\"indirect_income_ledger\",\"cash_bank_ledger\",\"capital_ledger\",\"debtor_ledger\",\"creditor_ledger\",\"sales_ledger\",\"purchase_ledger\",\"service_expense_ledger\",\"service_ledger\",\"sales_return_ledger\",\"purchase_return_ledger\",\"tax_ledger\",\"direct_expense_ledger\",\"debtor_receipt_record\",\"creditor_payment_record\",\"expense_record\",\"expense_recognition_record\",\"income_record\",\"journal_record\",\"contra_record\",\"salary_report\",\"direct_expense_balance\",\"direct_income_balance\",\"direct_income_ledger\",\"branch_tran_pen_list\",\"branch_tran_rcv_list\",\"branch_tran_transfer_list\",\"branch_ledger\",\"daily_ledger\",\"collection_record\",\"advance_tran_record\",\"advance_debtor_balance\",\"advance_creditor_balance\",\"item_entry\",\"item_category\",\"group_entry\",\"model_manage\",\"origin_manage\",\"item_unit\",\"user_entry\",\"warehouse_entry\",\"branch_entry\",\"company_profile\",\"sms_sender\",\"attendance_overview\",\"user_role_manage\",\"patient_overview\",\"doctor_overview\",\"bank_transactions\"]'
where
    user_id = 1;

alter table tbl_role_access
add column tab varchar(20);

update tbl_role_access 
set tab = 'sales'
where access in ('sales_entry','customer_entry','sales_return','product_replace','sales_voucher','sales_return_voucher','sales_record','sales_return_record','product_replace_record','');

update tbl_role_access 
set tab = 'quotation'
where access in ('quotation_entry','quotation_record');

update tbl_role_access 
set tab = 'service'
where access in ('service_entry','service_expense_entry','service_voucher','service_expense_voucher','service_record','service_expense_record');

  
update tbl_role_access 
set tab = 'order'
where access in ('sales_order_entry','purchase_order_entry','sales_order_voucher','purchase_order_voucher','purchase_order_record','sales_order_record');

update tbl_role_access 
set tab = 'purchase'
where access in ('purchase_entry','supplier_entry','purchase_return','purchase_voucher','purchase_return_voucher','purchase_record','purchase_return_record');

update tbl_role_access 
set tab = 'manufacturing'
where access in ('production_entry','production_voucher','production_record');


update tbl_role_access 
set tab = 'inventory'
where access in ('item_stock_report','item_ledger','transfer_entry','item_adjustment_entry','adjustment_record','transfer_record','transfer_pending_record','transfer_receive_record','item_entry','item_unit','group_entry','item_category','model_manage','origin_manage');

update tbl_role_access 
set tab = 'accounts'
where access in ('debtor_receipt','creditor_payment','expense_entry','expense_recognition_entry','income_entry','contra_entry','advance_transaction_entry','journal_entry','branch_tran','account_entry','location_entry','bank_transactions');

update tbl_role_access 
set tab = 'hrpayroll'
where access in ('salary_payment','attendance_entry','attendance_overview','employee_entry','department_entry','designation_entry');

update tbl_role_access 
set tab = 'reports'
where access in ('debtor_balance','creditor_balance','debtor_ledger','creditor_ledger','collection_record','debtor_receipt_record','cash_bank_balance','cash_bank_ledger','indirect_expense_balance','expense_record','daily_ledger','item_stock_report','profit_loss','item_wise_profit_loss','bill_wise_profit_loss','emi_due_list','loan_balance','balance_sheet','trial_balance','branch_tran_pen_list','branch_tran_rcv_list','branch_tran_transfer_list','advance_debtor_balance','indirect_income_balance','fixed_asset_balance','capital_balance','branch_balance','indirect_expense_ledger','fixed_asset_ledger','loan_ledger','indirect_income_ledger','capital_ledger','branch_ledger','sales_ledger','purchase_ledger','service_expense_ledger','service_ledger','sales_return_ledger','purchase_return_ledger','tax_ledger','creditor_payment_record','expense_recognition_record','income_record','journal_record','contra_record','sales_record','sales_return_record','purchase_record','purchase_return_record','production_record','salary_report','direct_expense_balance','direct_expense_ledger','direct_income_balance','direct_income_ledger','salary_report','monthly_salary_report');

update tbl_role_access 
set tab = 'pos'
where access = 'pos_entry'; 

update tbl_role_access 
set tab = 'crm'
where access in ('crm_customer_entry','pending_customer_list','approved_customer_list','rejected_customer_list','employee_wise_customer_list');


update tbl_role_access 
set tab = 'settings'
where access in ('warehouse_entry','branch_entry','sms_sender','user_entry','company_profile');

-- DB updated on 2-09-2024 21:14 IST
ALTER table tbl_institution_profile
add column department_name varchar(20),
add column street_address varchar(20),
add column po_box varchar(10),
add column phone_no varchar(20),
add column company_email varchar(30),
add column company_type varchar(20),
add column ein_ssn varchar(10),
add column tax_form varchar(20),
add column web_site varchar(20),
add column city varchar(15);

ALTER table tbl_role_access
add constraint unique_instituttion_access_role
unique (institution_id ,access,role_id,access_type);

alter table tbl_users modify user_role varchar (30);
