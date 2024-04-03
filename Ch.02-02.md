### Motivation to data layers 
![](https://i.imgur.com/jAOh0Jq.png)

breakdown of each part of the figure:
1. **Two Layers Architecture (Data & UI)**: This is the most basic structure where the application has two layers.
	- **App**: Represents the application layer that the user interacts with.
	- **FS (File System)**: Denotes the file system where the data is stored, in this case, CSV (Comma Separated Values) data.

2.  **Three Layers Architecture (Data & BL & UI)**: An additional layer is introduced here.

	- **App**: The application layer with the user interface (UI).
	- **BL (Business Logic)**: A new layer for business logic that handles data processing, in this case, a CSV Data Loader specifically for reporting.
	- **FS**: The file system still contains CSV data, but the business logic layer separates the data processing from the application UI.

3.  **Three Layers Architecture (Data (multi-sources) & BL & UI)**: Similar to (b) but with support for multiple data formats.

	- **App**: The application UI layer.
	- **BL**: The business logic layer now handles multiple data formats, like JSON and CSV, and is still used for reporting.
	- **FS**: The file system here contains JSON data, illustrating the flexibility to work with different data formats.

4.  **Four Layers Architecture (DB (L, M, H) & UI)**: A more complex and separated structure with four layers.

	- **App**: The top layer where the application UI resides.
	- **DBMS-H (Database Management System - High)**: This layer is a ready-prepared layer for each department, possibly tailored for high-level reporting and analytics.
	- **DBMS-M (Medium)**: Handles the logical part of data structuring and managing relationships between data entities.
	- **DBMS-L (Low)**: Deals with storage, data format related tasks, and data indexing and searching algorithms.

Each of these architectural models represents a step in the "Data Abstraction Journey," showing how data handling in applications can evolve from simple direct file system access to complex, multi-layered database management systems, improving scalability, maintainability, and separation of concerns.

---
### How can we think about a data solution or challenges in the data products?

1. **Requirements Analysis**: This is the initial phase where you understand what is needed. In the context of data solutions, this might mean determining the data you need, the level of data quality required, the performance expectations, and how the data will be consumed.
    
2. **Identify the Problem (Challenges)**: Once you know the requirements, the next step is to pinpoint the exact problems or challenges you face with your current data products. These could be technical issues, scalability concerns, data integrity problems, etc.
    
3. **Think About How to Overcome the Challenges**: After identifying the challenges, you need to brainstorm possible solutions or workarounds. This could involve tactical fixes, strategic changes, adopting new technologies, or modifying workflows.
    
4. **Ask Yourself the Following Questions**:
    
    - **Can we solve the problem using the current data structure by adding new features?**: This question pushes you to think about the adaptability and scalability of your existing data structure. It's about enhancing what you already have.
    - **What if we enhance/change the data structure or modeling?**: Sometimes, incremental changes aren't enough, and a more significant overhaul of the data structure or the data model is required to meet new requirements or solve existing problems.
    - **Could it help if we change the backend engine (ex: DBMS system)?**: This question suggests evaluating the underlying systems managing your data. Switching to a different Database Management System (DBMS) could potentially offer new features, better performance, or more suitable data models that better meet the project's needs.

Each of these points guides you through a thoughtful process of problem-solving specifically tailored to data-focused products, ensuring that the solutions are robust and future-proof.

---
### Data Layers (Abstraction)
1. **Any Data Product (Database) Contains Multi-Layers**:
    
    - Data products are typically structured in layers, with each layer serving a specific purpose. This multilayer approach is common in databases, where separation of concerns is important for manageability and scalability.
2. **Each Layer Responsible for Different Tasks and Operations**:
    
    - The responsibilities of each layer are distinct. One layer might handle data storage, another data processing, and yet another might manage the user interface or API endpoints.
3. **Each Layer Interacts with (Hardware or Software or Mixed)**:
    
    - Layers can interact with various components of a computing system, which may include hardware (like physical servers or storage devices), software (like operating systems or middleware), or a combination of both.
4. **Eliminate the Complexity of Data Interactions; Not All Internal Processes Are Shared or Available for the User**:
    
    - The purpose of layering is also to simplify interactions for the end-user. Not every internal process is exposed to the user; instead, the user interfaces with a simplified system that abstracts the complexity underneath.
5. **The Developer for Each Layer Hides Irrelevant Internal Details from the Developer (Users)**:
    
    - Developers working on a specific layer will only have to concern themselves with that layer's functionality. They don't need to know the intricate details of other layers, which simplifies development and maintenance.
6. **The Process of Hiding Irrelevant Details from the Developer (User) is Called Data Abstraction**:
    
    - Data abstraction is the principle of hiding the complexities and only exposing the necessary interfaces to the users or developers. It’s a fundamental concept in software engineering that helps to reduce complexity and promote efficient development practices.

In summary, Data abstraction allows developers to work more effectively by focusing on a specific segment of the system without being overwhelmed by its entire scope.

---
### Data abstraction definition 
**Data Abstraction and Data Independence**:

- **DBMS and Complex Data-Structures**: A DBMS is designed to handle complex data structures, providing an efficient system for storing, retrieving, and manipulating databases.
- **Efficiency and Complexity Reduction**: The goal is to make the system not only efficient in terms of data retrieval but also to reduce the complexity from the user's perspective. This involves simplifying interactions with the database so that users don't need to understand or deal with the underlying complexity.
- **Abstraction in Usability**: Abstraction here means hiding the technical details of the database's storage and operations from the user. This does not mean that details are removed; rather, they are encapsulated within the system.
- **Simplification of Database Design**: By abstracting details, the overall design of the database becomes simpler for users and developers to interact with, even though the underlying structure may be highly complex.

**There are 3 levels of data abstraction**:

1. **Physical Level**: This is the lowest level of abstraction. It describes how the data is actually stored and the complex structures that hold the data. For example, it deals with file structures on the disk, indexes, etc.
    
2. **Logical/Conceptual Level**: This is the middle level of abstraction. It describes what data is stored in the database, and the relationships among those data. In other words, this level is concerned with the structure of the entire database as a whole, without considering how things are implemented.
    
3. **View Level**: This is the highest level of abstraction and deals with how users interact with the system. At this level, different users may see different views of the database, which is a subset of the database. The view level provides a personalized representation of the database according to the specific needs and rights of a user.
    

Data abstraction helps in providing data independence, which allows for the modification of the data storage and data access techniques without altering the data access language or the application programs. This encapsulation makes systems more flexible and scalable, as changes can be made to one level without affecting other levels of the system.