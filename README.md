exist:  0
Executing query:  INSERT INTO tbl_items (item_name, item_code, item_barcode, is_serial, is_service, group_id, category_id, model_id, origin_id, unit_id, min_sale_qty, min_sale_rate, purchase_rate, sale_rate, wholesaler_rate, retailer_rate, corporate_rate, distributor_rate, discount_per, tax_per, opening_rate, opening_qty, narration, photo, create_by, branch_ids) VALUES (?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?)
With values:  [
  'pro', 'PO003', '',  'no',
  'no',  '0',     '0', '0',
  '0',   '1',     '0', '0',
  '0',   '1',     '0', '0',
  '0',   '0',     '0', '0',
  '0',   '0',     '0', '0',
  '0',   '0',     '',  '',
  1,     1
]
Error: You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?)' at line 1
    at PromisePool.query (C:\Users\abhijith\Projects\fortherp\api\node_modules\mysql2\promise.js:356:22)
    at Transaction.create (C:\Users\abhijith\Projects\fortherp\api\src\utils\TranDB.js:66:38)
    at C:\Users\abhijith\Projects\fortherp\api\src\controlers\administration.js:4709:36
    at processTicksAndRejections (node:internal/process/task_queues:96:5)
    
