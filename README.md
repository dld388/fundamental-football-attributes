# What Are the Fundamental Attributes of Player Performance in Football?

## Short Answer

Using 74 standardized performance variables from 673 outfield players at the 2026 World Cup, the analysis identifies five interpretable dimensions of player performance:

1. **Direct Engagement**
2. **Build-Up Involvement**
3. **Finishing Output**
4. **Creation**
5. **Attacking Box Presence**

The first four dimensions have the strongest statistical support. The fifth adds a useful distinction between attacking-box activity and realized finishing output, but its evidence is comparatively weaker.

## Project Overview

Football players are usually described through familiar positions and archetypes: passers, finishers, creators, ball carriers, and defenders. Those categories are useful, but they are generally defined before the data is examined.

This project takes the opposite approach.

Rather than deciding in advance what kinds of players should exist, I asked whether recurring dimensions of performance could emerge directly from the relationships among observed football statistics.

The analysis uses player-level data from **FBref, Squawka, and SofaScore** covering the 2026 World Cup. After reconciling player identities across sources, adjusting appropriate counting statistics to per-90 rates, applying a minimum playing-time threshold, and conducting robust outlier screening, the final analytical sample contained:

- **673 outfield players**
- **48 national teams**
- **74 standardized performance variables**

Player names, teams, ages, and positional labels were excluded from the PCA feature matrix.

## Methodology

The final analysis uses **classical Principal Component Analysis (PCA)** followed by **oblique Promax rotation**.

Choosing the number of dimensions was treated as a model-selection problem rather than relying on a single statistical rule.

Retention evidence included:

- Scree analysis
- Horn parallel analysis
- Original and revised MAP criteria
- Bootstrap component stability
- Principal-angle subspace stability
- Pattern-loading structure
- Cross-loadings
- Football interpretability

Because these diagnostics did not all recommend the same dimensionality, four-, five-, and six-component solutions were compared directly.

### Four Components

- **40.87%** of variance retained
- 47 variables with one salient loading
- 10 cross-loading variables

The solution was parsimonious, but it combined realized finishing with shooting and attacking-box activity.

### Five Components — Selected

- **44.56%** of variance retained
- 50 variables with one salient loading
- 10 cross-loading variables

The fifth component separated **Finishing Output** from **Attacking Box Presence**, producing a clearer distinction between converting chances and repeatedly reaching shooting situations.

### Six Components

- **47.77%** of variance retained
- 49 variables with one salient loading
- 15 cross-loading variables

The additional component increased complexity, produced more cross-loadings, and was supported by a comparatively narrow group of variables.

The five-component solution therefore provided the best balance between statistical structure, interpretability, and parsimony.

## The Five Performance Dimensions

### 1. Direct Engagement

Captures repeated direct interactions and contests with opponents.

Strong defining variables include:

- Ground duels contested
- Ground duels won
- Take-ons completed
- Tackles and other direct interaction measures

This dimension refers to active engagement with opponents. It should not be interpreted as physical speed or athleticism.

### 2. Build-Up Involvement

Represents sustained involvement in possession circulation and progression.

Strong defining variables include:

- Pass attempts
- Open-play passes
- Passes completed
- Touches and related passing activity

### 3. Finishing Output

Captures realized scoring production rather than simple shooting volume.

Strong defining variables include:

- Goals
- Non-penalty goals
- Goals from inside the box
- Conversion rate

### 4. Creation

Represents chance creation with a particularly strong crossing component.

Strong defining variables include:

- Crosses completed
- Crosses attempted
- Open-play crosses completed
- Chances created

### 5. Attacking Box Presence

Captures repeated involvement in dangerous attacking areas and shooting situations.

Strong defining variables include:

- Touches in the opposition box
- Shots excluding blocks
- Shots off target
- Big chances missed

This dimension is particularly useful because it separates **getting into shooting situations** from **actually converting them into goals**.

## An Unexpected Finding

A single, distinct defensive dimension did not emerge.

Defensive actions such as tackles, interceptions, clearances, and fouls were distributed across multiple dimensions rather than clustering into one unified defensive axis.

This does **not** imply that defense is unimportant.

One possible explanation is that conventional event statistics capture visible defensive actions more easily than off-ball positioning, maintaining team shape, closing passing lanes, and preventing opportunities before a recorded event occurs.

## Interpretation

These dimensions should not be interpreted as:

- Five independent football skills
- Player ratings
- Positional rankings
- Measures of overall player quality
- Universal dimensions that must exist in every football dataset

They describe **relative multivariate patterns of performance expression** within this tournament, measurement system, and reference population.

## Data Sources

Player-performance data were compiled from:

- FBref
- Squawka
- SofaScore

The project does not currently redistribute the raw source datasets.

## Project Outputs

- [**Jupyter Notebook — Full Analytical Workflow**](notebooks/what-are-the-fundamental-attributes-of-player-performance-in-football.ipynb)
- [**Research Paper — Full PDF**](paper/what-are-the-fundamental-attributes-of-player-performance-in-football.pdf)
- Player-level performance profiles
- 673-player radar-chart atlas
- Portfolio case study

## Repository Structure

```text
fundamental-football-attributes/
│
├── notebooks/
│   └── what-are-the-fundamental-attributes-of-player-performance-in-football.ipynb
│
├── paper/
│   └── what-are-the-fundamental-attributes-of-player-performance-in-football.pdf
│
└── README.md
