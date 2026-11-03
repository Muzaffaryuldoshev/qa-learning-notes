### Environments
- What is a production? 
    - an environment that real users from  teacher to parents and students interact with every single day. 
    - And it contains real data of the users from full name to their transactions and ages 
    - so if a tester performs any type of testing in that env, it affects to the real data and users.
    - Testing in production. that is why considered as unprofessional act
- there are isolated environments for each stake holder of the application
1. Dev Environment - code changes are first made and checked 
2. QA Encironment - functional and regression testing occurs against anonymized data(no real data)
3. Staging Environment - replicades production condition as closely as possible for final validation
4. Production - untouched by testers entirely as it might affect to the real data of the user 

### Selecting the right Environment. 
- `The decision framework` - ex: reression testing
1. who is performing the test? - QA Engineer 
2. What is the goal? - to check new updates are not breaking old feature functionalities. 
3. How stable does the code need to be?  it must be stable and version-controlled.
4. so correct env is QA env 

**Second scenario** 
- a project coordinator need to get the final sign-off from a client before it goes live? 
1. who is testing? - client/business analyst
2. what is the goal? - to check the application meets businees requirements and satisfies user's experience/requirement
3. How stable does the code need to be? stable and read to go live wihout bug or logic confusions. 
4. so correct env is staging env or qa env but staging env matches exactly.


### Preparing QA environment 
1. feature name and version/build number 
2. requirement links 
3. planned testing types 
4. specific  test data

### Preparing UAT Environment 
1. feature name and stable build number after qa environment is done.
2. confirmation that qa testing is complete 
3. business reviewers amd their roles 
4. Planned UAT timeframe






