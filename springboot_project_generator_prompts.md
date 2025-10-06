# 🚀 SPRING BOOT PROJECT GENERATOR — CLEAN PROMPT FILE (NO CODE SNIPPETS)

---

## 🧩 **STEP 1 — Generate Complete Spring Boot Project (Based on SQL)**

You are an expert backend architect.  
Generate a complete, production-ready Spring Boot 3.x (Java 17, Maven) project using Oracle Database, Spring Data JPA, Spring Web, Validation, and SpringDoc OpenAPI.

### INPUT
Below is an SQL query.  
Use it to infer entities, field types, and relationships automatically.

SQL QUERY:
SELECT o.id AS order_id,
       o.order_date,
       o.total_amount,
       c.id AS customer_id,
       c.name AS customer_name,
       c.email,
       p.id AS product_id,
       p.name AS product_name,
       p.sku,
       p.price,
       ol.quantity
FROM orders o
JOIN customers c ON o.customer_id = c.id
JOIN order_line ol ON ol.order_id = o.id
JOIN products p ON ol.product_id = p.id
WHERE o.order_date >= :startDate
  AND c.email LIKE :emailPattern
  AND o.total_amount > :minTotal;

### OBJECTIVE
Use the SQL query to generate a full Spring Boot project that:
1. Infers entities, relationships, and field types.
2. Uses Controller → Service → Repository layered architecture.
3. Includes Request and Response DTOs with proper JSON mapping.
4. Uses Spring Data JPA repositories with the above SQL translated into a parameterized query.
5. Returns all responses in JSON using a consistent response wrapper.
6. Includes:
   - Logger setup  
   - Global exception handling  
   - YML configuration with Oracle datasource  
   - SpringDoc OpenAPI setup for Swagger  
   - Unit test sample class  
   - README with build and run instructions  
7. Creates project files and folders for:
   - main application class  
   - config  
   - controller  
   - dto  
   - entity  
   - repository  
   - service and implementation  
   - exception handling  
   - util  
   - resources (application.yml)  
   - test  
8. Project must be directly runnable with Maven and must compile without manual edits.

### PROJECT SETTINGS
Project name: shop-service  
Package name: com.example.shop  
Database: Oracle  
Java version: 17  
Spring Boot version: latest 3.x  
Build tool: Maven  
Output: complete project with proper directory structure and build configuration

### OUTPUT EXPECTATION
Generate all required Java and configuration files for the project as if the user created it from scratch.  
Include relationships, repository interfaces, DTOs, validation-ready fields, and service logic inferred from the SQL.  
Comment wherever assumptions are made.  
Ensure it is ready to build and run.

---

## 🧩 **STEP 2 — Add Request Validation and Global Exception Handling**

You are enhancing the above Spring Boot project.  
Add complete field-level request validation and centralized exception management.

### OBJECTIVE
1. Add request validation annotations on DTO fields.
2. Add a global exception handler that handles validation and runtime exceptions.
3. Ensure controller methods use @Valid for request bodies and parameters.
4. Integrate validation with existing JSON response structure.
5. Update service and controller layers to align with validation rules.
6. Ensure consistent logging across all layers.
7. Include a test verifying the validation behavior.

### OUTPUT EXPECTATION
Generate or update only the files required to:
- Add DTO field validation
- Add and configure the global exception handler
- Update controller(s) to handle validation properly
Ensure all validation and error handling conform to standard Spring Boot patterns.

---

## 🧩 **(Optional) STEP 3 — Conditional Query Enhancement**

You are extending the existing project’s repository and service logic.

### OBJECTIVE
1. Implement conditional query logic for dynamic filters.
2. Use JPA CriteriaBuilder or Specification API.
3. Return results in consistent JSON response wrapper format.
4. Optimize for performance and allow pagination.
5. Add appropriate logging for query execution.

### OUTPUT EXPECTATION
Generate or modify only repository and service files to support dynamic conditional queries.  
Ensure the code is clean, production-ready, and aligned with best practices.

---

## ✅ HOW TO USE

1. **Step 1:** Paste the first block to generate the entire project.  
2. **Step 2:** Paste the second block to add validation and exception handling.  
3. **Step 3 (optional):** Paste the third block to enhance conditional query logic.
