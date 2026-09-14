# What Are the Fundamental Attributes of Player Performance in Football?

## Short Answer

The data suggests four robust dimensions of player performance:
ball distribution and possession, finishing and goal threat,
chance creation and crossing, and ground-duel and ball-carrying
involvement.

Evidence for a fifth dimension appears, but it is substantially
less stable.

## Project Overview

Football players are usually described with familiar labels: passers, finishers, creators, ball carriers, defenders. But those categories are often imposed before looking at the data. This project asks a more fundamental question: if we start only with player-performance data, what underlying attributes of football emerge naturally? Rather than assuming in advance what the important dimensions should be, the objective was to let the relationships among performance statistics reveal the structure themselves.

To investigate that question, I built a reconciled player-level dataset from multiple sources covering outfield players at the 2026 World Cup. The pipeline required resolving player and team identities across sources, validating unmatched and duplicate records, converting appropriate counting statistics to per-90 rates, removing goalkeeper-specific information, and separating actual performance measures from metadata and exposure variables. After cleaning, the dimensional analysis operated on 74 performance variables.

I did not want the conclusion to depend on a single dimensionality-reduction algorithm. Classical PCA was first used as an unconstrained benchmark, followed by Sparse PCA to produce cleaner and more interpretable loading structures. I then tested Nonnegative PCA, which imposes a very different assumption by requiring component loadings to be positive. The point was not simply to find the model that produced the most attractive football interpretation, but to ask whether similar underlying concepts would survive substantially different mathematical representations of the same data.

Across those approaches, four major dimensions repeatedly emerged. One captured ball distribution and possession involvement, driven by passing volume, completions, touches, and related measures. Another represented finishing and goal threat, including goals, shots on target, conversion, and shooting output. A third reflected chance creation and crossing, while a fourth captured ground-duel, ball-carrying, and direct involvement. The ordering of the components differed between methods, but the football concepts themselves repeatedly appeared.

The analysis also produced evidence for a fifth dimension, but this is where statistical validation became especially important. Under Nonnegative PCA, the additional component clearly represented aerial and defensive-duel activity, with strong contributions from aerial duels, clearances, and last-man tackles. However, bootstrap resampling showed that this fifth component was far less reproducible than the first four. The project therefore makes an important distinction between finding an interpretable pattern in one dataset and having enough evidence to treat that pattern as a stable underlying dimension.

Ultimately, Sparse PCA provided the strongest overall representation, balancing statistical structure, sparsity, interpretability, and stability. More importantly, several Sparse PCA dimensions were independently reproduced by Nonnegative PCA despite the methods imposing very different constraints: three component pairs achieved Tucker congruence values of .9803, .9548, and .9347. That cross-method agreement provides evidence that the major dimensions are not simply artifacts of one modeling choice. The broader conclusion is that player performance appears to have a relatively compact underlying structure, centered most strongly on distribution, finishing, chance creation, and ground-duel/carrying involvement.

## Methods

- Classical PCA
- Sparse PCA
- Nonnegative PCA
- Bootstrap stability analysis
- Tucker coefficient of congruence

## Outputs

- Portfolio case study
- Jupyter notebook
- Research paper
- Figures and supporting artifacts
