# Love Dynamics: A Differential Equation Model

A numerical exploration of Steven Strogatz's classic linear model of romantic relationships, built for a computational physics course assignment. Two people's feelings are modeled as a coupled system of ODEs and solved from scratch using the Euler method — no SciPy solver, just the raw numerical scheme.

## The model

Strogatz (1988) proposed that two individuals' feelings toward each other, R(t) and N(t), evolve according to a coupled linear system:

```
dR/dt = a·R + b·N
dN/dt = c·N + d·R
```

The coefficients `a` and `c` describe how much someone's feelings are driven by their *own* current feelings (positive = eager, negative = cautious/"plays it cool"), while `b` and `d` describe how much they're driven by their *partner's* feelings (positive = responsive, negative = averse to being pursued). Different sign combinations of `(a, b, c, d)` produce qualitatively different relationship dynamics — steady convergence, oscillation ("on-again off-again"), unrequited love, or mutual escalation.

This project implements two solvers:

- `love_solution(a, b, c, d, r0, n0, A, B)` — includes optional linear external-forcing terms `A·t` and `B·t` on each equation (e.g. modeling a slowly growing/decaying outside influence).
- `love_solution2(a, b, c, d, r0, n0)` — the unforced version of the same system.

Both integrate the system forward from initial conditions `r0`, `n0` using a fixed-step Euler method and plot each person's trajectory over time.

## What's explored

The notebook runs the model across several parameter regimes corresponding to the relationship archetypes discussed in the accompanying slides:

- Mutual cautious lovers (both `a, c < 0`) — damped oscillation toward equilibrium
- Mutual eager lovers (both `a, c > 0`) — runaway escalation
- One eager, one cautious — sustained oscillation ("Romeo and Juliet")
- Unrequited love — one party's feelings decay regardless of the other's response
- Forced variants — adding a constant external "nudge" (`A`, `B`) to see how it shifts the equilibrium

## Repo contents

| File | Description |
|---|---|
| `love_solution.ipynb` | Full implementation, parameter sweeps, and plots |
| `Pemodelan_cinta_dengan_persamaan_diferensial.pptx` | Course presentation walking through the model, results, and takeaways |

## Running it

```bash
pip install -r requirements.txt
jupyter notebook love_solution.ipynb
```

## Reference

Strogatz, S. H. (1988). Love affairs and differential equations. *Mathematics Magazine*, 61(1), 35.

## Notes

This was built as a lighthearted course assignment, not a research project — the model is a simplified linear approximation and (as the slides themselves note) doesn't account for feelings changing over time or the many real-world factors a two-variable linear system can't capture. It's included here as a sample of numerical methods work (implementing Euler's method from scratch, exploring stability/oscillation across parameter regimes) rather than as a serious claim about relationships.
