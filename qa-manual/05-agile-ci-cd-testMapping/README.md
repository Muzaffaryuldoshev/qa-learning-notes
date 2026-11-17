### Agile, Waterfall, ci/cd pipeline. 

#### **The Waterfall Model: One Direction, One Chance**
- The Waterfall model is the most traditional approach to software development. It organizes work into a fixed sequence
- of phases, where each phase must be fully completed before the next one begins — much like water flowing over a series of steps.


- its biggest weaknes is its inevibilty which makes it inefficient for shifts during process. 


#### The Agile Model 
- Why 
    1. iterative 
    2. collabrative 
    3. adaptive 
- Agile was created as a direct response to the rigidity of Waterfall. Rather than planning everything upfront 
- and delivering one large product at the end, Agile breaks work into short, repeating cycles called sprints 
- — typically lasting one to four weeks.

- **Key characteristics of Agile include:**
1. `Sprints:` Short, time-boxed development cycles that produce a working product increment
2. `xCross-functional teams:` Developers, testers, designers, and business stakeholders collaborate daily
3. `Continuous feedback` - Requirements can evolve based on stakeholder input between sprints 
4. `Early and frequent testing:` QA is embedded within each sprint, not saved for the end


#### CI/CD 
-  takes the Agile philosophy of frequent delivery and accelerates it dramatically through automation.
- While Agile teams might release working software at the end of each sprint,
- CI/CD teams can release updates multiple times per day.
- CI/CD is not a replacement for Agile — it is an evolution of it, powered by automated tools and pipelines. 


#### Mapping Test Activities to Agile Phases 
- **Mindset Shift: Testing as an Activity, Not a Phase**
- **Testing During Sprint Planning (Before Development Begins)**

1. `Clarifying Requirements`: as a tester we work with product owner and developers to analyze and review the user stories 
2. `Defining Acceptance Criteria`: as a tester, defining the scope of the project and its success criteria 
3. `Test Planning and Strategy`: high-level plan for what to be tested and how, anything to be automated as well 

- **Testing During the Sprint (While Development is Active)**
1. `Writing Automated Tests`: developer workin on a feature, qa writing automated script for that feature in parallel
2. `Exploratory Testing`: testing on edge cases where automated test script dind't cover or might miss using human intelligence 
3. `Integration and API Testing`: once developers complete the feature, qa tests with other parts using API
4. `Defect Managment`: logging found bugs with clear re-procucable steps and diagnosing with developers 

- **Testing at the End of the Sprint (Showcase and Release)**
1. 





























