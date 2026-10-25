## Map Testing to Wab Layers 
### `Layers` of `Web Application`
1. `Presentation` (UI) - everything a user can see or inrteracts with from buttons to forms 
2. `Application` (Backend) - the brain of the programm and business logic as well to process user request  
3. `Data` (database) - the application's long term memory to store user profiles, order history and everything

### `Testing strategies` to Web Layers
* **Testing the Presentation Layer (UI)**
  1. Functional Testing  - verifies that interactive elements of web works correctly from buttons to submitting fomrs.
  2. Cross-browser And Responsiveness Testing - ensures that web can work on different browsers and adopts to different screen sizes like desktop monitor or mobile phone.
  3. Usability Testing - Is the application intuitive and easy to navigate? target is to improve user's  experience working with the web how easy and smooth to complete tasks.
  4. Accessibilty Testing -  Can people with disabilities use the application? This involves checking for things like proper color contrast, keyboard navigation, screen reader compatibility. 

* **Testing the Application Layer** (Engine room)
    1. API(Application Programming Interface) Functional Testing - Do the API endpoints work as expected? if a user sedns  a request, api is giving correct output data to the request and everything in that process
        communication between layers.
    2. Security testing - Can a user access to the data anuotharized for themselves? testing for data leaks in responses, and ensuring sensitive data is handled securely.
    3. Performace Testing - How does  API works undeer heavy workload because application might experience thousands of users making requests simultaneously.

* **Testing the Data Layer**
  1. Blueprint and Data Type Validation - Do the database table structures match the design? If a field is supposed to store a number,
                does the database prevent you from saving text in it? This testing verifies the database's fundamental architecture.
  2. Data Integrity Testing - This is the most critical part of database testing. When a record is created, updated, or deleted,
          do the changes reflect correctly in the database? For example, if a user updates their shipping address, does the addresses
          table show the new information, and is the old information correctly archived or removed? This also includes checking for 
           orphaned records or incorrect relationships between tables.
  3. Data Migration Testing -  If you are moving from an old system to a new one, was all the data transferred correctly?
    This involves writing scripts to compare the data in the source and destination databases to ensure nothing was lost or corrupted during the migration.


###  `Traceability Matrix` 
-  table that maps user requirements to the specific test cases designed to validate them
- ex: "As a user, I can update my profile information." 
- traceability matrix might look like:
  Requirement
---
- `Requirement` - As a user, I can update my profile information.
---
- `UI Test Case ID` - TC-UI-01: Verify that the "Save" button on the profile page becomes clickable after a field is edited.
---
- `API Test Case ID` - TC-API-05: Send a PUT request to /api/users/{id} with a valid payload and verify a 200 value and verify an OK response.
---
- `Database Test Case ID` - TC-DB-09: After a successful API call, query the users table to confirm that the updated_at and user information fields are correct.








