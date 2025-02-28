# Entity and Attribute Changes Guide

## How to Create a New Entity or Add/Change an Attribute

### Creating a New Entity

1. **Define the Entity**:
   - Determine the entity name and its attributes.
   - Write a brief description of what the entity represents.

2. **Update Data Dictionary**:
   - Add a new row to the data dictionary table in `erd_and_data_dictionary.md`.

   **Example**:
```markdown
   | Entity Name          | Attributes                                             | Description                                  |
   |----------------------|--------------------------------------------------------|----------------------------------------------|
   | NewEntity            | id, attribute1, attribute2, ..., attributeN             | Description of the new entity                |

```

3. **Update ERD Diagram**:
    
    - Add the new entity to the ERD diagram section of `erd_and_data_dictionary.md`.
        
    
    **Example**:
    
    mermaid
    
    ```
    erDiagram
        NewEntity {
            int id PK
            string attribute1
            string attribute2
            ...
            string attributeN
        }
        # Add relationships as needed
    ```
    

### Adding/Changing an Attribute on an Existing Entity

1. **Identify the Entity**:
    
    - Find the entity in the data dictionary and ERD diagram.
        
2. **Update Data Dictionary**:
    
    - Modify the attributes in the data dictionary table for the entity.
        
    
    **Example**:
    
    markdown
    
    ```
    | Entity Name          | Attributes                                             | Description                                  |
    |----------------------|--------------------------------------------------------|----------------------------------------------|
    | ExistingEntity       | id, existing_attribute1, new_attribute, ..., existing_attributeN | Description of the existing entity           |
    ```
    
3. **Update ERD Diagram**:
    
    - Modify the entity attributes in the ERD diagram.
        
    
    **Example**:
    
    mermaid
    
    ```
    erDiagram
        ExistingEntity {
            int id PK
            string existing_attribute1
            string new_attribute
            ...
            string existing_attributeN
        }
        # Update relationships as needed
    ```
    

## Steps to Add New Attributes or Entities

1. **Update the Data Dictionary** (`design/data_dictionary.md`)
    
2. **Update the ERD** (`design/erd.md`)
    
3. **Update the API Documentation** (`implementation/api_documentation.md`)
    
4. **Update the Functional Requirements** (`requirements/functional_requirements.md`)
    
5. **Update the Non-Functional Requirements** (`requirements/non_functional_requirements.md`)
    
6. **Update the Test Plan** (`testing/test_plan.md`)
    
7. **Update the Test Cases** (`testing/test_cases.md`)
    
8. **Update the User Manual** (`user_guide/user_manual.md`)
    
9. **Update the FAQ** (`user_guide/faq.md`)
    
10. **Review the Deployment Guide** (`deployment/deployment_guide.md`)
    
11. **Update Continuous Integration Configurations** (`deployment/continuous_integration.md`)