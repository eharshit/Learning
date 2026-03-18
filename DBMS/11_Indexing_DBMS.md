# Indexing in DBMS

## 1. Overview

- Indexing is used to optimise the performance of a database by minimising the number of disk accesses required when a query is processed.
- The index is a type of data structure. It is used to locate and access the data in a database table quickly.
- Speeds up operations with read operations like SELECT queries, WHERE clause etc.
- **Search Key:** Contains copy of primary key or candidate key of the table or something else.
- **Data Reference:** Pointer holding the address of disk block where the value of the corresponding key is stored.
- Indexing is optional, but increases access speed. It is not the primary mean to access the tuple, it is the secondary mean.
- Index file is always sorted.

---

## 2. Indexing Methods

### Primary Index (Clustering Index)

- A file may have several indices, on different search keys. If the data file containing the records is sequentially ordered, a Primary index is an index whose search key also defines the sequential order of the file.
- **NOTE:** The term primary index is sometimes used to mean an index on a primary key. However, such usage is nonstandard and should be avoided.
- All files are ordered sequentially on some search key. It could be Primary Key or non-primary key.

#### Dense and Sparse Indices

1. **Dense Index**
   - The dense index contains an index record for every search key value in the data file.
   - The index record contains the search-key value and a pointer to the first data record with that search-key value.
   - The rest of the records with the same search-key value would be stored sequentially after the first record.
   - It needs more space to store index record itself. The index records have the search key and a pointer to the actual record on the disk.

2. **Sparse Index**
   - An index record appears for only some of the search-key values.
   - Sparse Index helps you to resolve the issues of dense Indexing in DBMS. In this method, a range of index columns stores the same data block address, and when data needs to be retrieved, the block address will be fetched.

#### Primary Indexing based on Key attribute

- Data file is sorted w.r.t primary key attribute.
- PK will be used as search-key in Index.
- Sparse Index will be formed i.e., no. of entries in the index file = no. of blocks in datafile.

#### Primary Indexing based on Non-Key attribute

- Data file is sorted w.r.t non-key attribute.
- No. of entries in the index = unique non-key attribute value in the data file.
- This is a dense index as all the unique values have an entry in the index file.
- E.g., Let's assume that a company recruited many employees in various departments. In this case, clustering indexing in DBMS should be created for all employees who belong to the same dept.

#### Multi-level Index

- Index with two or more levels.
- If the single level index becomes large enough that binary search itself would take much time, we can break down indexing into multiple levels.

---

### Secondary Index (Non-Clustering Index)

- Datafile is unsorted. Hence, Primary Indexing is not possible.
- Can be done on key or non-key attribute.
- Called secondary indexing because normally one indexing is already applied.
- No. of entries in the index file = no. of records in the data file.
- It's an example of Dense index.

---

## 3. Advantages of Indexing

- Faster access and retrieval of data.
- IO is less.

---

## 4. Limitations of Indexing

- Additional space to store index table.
- Indexing decreases performance in INSERT, DELETE, and UPDATE queries.
