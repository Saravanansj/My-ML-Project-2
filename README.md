**🩺 Provide Better Diabetes Treatment using Reinforcement Learning
📌 Introduction**

This project demonstrates the application of Reinforcement Learning (RL) algorithms — Q-Learning and SARSA — to optimize diabetes treatment decisions. By modeling patient health states and treatment actions as a Markov Decision Process (MDP), the system learns an optimal treatment strategy to improve patient outcomes.

The model trains an agent to decide whether to recommend Insulin, Oral Medication, Diet Adjustment, or Exercise, depending on whether the patient’s diabetes is Controlled or Uncontrolled.

**Abstract**

The project implements Q-Learning (off-policy) and SARSA (on-policy) algorithms to train an agent that recommends diabetes treatments.

State Space: Controlled, Uncontrolled

Action Space: Insulin, Oral Medication, Diet Adjustment, Exercise

Q-Table: Stores expected cumulative rewards for each state-action pair.

Reward Structure: Reflects the effectiveness of treatments (positive for effective, negative/low for ineffective).

The system allows the user to select an algorithm, train the model, view the learned Q-table, and receive treatment recommendations.

**Reinforcement Learning Concepts**

Agent → Learns and makes treatment decisions

Environment → Patient health condition

State (s) → Controlled / Uncontrolled

Action (a) → Treatment options

Reward (R) → Effectiveness of treatment

Policy (π) → Strategy mapping states → actions

Q-Value → Action-value function estimating rewards for each state-action pair

Exploration vs Exploitation → Epsilon-greedy strategy to balance new discoveries and known best actions

Discount Factor (γ) → Importance of future rewards

**Algorithms Implemented**
**Q-Learning (Off-Policy)**

Updates Q-values using the maximum future reward, regardless of actions actually taken.

Faster convergence, but can be unstable.

Update rule:

Q(s,a) ← Q(s,a) + α [ R + γ max_a' Q(s’,a’) – Q(s,a) ]

**SARSA (On-Policy)**

Updates Q-values based on the action actually taken under the current policy.

Slower but more stable.

Update rule:

Q(s,a) ← Q(s,a) + α [ R + γ Q(s’,a’) – Q(s,a) ]

**Algorithm Implementation**

Q-Table Initialization → 2D array with zeros

Hyperparameters → learning rate, discount factor, epsilon (exploration rate), episodes

Reward Function → Positive for effective treatments (e.g., Insulin in Controlled state = +10), negative/low for ineffective ones

Transition Function → Defines how patient states change based on actions (e.g., Insulin and Exercise more likely to maintain Controlled state)

Action Selection → Epsilon-greedy policy

**Prediction Comparison**
Aspect	Q-Learning	SARSA
Convergence	Faster, off-policy	Slower, on-policy
Policy Outcome	Aggressive, favors max reward	Conservative, reflects actual actions
Exploration	Strong, prioritizes best possible reward	Cautious, depends on current policy
Stability	Less stable, may oscillate	More stable, smoother adjustments
Example Output	Suggested Exercise for Controlled	Suggested Insulin for Controlled


**Sample Outputs**

Q-Learning Example:

Learned Q-table:
[[58.97 44.23 52.85 70.  ]
 [39.64 55.6  57.6  64.  ]]

Suggested treatment for 'Controlled': Exercise


SARSA Example:

Learned Q-table:
[[83.11 62.10 61.01 75.33]
 [39.59 47.42 50.04 75.00]]

Suggested treatment for 'Controlled': Insulin

**Conclusion**

Q-Learning → Aggressive, fast optimization, favors maximizing long-term rewards. In this setup, often suggested Exercise for controlled patients.

SARSA → More conservative, experience-driven, ensures stability. Frequently suggested Insulin for controlled patients.

👉 Q-Learning is ideal for quick optimization.
👉 SARSA ensures stable, experience-based decisions.

**License**

This project is licensed under the MIT License.

**Acknowledgments**

Project developed as part of academic work at Government College of Engineering, Bodinayakanur(In TVS training and Services).

Inspired by Sutton & Barto’s Reinforcement Learning textbook.

Built for educational purposes only — not a substitute for professional medical advice.
