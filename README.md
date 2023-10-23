# EXP04-Implement Simple Hill Climbing Algorithm

#### NAME: K.M.Swetha
#### REG NO: 212221240055

## AIM:
Implement Simple Hill Climbing Algorithm and Generate a String by Mutating a Single Character at each iteration

## THEORY:
Hill climbing is a variant of Generate and test in which feedback from test procedure is used to help the generator decide which direction to move in search space. Feedback is provided in terms of heuristic function

## ALGORITHM:

1. Evaluate the initial state.If it is a goal state then return it and quit. Otherwise, continue with initial state as current state.
2. Loop until a solution is found or there are no new operators left to be applied in current state:
* Select an operator that has not yet been applied to the current state and apply it to produce a new state
* Evaluate the new state:
  
  * if it is a goal state, then return it and quit
  * if it is not a goal state but better than current state then make new state as current state
  * if it is not better than current state then continue in the loop

### STEPS:

<b> Step 1: </b> Generate Random String of the length equal to the given String

<b> Step 2: </b> Mutate the randomized string each character at a time

<b> Step 3: </b> Evaluate the fitness function or Heuristic Function

<b> Step 4: </b> Lopp Step -2 and Step-3 until we achieve the score to be Zero to achieve Global Minima.


## PROGRAM:
```python
import random
import string
def generate_random_solution(answer):
    l=len(answer)
    return [random.choice(string.printable) for _ in range(l)]
def evaluate(solution,answer):
    print(solution)
    target=list(answer)
    diff=0
    for i in range(len(target)):
        s=solution[i]
        t=target[i]
        diff +=abs(ord(s)-ord(t))
    return diff
def mutate_solution(solution):
    ind=random.randint(0,len(solution)-1)
    solution[ind]=random.choice(string.printable)
    return solution
def SimpleHillClimbing():
    answer="Artificial Intelligence"
    best=generate_random_solution(answer)
    best_score=evaluate(best,answer)
    while True:
        print("Score:",best_score," Solution : ","".join(best))  
        if best_score==0:
            break
        new_solution=mutate_solution(list(best))
        score=evaluate(new_solution,answer)   
        if score<best_score:
            best=new_solution
            best_score=score
#answer="Artificial Intelligence"
#print(generate_random_solution(answer))
#solution=generate_random_solution(answer)
#print(evaluate(solution,answer))
SimpleHillClimbing()

```
### Sample Input and Output:

<b> SAMPLE STRING: </b>   Artificial Intelligence

![image](https://github.com/Aashima02/AI04-Implement-Simple-Hill-Climbing-Algorithm/assets/93427086/0a72b72b-e7cf-4d98-8612-e8b695fd0c5e)

......................................
......................................
......................................

![image](https://github.com/Aashima02/AI04-Implement-Simple-Hill-Climbing-Algorithm/assets/93427086/e8f9fba8-dac5-46b8-a471-9dab40cc85e2)





## RESULT:


Thus, a program was generated to implement Simple Hill Climbing Algorithm and Generate a String by Mutating a Single Character at each iteration
