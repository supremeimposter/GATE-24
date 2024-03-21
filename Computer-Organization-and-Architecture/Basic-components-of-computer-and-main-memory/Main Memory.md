---
pdf: 
module: 1
lecture: "2"
date: 2024-03-17T18:18:00
version:
  - COA-24
last-revision: 
notes-taken: false
tags:
  - ComputerOrganizationAndArchitecture/Memory
---
# Main Memory

- Main memory is equally divided into small units called **cells**.
- Each cell is uniquely identified by a binary number called **address**.
- The representation of main memory is,
$$
\text{Number of cells} \times \text{size of each cell (bits)}
$$
- The capacity of the cell is decided when manufacturing the hardware.
- If there are $2^k$ cells(or locations or addresses), then minimum $k$ bits are required to uniquely identify each cell (or location or address).

> [!NOTE] 
> Addresses are not stored physically.

- Memory Address Register **MAR** is used to store the address generated by the CPU to access the memory.
- If a memory has 8 bits in a cell, then the memory is called **byte-addressable**.
- **Word** Length is a property of CPU.
- **Word-addressable** memory is a memory in which each cell size is 1 word.

````col
```col-md
flexGrow=1
===
### Byte Addressable
![[Main Memory-20240317210126736.webp]]
```
```col-md
flexGrow=1
===
### Word Addressable
![[Main Memory-20240317210135659.webp]]
```
````
- Size of Address = Number of Address Lines
- Address of a multi-byte object is the lowest address of all bytes it contains.

## Byte Ordering
- When the memory is byte-addressable and multi-byte primitive data is stored, then byte ordering (Endian-ness) comes into play.
- Endian-ness is a property of CPU (system).

> [!convention] 
> Big Endian - Start with the bigger end
> Small Endian - Start with the smaller end
> ![[Main Memory-20240318115331778.webp]]

- The most significant byte of the data is the bigger end of the data.
- The least significant byte of the data is the smaller end of the data.
- In Byte ordering, the data is ordered by **byte** and not by bit.

![[Main Memory-20240318101822147.webp]]

- Little Endian architecture starts with the least significant byte and Big Endian architecture starts with the most significant byte.

- Endian-ness property applies only to multi-byte primitive data items. Endian-ness does not apply to strings, arrays or structs.
- Endian-ness cannot change the order of an array.


> [!question] When does Endian-ness matter to a programmer?
> 1. When you store a data as integer and read it later as a character, then endian-ness causes issue.
> 2. When you transfer data files between different computers over a network, it can lead to mis-interpretation.
