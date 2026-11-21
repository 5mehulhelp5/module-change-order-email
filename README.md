# BluePrint3D – Change Order Email for Magento 2 ✉️

![Magento 2.4.x](https://img.shields.io/badge/Magento-2.4.x-orange.svg)
![PHP 8.1–8.5](https://img.shields.io/badge/PHP-8.1--8.5-blue.svg)
![Licence](https://img.shields.io/badge/Licence-Free_EULA-lightgrey.svg)

Lets store staff correct the customer email address on an existing order, straight from the order view page, with no database access needed.

---

## 🛑 The Problem
Customers regularly mistype their email at checkout, and Magento gives admins no safe way to fix it. The order email is tied to the customer record, so a naive edit can detach the order from its account or collide with an address another customer already uses.

## 🛠️ The Solution
An **Edit Order Email** button on the admin order view. Submitting a new address updates the order, and the customer account if there is one, safely:

- If the new email is unused, or already belongs to the same customer, the order and account are updated straight away.
- If it belongs to a **different** customer, the admin must confirm before the order is moved to that account.
- Guest orders are updated in place with no account changes.

Every change is written to the order's status history: old and new email, the customer ID involved, and which admin made it.

## ✨ Features
- **In-context editing:** change the email without leaving the order view.
- **Guest and customer safe:** guest orders, matching accounts and conflicting accounts are each handled correctly.
- **Confirmation step:** never silently reassigns an order to another customer.
- **Full audit trail:** every change logged to the order history with the admin's name.
- **Sales grid aware:** keeps the `sales_order_grid` email column in sync.

---

## 📦 Installation

```bash
composer require blueprint3d/module-change-order-email
bin/magento module:enable BluePrint3D_ChangeOrderEmail
bin/magento setup:upgrade
bin/magento setup:di:compile
bin/magento cache:flush
```

## ⚙️ Configuration
No settings. Open any order in **Sales > Orders**, click **Edit Order Email**, enter and confirm the new address and submit. If it belongs to another customer you'll be asked to confirm the move first.

---

## 📖 Documentation
Full setup guide: [`Change Order Email Setup Guide.pdf`](Change%20Order%20Email%20Setup%20Guide.pdf).

## 📜 Licence & Support
**Copyright © 2026 BluePrint3D Ltd. All rights reserved.**

Free to use on personal and commercial stores. Resale, redistribution or sublicensing of this source code, modified or unmodified, for direct financial gain is prohibited. Full terms in [`LICENSE.txt`](LICENSE.txt).

- **Website:** [blueprint3d.dev](https://www.blueprint3d.dev/modules/change-order-email)
- **Support:** [support@blueprint3d.dev](mailto:support@blueprint3d.dev)
- **Company:** BluePrint3D Ltd, Company No. 13473806
