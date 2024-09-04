This repository represents a snapshot of my understanding and hands-on notes about Clean Architecture to myself future in case i confuse myself again which likely to happens...

One of the common misconceptions about Clean Architecture is that "contradictory flow of control is not allowed in Clean Architecture."

However, the truth is that as long as this contradiction doesn't violate the Dependency Rule—such as when using the Dependency Inversion Principle—it's acceptable.

## TLDR:
Clean Architecture is fundamentally about Separation of Concerns. How do you achieve this? By adhering to the (inward) Dependency Rule.

When is the Dependency Rule broken?

A simple way I use to identify this is by checking if a model that's convenient for database tasks is leaking into the use case layer. In other words, is there a data model that's in the wrong place? If there is, it indicates that the inner circle is being forced to know something about the database, which it shouldn't.

In summary, I understand that the flow of control can move inward or outward as long as it does not break the Dependency Rule.