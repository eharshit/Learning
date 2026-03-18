# LEC-12: Transaction

## 1. Transaction

- A unit of work done against the DB in a logical sequence.
- Sequence is very important in transaction.
- It is a logical unit of work that contains one or more SQL statements. The result of all these statements in a transaction either gets completed successfully (all the changes made to the database are permanent) or if at any point any failure happens it gets rolled back (all the changes being done are undone).

---

## 2. ACID Properties

To ensure integrity of the data, we require that the DB system maintain the following properties of the transaction.

### Atomicity

- Either all operations of a transaction are reflected properly in the DB, or none are.

### Consistency

- Integrity constraints must be maintained before and after transaction.
- DB must be consistent after transaction happens.

### Isolation

- Even though multiple transactions may execute concurrently, the system guarantees that for every pair of transactions Ti and Tj, it appears to Ti that either Tj finished execution before Ti started, or Tj started execution after Ti finished.
- Thus, each transaction is unaware of other transactions executing concurrently in the system.
- Multiple transactions can happen in the system in isolation, without interfering with each other.

### Durability

- After transaction completes successfully, the changes it has made to the database persist, even if there are system failures.

---

## 3. Transaction States

### Active State

- The very first state of the life cycle of the transaction — all the read and write operations are being performed.
- If they execute without any error, the transaction comes to Partially Committed state.
- If any error occurs, it leads to a Failed state.

### Partially Committed State

- After the transaction is executed, the changes are saved in the buffer in the main memory.
- If the changes made are permanent on the DB, the state will transfer to the Committed state.
- If there is any failure, the transaction will go to Failed state.

### Committed State

- When updates are made permanent on the DB, the transaction is said to be in the Committed state.
- Rollback can't be done from the committed state.
- New consistent state is achieved at this stage.

### Failed State

- When the transaction is being executed and some failure occurs. Due to this, it is impossible to continue the execution of the transaction.

### Aborted State

- When the transaction reaches the Failed state, all the changes made in the buffer are reversed.
- After that the transaction is rolled back completely. Transaction reaches the Abort state after rollback.
- DB's state prior to the transaction is achieved.

### Terminated State

- A transaction is said to have terminated if it has either committed or aborted.
