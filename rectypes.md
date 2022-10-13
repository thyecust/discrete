# Rectypes

> Rectype is a neologism that we have stolen from T. Forster in Cambridge; it is somewhat nonstandard, but it’s too good not to use.

We are given >=1 *atoms* and >=1 *constructors*. We are interested in the objects produced by repeated application of constructors to atoms.
We call a set X *inductive* if X contains all the atoms and is closed under the constructors.

## Linked Lists

Linked lists were invented in 1953 by Hans Peter Luhn and implemented by Newell, Shaw and Simon in 1956 in their work on AI.
A little later, McCarthy's Lisp used linked lists as foundamentional concept.

Rectype List(A): all lists over A

- atom: nil
- constructor: prep[a, L] for all a in A (other notation is a::L)

### Rotation Problem

Given a linked list of A and a positive integer s, rotate the linked list by s places.

Note that if u has length s, then Rot(u::v, s) = rev(rev(u)::rev(v)).

```c
// reverse block from lo to hi, inclusive
void reverse(int lo, int hi) {
  int i, j, m = (hi - lo) / 2;
  for (i = lo, j = hi; i < m; i++, j--)
    swap(i, j);
}

// rotate left, len length of array
void rotate_left(int s) {
  s = s mod len;
  reverse(0, s - 1);
  reverse(s, len - 1);
  reverse(0, len - 1);
}
```
