Monte Carlo Simulations of Betting Strategies

This repository contains a series of Python scripts that use Monte Carlo methods to simulate, analyze, and visualize the outcomes of various betting strategies in a game of chance. The project evolves from a simple command-line simulation to a sophisticated analysis of risk, reward, and return on investment, complete with 2D and 3D data visualizations.

The core of the simulation is a simple dice roll with a slightly less than 50% chance of winning, modeling a typical casino game with a house edge.

Table of Contents

Project Description

Betting Strategies Explored

Progression of the Scripts

Prerequisites

How to Run the Scripts

Key Findings & Disclaimer

Project Description

This project aims to answer a fundamental question: Can a betting strategy overcome the house edge in the long run?

Using Python, we build a simulation environment to test several popular strategies. We track the funds of thousands of simulated "bettors" over time, measuring key metrics like:

Volatility: The wild swings in a player's bankroll.

Bust Rate: The percentage of players who lose their entire starting funds.

Profit Chance: The percentage of players who end with more money than they started with.

Return on Investment (ROI): The net profit or loss across all simulations combined.

The scripts make extensive use of the random library for the game simulation and matplotlib for visualization.

Betting Strategies Explored

Simple Bettor: Bets the same fixed amount every time. A baseline strategy.

Martingale (Doubler) System: Doubles the wager after every loss. This is a high-risk, high-volatility strategy.

Custom Multiplier System: A variation of the Martingale where the wager is multiplied by a variable amount after a loss. The scripts explore how to optimize this multiplier.

D'Alembert System: A more conservative progression system where the wager is increased by one unit after a loss and decreased by one unit after a win.

Labouchere System: A cancellation system where the bettor uses a sequence of numbers to determine their wager size, aiming to cross off all numbers in the sequence.

Progression of the Scripts

The scripts are numbered to show a clear evolution from basic concepts to complex analysis.

mont1.py & mont2.py: The foundation. A simple dice roll function and a simple_bettor function that simulates a series of bets and prints the results to the console.

mont3.py: Introduction to visualization. This script plots the journey of multiple simple_bettors on a 2D graph using matplotlib, showing how their funds change over time.

mont4.py - mont6.py: Introducing a new strategy. The doubler_bettor (Martingale) is created and simulated. These scripts begin to track the broke_count to quantify risk.

mont7.py - mont9.py: Direct comparison and statistical analysis. The simple_bettor and doubler_bettor are run for a large sample size. The scripts calculate and print the precise "Bust Chances" and "Profit Chances" for each, offering a clear statistical comparison of the two strategies.

mont10.py: Optimization. The multiple_bettor is introduced to find an "optimal" multiplier for a Martingale-style system that might yield a lower bust rate and higher profit chance.

mont11.py & mont14.py: Introducing the D'Alembert system. These scripts run thousands of simulations with random parameters (wagerSize, wagerCount) to find profitable configurations and save the results (ROI, wager size, etc.) into a monteCarlo.csv file for later analysis.

mont12.py & mont13.py: Focus on ROI. These scripts shift the analysis to the most critical metric: overall profitability. They calculate the total money invested versus the total money returned across millions of simulations to see if a strategy is profitable in the aggregate.

mont15.py & mont16.py: Advanced Data Visualization. These scripts read the monteCarlo.csv file and use it to generate 2D and 3D scatter plots. This helps visualize the relationships between wager size, wager count, and ROI, making it possible to spot trends in the data.

mont17.py: The Labouchere System. This script implements and simulates the more complex Labouchere betting system, tracking wager sizes and fund progression to calculate its overall viability.

Prerequisites

To run these scripts, you will need Python 2 or 3 and matplotlib.

You can install the necessary library using pip:

code
Bash
download
content_copy
expand_less
pip install matplotlib
How to Run the Scripts

Clone the repository:

code
Bash
download
content_copy
expand_less
git clone https://github.com/your-username/monte-carlo-betting-strategies.git
cd monte-carlo-betting-strategies

Run a script from your terminal:
The scripts are best explored in numerical order to understand the project's progression.

code
Bash
download
content_copy
expand_less
python mont1.py
python mont3.py
# and so on...

Note: Some scripts (like mont11.py) are designed to run indefinitely while searching for optimal parameters and will need to be manually stopped (CTRL+C).

Key Findings & Disclaimer

Across all simulations and strategies, a clear pattern emerges: no betting strategy can consistently overcome the house edge. While some aggressive strategies like the Martingale can produce a higher percentage of winning sessions, they also come with a catastrophic risk of ruin (high bust rate) and are ultimately unprofitable in the long run, as demonstrated by the ROI analysis.

These scripts are for educational and analytical purposes only and should not be interpreted as financial or gambling advice. They serve as a powerful illustration of probability, risk, and the mathematical certainties of games of chance.
