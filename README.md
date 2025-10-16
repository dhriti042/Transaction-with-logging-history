# 🏦 Bank Account Transaction System (with Logging & Twilio SMS)

This Python program simulates a **bank account system** that allows users to **withdraw** and **deposit** money while maintaining **detailed transaction logs**.  
It also includes **SMS notifications** using the **Twilio API**.

---

## 📋 Features

- ✅ Deposit and withdraw money securely  
- ⚠️ Custom exception handling (`InvalidAccountError`) for invalid operations  
- 📝 Transaction logging using Python’s built-in `logging` module  
- 📱 SMS notifications for every transaction using **Twilio**  
- 💾 All logs stored in a persistent log file (`bank_transactions.log`)  

---

## ⚙️ Logging Details

Logging is a major part of this project.  
The `logging` module is configured at the top of the script to record all activities.

### 🔧 Logging Configuration

logging.basicConfig(
    filename='bank_transactions.log',
    level=logging.INFO
)
| Log Type     | Description                                                           | Example                                                         |
| ------------ | --------------------------------------------------------------------- | --------------------------------------------------------------- |
| **INFO**     | Normal operations (account creation, deposits, withdrawals, SMS sent) | `INFO: Account created: 123456, Initial balance: ₹1000`         |
| **WARNING**  | Non-critical errors like invalid input or failed transaction          | `WARNING: Withdrawal failed: Insufficient funds for withdrawal` |
| **ERROR**    | Failed SMS messages or exceptions                                     | `ERROR: Failed to send SMS to +91XXXXXXXXXX`                    |
| **CRITICAL** | Unexpected or fatal errors                                            | `CRITICAL: Unexpected error: Twilio credentials missing`        |
INFO:root:Account created: 123456, Initial balance: ₹1000
INFO:root:Withdrawal of ₹200.00 successful. Available balance: ₹800.00 (Account: 123456)
INFO:root:Deposit of ₹500.00 successful. Available balance: ₹1300.00 (Account: 123456)
WARNING:root:Withdrawal failed: Insufficient funds for withdrawal (Account: 123456)
ERROR:root:Failed to send SMS to +91XXXXXXXXXX: TwilioRestException
