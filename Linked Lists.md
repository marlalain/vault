A linked list is a linear collection of data elements whose order is not given by their physical placement in memory. Instead, each element [[Pointers|points]] to the next. It is a [[Data Structures|data structure]] consisting of a collection of [[nodes]] which together represent a [[sequence]]. In its most basic form, each node contains: data and a reference (or a pointer) to the next node in the sequence.

![Linked list](https://upload.wikimedia.org/wikipedia/commons/thumb/6/6d/Singly-linked-list.svg/2560px-Singly-linked-list.svg.png)

## Tradeoffs

- Peek -> Θ(n)
- Mutate (insert or delete) Beginning ->
	- Θ(1), known end element
	- Θ(n), unknown end element
- Mutate (insert or delete) End -> Θ(n)
- Middle (insert or delete) Middle -> Peek time + Θ(1)
- Excess space, average -> Θ(n)