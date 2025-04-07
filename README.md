# adaptive_mirror_fox

## Overview

`adaptive_mirror_fox` is an intelligent and context-aware strategy designed for the **Iterated Prisoner's Dilemma Tournament**. It balances friendliness, adaptability, and strategic retaliation to maximize total score in both short and long games. The strategy evolves its behavior based on the opponent's past moves and dynamically chooses who to play against in Round 3, aiming to create the highest scoring opportunities.

The algorithm strictly follows all requirements and constraints provided for the tournament and is divided into two parts:
- **Round 1 & 2**: Implements the `strategy(...)` function that responds to each move.
- **Round 3**: Implements the `strategy_round_3(...)` function which includes both the move and opponent selection.

---

## Strategy Logic – `strategy()`

This function governs decision-making for **Rounds 1 and 2**.

### Behavior:
1. **First move**: Always cooperates to encourage mutual benefit.
2. **Revenge**: If the opponent defects **twice in a row**, it retaliates with a defection (a sign of malicious intent).
3. **Forgiveness**: If after being punished, the opponent **cooperates twice in a row**, the strategy forgives and cooperates again.
4. **Statistics-based logic**:
    - If opponent is **≥70% cooperative** → cooperate (trust is earned).
    - If opponent is **>40% defecting** → mirror their last move (caution mode).
5. **Default**: If none of the above apply → cooperate (hopeful default).

This makes it **cooperative yet cautious**, allowing it to thrive with trustworthy opponents and defend itself against hostile ones.

---

## Strategy Logic – `strategy_round_3()`

This function governs behavior for **Round 3**, where opponent selection is part of the strategy.

### Behavior:
- **Same adaptive logic as `strategy()`** is used for deciding the move.
- **Opponent Selection**:
    - Picks from available opponents who have not yet reached 200 rounds.
    - If all opponents are exhausted (all reached 200), continues with the current one.
    - Prioritizes keeping the match alive with those who still allow scoring.

This ensures:
- **Maximum utilization** of the total available rounds (1000 total)
- **Flexible pairing**: Works well with nice algorithms and avoids wasting rounds on consistently hostile ones.

