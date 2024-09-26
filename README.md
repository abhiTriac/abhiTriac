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
