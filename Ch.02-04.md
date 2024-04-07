# Logical Layer 
- It's an intermediate level of the database architecture.
- This layer describes what data is stored in the database.
- It explains the relationships between different types of stored data.
- Changes can be made at this level without affecting the external view or the actual programs that interface with the database (via APIs or direct queries).

- **Possible changes at the logical layer include:**

	- Adding new tables to the database schema.
	- Modifying records by merging or deleting them, which does not impact the applications in use.
	- Changing attributes in tables, such as adding or deleting them.