# adaptive_mirror_fox

## Overview

`adaptive_mirror_fox` is a strategic algorithm created for the Iterated Prisoner's Dilemma tournament (Part 1). It is designed to promote cooperation while defending itself intelligently when facing betrayal. The algorithm is written in pure Python and fully respects all tournament rules, including runtime, memory usage, and input constraints.

---

## How the algorithm works

The algorithm starts by cooperating on the first move. It monitors the opponent's behavior throughout the game and adapts its own response accordingly:

- If the opponent defects twice in a row, the algorithm retaliates by defecting.
- If the opponent cooperates twice after being punished, the algorithm forgives and returns to cooperation.
- If the opponent is at least 70% cooperative overall, the algorithm continues to cooperate.
- If the opponent defects more than 40% of the time, the algorithm mirrors their last move.
- In all other cases, it defaults to cooperation.

This adaptive approach helps the algorithm earn points efficiently with trustworthy players while avoiding exploitation by hostile ones.

---

## Character

The strategy is **neat** — it never defects first and favors cooperation by default. It punishes repeated betrayal but is also capable of forgiving and rebuilding trust.

---

## File Contents

- `adaptive_mirror_fox.py`: Contains the `strategy()` function used in Round 1 and Round 2 of the tournament.


