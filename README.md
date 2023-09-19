# Batch-Processing-With-Remote-Database
Here we are using two databases one having table named tanmay.TBL_MERCHANT_MDR_SUMMARY, while other remote database name is IDB and it is having two database tables 1. bdbl.tbl_upi_chg_dump 2. bdbl.syn_Charge_Matrix. We are batch processing the data using these 3 tables.

Steps:
1. We will fetch the records from bdbl.tbl_upi_chg_matrix where product_code = 'UPI_PAY' from that we are fetching 'p1' (Payee_Account).
2. We will fetch the records from tanmay.TBL_MERCHANT_MDR_SUMMARY where txn_date = SysDate - 1 and payee_account matches with the 'p1' we got from bdbl.tbl_upi_chg_matrix.
3. That match records we will move to bdbl.tbl_upi_chg_dump by using batch processing with the help of schedular.
