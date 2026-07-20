
[[chubb]]
[[TIQ]]

anls1 = US EQ + US FL + CAN EQ + CAN FL (grouped analysis): produced by RM or imported into platform

  

1

2

3

  
  

convert event rate loss using ERS A: Legal entity anls a:

---> 1 --> c1 --> c1 * 0.8

--> 2 --> c2 --> c2 * 0.75

--> 3 --> c3 --> c3 * 1

  

convert event rate loss using ERS B: Legal entity anls b:

---> 1 --> c4 --> c1 * 0.9

--> 2 --> c5 --> c2 * 0.7

--> 3 --> c6 --> c3 * 0.8

  
  

Split the events relevant to legal entity and apply event rates (repeated for all analyses under a legal entity)

  

BH

--> node 1 for legal entity P --> anls a

--> node 2 for legal entity Q --> anls b