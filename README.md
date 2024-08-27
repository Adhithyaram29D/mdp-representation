# MDP REPRESENTATION

## AIM:
To represent a Stochastic MDP (Markov Decision Process) problem in the following ways.

Text representation
Graphical representation
Python - Dictonary representation

## PROBLEM STATEMENT:

### Problem Description
To make admission process for a school, if the student is eligible then provide admission and if the student is not eligible than no admission is provided.
The agent's primary goal is to ensure that only eligible students are admitted to the school. This involves checking the eligibility of each student who applies and making the appropriate decision—either promoting the student to the next stage of the admission process if they are eligible or denying their admission if they are not.


### State Space
{0,1,2,3}
### Sample State
* 0 -> Apply Admission
* 1 -> Check Eligibility
* 2 -> Admission Approved
* 3 -> Admission Denied
 
### Action Space
* A0: Approve
* A1: Deny


### Sample Action
* A0: Verify/Promote Eligibility
* A1: Deny Admission/Do Nothing

### Reward Function
* If the goal is reached (Admission Approved): Reward = +1
* Else (Admission Denied or No Action): Reward = 0

### Graphical Representation
![WhatsApp Image 2024-08-27 at 17 10 03_4c49692c](https://github.com/user-attachments/assets/8bfaffe7-184c-41d1-83ae-9eebe70f0f0f)


## PYTHON REPRESENTATION:
```python
solved_mdp = {
    0: {  # State S0: Student applies
        0: [(1.0, 1, 0.0, False)],  # Verify eligibility 
        1: [(1.0, 0, 0.0, False)]   # Do nothing 
    },
    1: {  # State S1: Eligibility check
        0: [(1.0, 2, 1.0, True)],   # Approve admission 
        1: [(1.0, 3, 0.0, True)]    # Deny admission
    },
    2: {  # State S2: Admission approved (terminal)
        0: [(1.0, 2, 1.0, True)],   # Confirm admission 
        1: [(1.0, 2, 1.0, True)]    # No other action
    },
    3: {  # State S3: Admission denied (terminal)
        0: [(1.0, 3, 0.0, True)],   # Reconfirm denial
        1: [(1.0, 3, 0.0, True)]    # No other action 
    }
}
solved_mdp
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/86c03015-beee-426c-ac37-67bc387b65c9)

## RESULT:
Thus a real world problem is represented as Markov Decision Problem in the following ways
successfully:
- Text Representation
- Graphical Representation
- Python Representation

