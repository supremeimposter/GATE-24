---
pdf: lec-28, lec-28-summary
module: 5
lecture: 28, 28-summary
date: 2023-10-12T10:45:00
version:
  - DM-24
last-revision: 
notes-taken: true
tags:
  - DiscreteMath/Sets
  - DiscreteMath
---
# Partition of a Set

> [!youtube] 
> [Partition of a Set](https://www.youtube.com/watch?v=P6Azf1wPYg4)
> [Summary - Partition of a set](https://www.youtube.com/watch?v=UVfj0NaSA2Y)
> [Refinement of a Partition](https://www.youtube.com/watch?v=Mh2F1Y01lUs)

> [!quote] What is a partition of a set?
> A partition of a set is a way of splitting the set into disjoint, non empty subsets so that every element belongs to exactly one subset.

- A partition of a set $A$ is a collection of disjoint sets.
- All the elements of partition of a set $A$ are subsets of $A$.
- $\text{If } a \in \text{partition of } A, \text{ then } a \subseteq A$.
- A partition is represented by $\Pi$.

![[Pasted image 20231016085331.png|Venn diagram of Partition of a set]]

## Properties of a Partition
- A set $A$ is partitioned into `n` partitions, such that

1. $A_i \; \cap \; A_j = \phi \;, \text{ for } 1 \le i \not = j \le n$ i.e. pairwise disjoint sets
2. $A = A_1 \; \cup \; A_2 \; \cup \; \ldots \; \cup \; A_n = \bigcup\limits_{i = 1}^{n} A_i$
3. $\forall_{i} \; A_i \not = \phi$  
4. $\forall_{i} \; A_i \subseteq A$

> [!intuition] A partition of a set is again a set
> Base set should be non-empty

- Any partition of $A$ defines an [[Equivalence Relation|equivalence relation]] over $A$.
## Number of partitions of a Set
- For a base set $A$, if the $|A| = k$ then, the partitions $\Pi$ will be as follows
	- `1`- part partition
	- `2`- part partition
	- $\ldots$
	- `k`- part partition

> [!NOTE] There is no general formula for number of partitions of a set.
- The number of partitions is solely determined by the cardinality of the base set.
- While counting for the number of partitions of a set, follow a systematic manner of counting to avoid confusion.

## Examples

> [!example] ![[Pasted image 20231016090316.png]]
> ![[Pasted image 20231016090334.png]]

> [!example] $S = \{1, 2\}$
> 1- part partition
> ![[Pasted image 20231015163458.png]]
> 2- part partition
> ![[Pasted image 20231015163521.png]]

> [!example] $S = \{1, 2, 3\}$
> 1- part partition
> ![[Pasted image 20231015163229.png]]
> 2- part partition
> ![[Pasted image 20231015163251.png]]
> 3- part partition
> ![[Pasted image 20231015163319.png]]

> [!example] $A = \{a, b, c, d\}$
> ![[Pasted image 20231015164346.png]]

> [!example] $A = \mathbb{Z}$
> ![[Pasted image 20231015164649.png]]
> ![[Pasted image 20231015164700.png]]

> [!example] $A = \mathbb{N}$
> { Prime, Composite, {1} }
> { Odd, Even }


> [!pdf] lec-28-summary-partitions pg-no. 19-
> More examples 

---
