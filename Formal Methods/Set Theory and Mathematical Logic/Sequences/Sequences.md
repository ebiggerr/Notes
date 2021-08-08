# Sequence

A sequence is an ordered collection of object. If there is no objects in the collection, the sequence is the `empty sequence`, and written '$\langle$ $\rangle$' 

The expression $\langle$ a,b,c $\rangle$ denotes the sequences containing objects `a`, `b` and `c` in that order.

### Concatenation  $\frown$

Two sequences are combined in such a way that the elements of one follow the elements of the other, and order is maintained.

$\langle$ a,b,c $\rangle$  $\frown$  $\langle$ d,e $\rangle$  =  $\langle$ a,b,c,d,e $\rangle$ 

### Filtering $\upharpoonright$

$\langle$ a,b,c,d,e,d,c,b,a $\rangle$  $\upharpoonright$  $\langle$ a,d $\rangle$  =  $\langle$ a,d,d,a $\rangle$ 


### Squash 
squash(m.....n $\triangleleft$  S ) is th sequence of the element from position `m` to position of `n` of `S` (Index starts from 1)

### Head
head $\langle$ a,b,c,d,e $\rangle$  = $\langle$ a $\rangle$ 

### Tail
tail $\langle$ a,b,c,d,e $\rangle$  = $\langle$ b,c,d,e $\rangle$ 

### Front
front $\langle$ a,b,c,d,e $\rangle$  = $\langle$ a,b,c,d $\rangle$ 

### Last
last $\langle$ a,b,c,d,e $\rangle$  = $\langle$ e $\rangle$ 


