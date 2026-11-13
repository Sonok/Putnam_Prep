# Putnam Prep

Putnam problems are solved with a small set of proof techniques. This repo has one folder per technique. Prep is one test at a time: one problem, one written proof, one lesson.

## How a test works

1. Say "test me." Claude picks the next test, weighted toward the highest-return techniques. The test does not say which technique it is. Spotting that is part of the test.
2. Open `tests/test_NNN.pdf`. One problem, 45 minutes, written proof. Tests are taken in number order. A hint is on page 2.
3. Hand back the proof, typed (copy `tests/my_solution.tex`) or as photos of handwriting.
4. Claude grades it out of 10 the way a Putnam grader would and explains each point lost.
5. Open `tests/test_NNN_lesson.pdf`: the technique, a tiny example, and a model proof.
6. The test, your proof, and the lesson get filed into that technique's folder.

## Difficulty

Levels follow the [AoPS competition ratings](https://artofproblemsolving.com/wiki/index.php/AoPS_Wiki:Competition_ratings), a 1 to 10 scale.

| Contest problems | AoPS level |
|---|---|
| AIME, problems 6 to 9 | 3 to 4.5 |
| USAJMO, problems 1 and 4 (easiest proofs) | 4.5 to 5 |
| AIME, problems 13 to 15 | 5.5 to 6.5 |
| **Putnam A1, A2, B1, B2** | **7** |
| Putnam A3, A4, B3, B4 | 8 |

Tests start at about level 4.5, the easiest proof problems, and climb to 6, one step below Putnam A1. Levels are my estimates. Problems do not have to be Putnam problems.

- **Score 8 or more out of 10:** the next test on that technique goes up half a level.
- **Score below 5:** the next one goes down half a level.
- **Technique is "at 6":** two level 6 tests on it scored 8 or more.
- **Everything at 6:** switch to real Putnam A1, B1, A2, B2 problems.

The aim at each level is to feel solid before moving up, not to get through the levels quickly.

## Techniques

Numbered by return: the lower the number, the more early Putnam problems it decides.

| Folder | At 6? | Tests done |
|---|---|---|
| `01_small_cases` | | |
| `02_induction` | | |
| `03_contradiction` | | |
| `04_pigeonhole` | | |
| `05_extremal` | | |
| `06_invariants` | | |
| `07_construction` | | |
| `08_bijection` | | |
| `09_modular_arithmetic` | | |
| `10_factoring_and_identities` | | |
| `11_inequalities` | | |
| `12_polynomial_roots` | | |
| `13_telescoping_and_recursion` | | |
| `14_symmetry_and_substitution` | | |
| `15_bounding_and_limits` | | |
| `16_linear_algebra` | | |

Each folder's `README.md` says what the technique is and when to reach for it, and logs the tests filed there.

## Layout

- `tests/` holds tests waiting to be taken, with their lessons. Five are ready: `test_001` and `test_002` at level 4.5, then `test_003` to `test_005` at level 6.
- `techniques/` holds one folder per technique.
- `archive/` holds the earlier session-based material. Nothing was deleted.
- `putnamprep.sty` is the shared LaTeX style.
- `Putnam_Guide copy.pdf` is the UMD Putnam Guide, used as the reference for lessons.
