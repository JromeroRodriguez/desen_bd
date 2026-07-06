## Project Description
This repository contains the normalization process and database design for RiwiSupply S.A.S. The project migrates an unstandardized, redundant single Excel file into an optimized PostgreSQL relational model under Third Normal Form (3FN).

## Technologies Used
- **Database Engine:** PostgreSQL 15+ / pgAdmin 4
- **Modeling:** Mermaid.js / Draw.io
- **Language:** SQL (DDL, DML)

## Explanation of Normalization Process
1. **1FN:** Atomic values were ensured; repeating multi-valued records in Excel rows were split.
2. **2FN:** Tables like `riwi_products` and `riwi_suppliers` were generated, stripping attributes that didn't fully depend on the primary keys.
3. **3FN:** Transitive dependencies were solved by isolating cities into their own `riwi_cities` entity instead of maintaining them directly inside warehouses or suppliers.

## Database Structure
All entities use the mandatory `riwi_` prefix and are strictly named in English:
- `riwi_cities` (Master)
- `riwi_categories` (Master)
- `riwi_suppliers` (Relation)
- `riwi_warehouses` (Relation)
- `riwi_products` (Relation)
- `riwi_purchase_orders` (Relation)
- `riwi_inventory_movements` (Fact/Transaction)

## Instructions to Create the Database
1. Open pgAdmin 4 and create a database named `bd_[your_name]_[your_lastname]_[your_clan]`.
2. Open the Query Tool and execute the DDL script in order (Independent tables first, transaction tables last).


