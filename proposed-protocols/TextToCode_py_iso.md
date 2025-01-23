#  Text to Code Python  - Stand Alone



## Goal

Given a text description of a current event the model should produce an satirical image with the goal of maximizing entertainment value relevant to the event.  

Coding challanges will be seeded with leetcode style prompts but may be anything that does not require integration of external dependecies. The solutions must be possible stand alone with local execution. The solution must also be possible within 1MB of code.  

## Evaluation 

Validators are expected to create their own coding challanges and hidden test cases.  The miners responses will be executed in an isolated  enviroment and performance measured as well as correctness for an automated score. 

Where all programs are equally fast and correct, size of the program may be considered (ignoring names and whitespace) akin to kolmogorov complexity. 


## Actions 

### `textToCode_py_iso()`
- **Params**:
  - `prompt` (string):  Text the program to write.  Max 4000 characters.  
- **Returns**:
   - `text` code with imports all in one file 
    - Text must be <1MB in size 

- **Performance  Requirements**:
    - Query response within 90 seconds
    - Programs must solve the problem within 30seconds on a single core else execution will be halted.  
    - Rate limit of at least 1 request per 30 seconds.
    - Minimum 100 API calls per subscription per month.




