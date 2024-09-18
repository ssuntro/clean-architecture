

This repository represents a snapshot of my understanding and hands-on notes about Clean Architecture to myself future in case i confuse myself again which likely to happens...

## The myth
One of the common misconceptions about Clean Architecture is that "Contradictory flow of control is not allowed in Clean Architecture."
However, the truth is that as long as this contradiction doesn't violate the Dependency Rule—such as when using the Dependency Inversion Principle—it's acceptable.

<div style="text-align: center;">
  <img src="https://github.com/user-attachments/assets/61187af2-6a15-4f46-a4bd-8babe0a3b462" alt="image" width="700" height="500">
</div>



## The Origin of Clean
Clean Architecture is fundamentally about Separation of Concerns. How do you achieve this? By adhering to the (inward) Dependency Rule.

## When is the (inward) Dependency Rule broken?
A simple way I use to identify this is by checking if a model that's convenient for database tasks is leaking into the use case layer. In other words, is there a data model that's in the wrong place? If there is, it indicates that the inner circle is being forced to know something about the database, which it shouldn't.



In summary, I understand that the flow of control can move inward or outward as long as it does not break the Dependency Rule.

## A beneficial side effect
| problem | solution with DIP |
|----------|----------|
|   <img src="https://github.com/user-attachments/assets/7f140896-38a3-4ef2-b5f2-b663c80900ea" alt="problem" width="300" >  |   <img src="https://github.com/user-attachments/assets/fc6d2f97-af2c-456f-b98d-33c43a84e09f" alt="solution" width="300" > |

   
With DIP concept, it helps reduce cyclic references, which are often the root cause of memory leaks in many languages, such as Swift. It also prevents odd code patterns like A calling B, and B calling A, continuing in a loop. For example the situation where A is usecase and B is repository.
