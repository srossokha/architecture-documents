# Code Review

[Why it matters](./whyitmatters.md)

## Points to check on code review

### Architecture / Design
1. **Single Responsibility Principle**:  A class or method should have one-and-only-one responsibility. If we have to use “and” to finish describing what a method is capable of doing, it might be at the wrong level of abstraction.
2. **Code duplication**:  Go by the “three strikes” rule. If code is copied once, it’s usually okay although not ideal. If it’s copied again, it should be refactored so that the common functionality is split out. (Can be automated)
3. **Magical strings or numbers**: Are string or numbers used in code moved to constants with meaningful names?
4. **Potential bugs**: Are there off-by-one errors? Will the loops terminate in the way we expect? Will they terminate at all?
5. **Error handling**: Are errors handled gracefully and explicitly where necessary? Have custom errors been added? If so, are they useful?
6. **Efficiency**: If there’s an algorithm in the code, is it using an efficient implementation? 
7. **Potential memory leaks**:  Are all event listeners removed when not used? Is data cleaned up if no longer used? 

### Style
1. **Class, method and variable names**: Thing should be named semantically - name should clearly state what a class, a method or variable is meant for. Check for any names that are misleading.
2. **Function length**: The rule of thumb is that a function should be less than 20 or so lines. If I see a method above 50, I feel it’s best that it be cut into smaller pieces. (Can be automated)
3. **Commented code**: Commented out lines are to be removed.
4. **Number of method arguments**: For the methods and functions, do they have 3 or fewer arguments? Greater than 3 is probably a sign that it could be grouped in a different way. (Can be automated)
4. **Readability**: Is the code easy to understand? Do you have to pause frequently during the review to decipher it?

### Documentation
1. Do comments exist and describe the intent of the code?
2. Is any unusual behaviour or edge-case handling described?
3. Are data structures and units of measurement explained (at least with Flow annotations)? 
4. Is there any incomplete code? If so, should it be removed or flagged with a suitable marker like ‘TODO’ 

### Testing
1. **Test coverage**: All new features should be covered by unit tests. Are the tests thoughtful? Do they cover the failure conditions? Are they easy to read? How fragile are they?
2. **Meets requirements**: Usually as part of the end of a review, take a look at the requirements of the story, task, or bug which the work was filed against. If it doesn’t meet one of the criteria, it’s better to bounce it back before it goes to QA.


### What should be automated?

1. Detecting code formating issues should be integrated in code publishing process
    
    > ESLint is configured to detect code formatting issues and easy to catch errors (like unused or undeclared variables, dead code). Precommit hook should be used to lints all staged files -  linting should be also used as a first phase of test running. Prepush hook should be used to run all tests  - so push will fail if linting or tests fail

2. Code formating tools should be used on project.

    > For example, [Prettier](https://github.com/prettier/prettier) could be used in js projects to enforce uniform formatting

3. Code past detection should be enabled  

    > For example, [jsinspect](https://github.com/danielstjules/jsinspect) or [jscpd](https://github.com/danielstjules/jsinspect) could be used in js projects to automatically detect copy-pasted code

4. Use code style guidelines checker

    > For example, [JS Standard](https://standardjs.com/) code style guidelines could be used on js projects to guarantee one coding standard within the project

