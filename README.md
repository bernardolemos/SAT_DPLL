# SAT
### SAT solver implementation using the _DPLL Algorithm_ in _Prolog_
- [Davis–Putnam–Logemann–Loveland (DPLL) algorithm](https://en.wikipedia.org/wiki/DPLL_algorithm)
- [Boolean satisfiability problem (SAT)](https://en.wikipedia.org/wiki/Boolean_satisfiability_problem#Algorithms_for_solving_SAT)

The _Satisfiability problem (SAT)_ consists in finding the values (_TRUE_ or _FALSE_) of a formula's variable such that the formula is satisfiable (_TRUE_).

The _SAT_ problem in **NP-Complete**.



## Usage
A _propositional logic formula_ is given as _input_ to the solver (**_sat_**) and a list with all possible solutions is returned. An empty list is returned if the formula is not satisfiable.
- `*`: conjuction (**∧**)
- `+`: disjunction (**V**)
- `-`: negation (**¬**)
- _`<string>`_: variable

The solver returns a list
### Examples
The CNF formula:
`(¬p V q) ∧ (¬p V q) ∧ (p V ¬q) ∧ (p V q)` is written as `(-p+ -q)*(-p+q)*(p+ -q)*(p+q)`

**I/O examples**

    ?- sat(p1*(-p1+ -p2)*(p3+p2)*(-p7+p2)*(-p3+p4)*(-p3+p5)*(-p4+ -p+q)*(-p5+ -p6+r)*(-p+ -q+p6)*(p+p7)*(-r+p7),A).
    A = []

    ?- sat((-p+ -q)*(-p+q)*(p+ -q)*(p+q),A).
    A = []

    ?- sat(p1*(-p1+ -p2)*(-r+p7)*(r+s),A).
    A = [[p1-t,p7-t,r-t,-p2-t],[p1-t,p7-t,s-t,-p2-t],[p1-t,s-t,-p2-t,-r-t]]

    ?- sat((p+q+r)*(-p+ -q+ -r)*(p+ -q+ -rp+q+ -r)*(-p+q)*(-p+r)*(p+ -q+r),A).
    A = [[q-t,r-t,-p-t],[q-t,r-t,-p-t,-rp-t],[r-t,-p-t,-q-t]]
