## Static vs Dynamic Testing Techniques 
- **Static Testing** - Reviewing the Blueprint 
    - The goal is to find defects early on the stage so they costs almost notohing but a few of negotiations, results in nothing 
    - examples: reviewing requirement, inspecting design mockups, and peer-reviewing code
  
- **Dynamic Testing** - Walkiing through the finished product 
    - the goal is to test ready-to-use application and executing it to see all elements working correctly 
    - example: standard way of testing, actively using the application from testing mindset
  
### Test Levels 
1. `Unit Testing` - Unit "one specific part of the application", done by developers to verify that piece works correctly
   - ex: function testing called calculatePrice() developer should test with different price tag and tax amount
2. `Integration Testing` - verifies the flow between integrated units and dome by both developers and qa engineers 
  - ex: registration form(Unit A) sending data to the Database (Unit B) and in database a new user being created as requested in the form 
3. - `System Testing` - Testing the application end to end in a complete format against to businees and technical requirements (QA Team does it)
  - ex: a qa tester following to user's full journey in a e-commerce website from seaching for a product to completing the payment.
4. `Acceptance Testing` - that requires more involvement of end users as it verifies that software meets business need and answering to a question 
   - "is this what you asked for? " 

