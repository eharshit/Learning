# LEC-4: Extended ER Features

## 1. Overview

Basic ER Features studied in LEC-3 can be used to model most DB features, but when complexity increases, it is better to use some Extended ER features to model the DB Schema.

---

## 2. Specialisation

- In ER model, we may require to subgroup an entity set into other entity sets that are distinct in some way with other entity sets.
- Specialisation is splitting up the entity set into further sub entity sets on the basis of their functionalities, specialities and features.
- It is a **Top-Down** approach.
- E.g., Person entity set can be divided into customer, student, employee. Person is superclass and other specialised entity sets are subclasses.
  - We have "is-a" relationship between superclass and subclass.
  - Depicted by triangle component.

### Why Specialisation?

- Certain attributes may only be applicable to a few entities of the parent entity set.
- DB designer can show the distinctive features of the sub entities.
- To group such entities we apply Specialisation, to overall refine the DB blueprint.

---

## 3. Generalisation

- It is just a reverse of Specialisation.
- DB Designer may encounter certain properties of two entities are overlapping. Designer may consider to make a new generalised entity set. That generalised entity set will be a super class.
- "is-a" relationship is present between subclass and super class.
- E.g., Car, Jeep and Bus all have some common attributes, to avoid data repetition for the common attributes. DB designer may consider to Generalise to a new entity set "Vehicle".
- It is a **Bottom-up** approach.

### Why Generalisation?

- Makes DB more refined and simpler.
- Common attributes are not repeated.

---

## 4. Attribute Inheritance

- Both Specialisation and Generalisation have attribute inheritance.
- The attributes of higher level entity sets are inherited by lower level entity sets.
- E.g., Customer & Employee inherit the attributes of Person.

### Participation Inheritance

- If a parent entity set participates in a relationship then its child entity sets will also participate in that relationship.

---

## 5. Aggregation

- How to show relationships among relationships? — Aggregation is the technique.
- Abstraction is applied to treat relationships as higher-level entities. We can call it Abstract entity.
- Avoid redundancy by aggregating relationship as an entity set itself.
