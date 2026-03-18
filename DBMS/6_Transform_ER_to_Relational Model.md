# LEC-8: Transform ER Model to Relational Model

## 1. Overview

- Both ER-Model and Relational Model are abstract logical representation of real world enterprises. Because the two models imply similar design principles, we can convert ER design into Relational design.
- Converting a DB representation from an ER diagram to a table format is the way we arrive at Relational DB-design from an ER diagram.

---

## 2. ER Diagram Notations to Relations

### 1. Strong Entity

- Becomes an individual table with entity name; attributes become columns of the relation.
- Entity's Primary Key (PK) is used as Relation's PK.
- FK are added to establish relationships with other relations.

### 2. Weak Entity

- A table is formed with all the attributes of the entity.
- PK of its corresponding Strong Entity will be added as FK.
- PK of the relation will be a composite PK: {FK + Partial discriminator Key}.

### 3. Single Valued Attributes

- Represented as columns directly in the tables/relations.

### 4. Composite Attributes

- Handled by creating a separate attribute in the original relation for each component of the composite attribute.
- e.g., Address: {street-name, house-no} is a composite attribute in customer relation — we add `address-street-name` & `address-house-name` as new columns and ignore "address" as an attribute.

### 5. Multivalued Attributes

- New tables (named as the original attribute name) are created for each multivalued attribute.
- PK of the entity is used as a FK column in the new table.
- Multivalued attribute's name is added as a column to define multiple values.
- PK of the new table: {FK + multivalued name}.
- e.g., For Strong entity Employee, `dependent-name` is a multivalued attribute:
  1. New table named `dependent-name` will be formed with columns `emp-id` and `dname`.
  2. PK: {emp-id, name}
  3. FK: {emp-id}

### 6. Derived Attributes

- Not considered in the tables.

---

## 3. Generalisation

**Method 1:** Create a table for the higher-level entity set. For each lower-level entity set, create a table that includes a column for each of its attributes plus a column for each attribute of the PK of the higher-level entity set.

- e.g., Banking System — generalisation of Account → saving & current:
  - Table 1: `account (account-number, balance)`
  - Table 2: `savings-account (account-number, interest-rate, daily-withdrawal-limit)`
  - Table 3: `current-account (account-number, overdraft-amount, per-transaction-charges)`

**Method 2:** An alternative if the generalisation is disjoint and complete — do not create a table for the higher-level entity set. Instead, for each lower-level entity set, create a table that includes a column for each of its attributes plus a column for each attribute of the higher-level entity set.

- Tables would be:
  - Table 1: `savings-account (account-number, balance, interest-rate, daily-withdrawal-limit)`
  - Table 2: `current-account (account-number, balance, overdraft-amount, per-transaction-charges)`

**Drawbacks of Method 2:** If used for an overlapping generalisation, some values such as balance would be stored twice unnecessarily. If the generalisation were not complete, some accounts could not be represented with this method.

---

## 4. Aggregation

- Table of the relationship set is made.
- Attributes include primary keys of entity set and aggregation set's entities.
- Also add descriptive attribute if any on the relationship.
