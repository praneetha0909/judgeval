# Judgment Labs - EchoAgent Evaluation Project

This project demonstrates how to evaluate a simple AI agent using the open-source `judgeval` framework by Judgment Labs. It showcases how to define an agent, run evaluations, and score outputs using a custom-defined scorer.

---

## **Project Structure**

**my_agents/agents/echo_agent.py**  
A minimal agent that echoes the input prompt with a prefix: "You said: <prompt>".

**my_agents/agent_battle.py**  
Main evaluation script that:
- Loads prompt-response examples from JSON
- Calls the agent on each prompt
- Scores outputs using a custom scorer (`AnswerRelevancyScorer`)
- Prints results with pass/fail metrics

**my_agents/examples/prompts.json**  
Contains a list of test cases with expected inputs and outputs.

**src/judgeval/scorers/answer_relevancy_scorer.py**  
Implements the `AnswerRelevancyScorer`, a basic scorer that checks if the generated output is relevant to the expected output.

---

## **How to Run**

1. Set the Python path:

   ```bash
   export PYTHONPATH=src
   ```

2. Run the evaluation script:

   ```bash
   python my_agents/agent_battle.py
   ```

---

## **Example Output**

```
Prompt: What is Python?
Generated: You said: What is Python?
Expected: Python is a high-level programming language.
Score: 0.17 | Passed: False
---
Prompt: Define variable.
Generated: You said: Define variable.
Expected: A variable stores a value in programming.
Score: 0.33 | Passed: False
---
Agent Accuracy: 0/2 passed (0.00%)
```

---

## **Notes**

This evaluation uses a basic agent (`EchoAgent`) and a simple scoring strategy for demonstration. You can extend it by:
- Creating more intelligent agents
- Improving the scoring logic
- Adding more prompts and test cases
