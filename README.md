# Formulation of 3-Flavor Neutrino Oscillation Probabilities in Matter with the Cayley-Hamilton Theorem

Undergraduate thesis (Physics), Universitas Gadjah Mada, 2024. Derives closed-form, perturbative approximations for three-flavor neutrino oscillation probabilities in constant-density matter, and validates them against exact numerical results.

## What this is

Neutrinos oscillate between three "flavors" (electron, muon, tau) as they travel, and that oscillation behaves differently once the neutrino is passing through matter (e.g. the Earth's crust) rather than vacuum, due to the MSW (Mikheyev-Smirnov-Wolfenstein) effect. The exact expression for the oscillation probabilities in matter is extremely long and impractical to work with directly, so this thesis:

1. Derives the eigenvalues of the flavor-basis Hamiltonian using **perturbative diagonalization**, expanding in two small parameters: `s13 = sin θ13` and `α = Δm²21/Δm²31`.
2. Uses the **Cayley-Hamilton theorem** to express the time-evolution operator as a finite polynomial in the Hamiltonian (rather than an infinite Taylor series), following the approach of Akhmedov et al. (2004) and Grönroos (2023).
3. Combines the two to derive simplified, closed-form oscillation probability formulas — expanded to third order in `s13` and `α` — for all six independent oscillation channels (Pee, Peµ, Peτ, Pµµ, Pµτ, Pττ).
4. Validates every analytic formula against a full numerical solution (matrix diagonalization + exact matrix exponential) computed in Mathematica, across a range of neutrino energies (0.5–10 GeV), and checks that unitarity holds.

The results reproduce and extend prior work by Akhmedov et al. (2004), while keeping the derivation self-contained and checked step-by-step against numerics.

## Repo contents

| File | Description |
|---|---|
| `skripsi_safa.pdf` | Full thesis (Indonesian, with English abstract) — theory, derivation, results, and discussion |
| Mathematica notebook (linked below) | All symbolic derivations and numerical validation, in Wolfram Mathematica |

The full Mathematica source is at **[SafaArdhany/Neutrino-Oscillation-in-Matter](https://github.com/SafaArdhany/Neutrino-Oscillation-in-Matter)**, referenced as Lampiran A in the thesis.

> **A note on the Mathematica notebook:** it was written under a university Wolfram license that has since expired, so it isn't actively maintained or re-run. The formulas and plots in the thesis PDF are the citable, validated results — the notebook is included for transparency into how they were derived. Anyone wanting to run or extend it can do so for free via [Wolfram Cloud](https://www.wolframcloud.com/) or the free [Wolfram Engine for Developers](https://www.wolfram.com/engine/) — no paid license required for non-commercial use.

## Key result

Six oscillation probabilities are derived in closed form as functions of the standard neutrino mixing parameters (θ12, θ13, θ23, δ, Δm²21, Δm²31), the matter potential, and baseline length — accurate to third order in the small parameters, and matching full numerical diagonalization to within ~0.1–5% depending on energy. Full derivation, all six formulas, and the validation plots are in Section 5 of the thesis.

## Reference

Ardhany, N. S. (2024). *Perumusan Probabilitas Osilasi Neutrino dalam Materi Menggunakan Teorema Cayley-Hamilton* [Formulation of 3-Flavor Neutrino Oscillation Probabilities in Matter with Cayley-Hamilton Theorem]. Undergraduate thesis, Universitas Gadjah Mada.

Key sources built upon:
- Akhmedov, E., Johansson, R., Lindner, M., Ohlsson, T., & Schwetz, T. (2004). Series expansions for three-flavor neutrino oscillation probabilities in matter. *Journal of High Energy Physics*, 04, 078.
- Grönroos, J. W. (2023). *Expansions of neutrino oscillation and decay probabilities in matter*.
