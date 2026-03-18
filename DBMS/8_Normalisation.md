# LEC-8: Normalisation

## 1. Overview

Normalisation is a step towards DB optimisation.

---

## 2. Functional Dependency (FD)

- It's a relationship between the primary key attribute (usually) of the relation to that of the other attribute of the relation.
- X → Y, the left side of FD is known as a **Determinant**, the right side is known as a **Dependent**.

### Types of FD

1. **Trivial FD** — A → B has trivial functional dependency if B is a subset of A. A→A, B→B are also Trivial FD.
2. **Non-trivial FD** — A → B has a non-trivial functional dependency if B is not a subset of A. [A ∩ B is NULL].

### Rules of FD (Armstrong's Axioms)

1. **Reflexive** — If 'A' is a set of attributes and 'B' is a subset of 'A', then A → B holds. If A ⊇ B then A → B.
2. **Augmentation** — If B can be determined from A, then adding an attribute won't change anything. If A → B holds, then AX → BX holds too. ('X' being a set of attributes.)
3. **Transitivity** — If A determines B and B determines C, then A determines C. If A → B and B → C then A → C.

---

## 3. Why Normalisation?

- To avoid redundancy in the DB, not to store redundant data.
- What happens if we have redundant data? → Insertion, deletion and updation anomalies arise.

---

## 4. Anomalies

- Anomalies means abnormalities. There are three types of anomalies introduced by data redundancy.

1. **Insertion anomaly** — When certain data (attribute) cannot be inserted into the DB without the presence of other data.
2. **Deletion anomaly** — The delete anomaly refers to the situation where the deletion of data results in the unintended loss of some other important data.
3. **Updation anomaly (modification anomaly)** — The update anomaly is when an update of a single data value requires multiple rows of data to be updated. Due to updating many places, data inconsistency may arise if one forgets to update the data at all the intended places.

- Due to these anomalies, DB size increases and DB performance becomes very slow.
- To rectify these anomalies, we use the DB optimisation technique called **NORMALISATION**.

---

## 5. What is Normalisation?

- Normalisation is used to minimise the redundancy from a relation. It is also used to eliminate undesirable characteristics like Insertion, Update, and Deletion Anomalies.
- Normalisation divides composite attributes into individual attributes OR larger tables into smaller ones and links them using relationships.
- The normal form is used to reduce redundancy from the database table.

---

## 6. Types of Normal Forms

### 1NF

- Every relation cell must have atomic value.
- Relation must not have multi-valued attributes.
- Relation must be in 1NF.

### 2NF

- Relation must be in 1NF.
- There should not be any partial dependency.
  - All non-prime attributes must be fully dependent on PK.
  - Non-prime attribute cannot depend on the part of the PK.

### 3NF

- Relation must be in 2NF.
- No transitivity dependency exists.
  - Non-prime attribute should not determine a non-prime attribute.

### BCNF (Boyce-Codd Normal Form)

- Relation must be in 3NF.
- FD: A → B, A must be a super key.
  - We must not derive prime attribute from any prime or non-prime attribute.

---

## 7. Advantages of Normalisation

- Normalisation helps to minimise data redundancy.
- Greater overall database organisation.
- Data consistency is maintained in DB.
