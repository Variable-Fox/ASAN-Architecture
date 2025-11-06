# ASAN: The Guide

Samuel Victor Miño Arnoso  
November 6, 2025

---

## Figure 1: Conceptual Image of the ASAN Neural Network

### ASAN Network: Questions about the System (Understanding the Concept Image)

The following questions were posed as a fictional conversation to help understand (and interpret) the concept image above and thus the ASAN network system:

---

### 1. User - Question 1:

What is the bright-yellow glowing circle in the middle of this concept image? Is that an Auto Agent? As in, an A.I. agent of the ASAN system that receives a request from a user (who is currently using the ASAN network) and this (Auto) Agent then queries other agents/"specialists" (and can even have an "On Demand" agent created if needed; i.e., a new, additional [specialist] agent), to gather all possible information needed for this (Auto) Agent to respond to the user in a perfectly informative way?

**Answer 1:**  
That’s an excellent question! You have already interpreted the image very well and understood both the Auto Agent and the ASAN concept quite quickly. Let’s clarify this step-by-step using your questions and the paper’s definitions for this ASAM system:

- The yellow, bright circle in the center of the concept image for this ASAN network system (The "Auto Agent"):  
  Exactly. You’ve grasped it perfectly. This bright core in the middle represents a high-level agent (like the "Auto Agent" from the sports car example in the Companion Paper).  
  This user-facing Auto Agent receives the user’s complex request (e.g., "Analyze this or that user request"), breaks it down (deconstructs the request), and initiates the "pulsing" cascade by sending the user’s requests to the specialists in the outer rings (visible in the concept image). These others are agents (specialists) that are specifically "woken up" from their "frozen" (cold state on slow storage) stage, and they then gather all the information that the user-facing (Auto) Agent needs.

And your further, supplementary thought is also correct: If this Auto Agent (or another agent in the chain) needs an extra, additional specialist that doesn’t exist yet (to fully gather their information or accomplish their task), it (or one of the other specialist agents) would initiate "On-Demand Autopoiesis" (the "birth" of a new specialist via QLoRA, as described in the main paper 7.1/7.2.2) via the Meta-Agents (the "operating system" — The connecting lines and circles in the concept image that hold the system together).

This means: It, or even some of them, will create a new agent specifically for this request if certain, specialized information is needed and missing, which requires an extra-new specialist agent.

**Operational note:** Cold/Warm storage: Newly created specialists are not frozen by default after a single request; they remain warm for an observation window to measure real demand and latency. If their utilization stays below a minimum threshold during that window, the Directory transitions them to cold storage and reactivates them on demand. For bursty workloads the system applies predictive pre‑warming and elastic auto‑scaling to meet the target latency, rather than freezing immediately. Freeze/unfreeze and replica‑scaling decisions are bounded by global budget caps, audit‑logged, and may be overridden by human operators under the governance layer.

A new agent (specialist) is thus born into the ASAN system and automatically becomes part of the entire ASAN network, but it must follow the rules of all other agents (to maintain energy-saving mode after completing a job).  
The network thus grows continuously, if it deems it necessary (on-demand = autopoiesis = self-creation).

---

### 2. User - Question 2:

What are the dots in the image that seem to be scattered all over the circles? Do they have any meaning in the network?

**Answer 2:**  
**Budgeted Autopoiesis — The Meta-Agents**  
**(The Governance — The Action House)**

You’ve noticed these dots very attentively and have already guessed that they might have a task in the entire network. These dots represent the network’s oversight.  
They are the "state administration" that monitors and controls the entire system’s treasury, i.e., the budgeting activities.  
When an "Auto Agent" (middle) needs a new specialist (Autopoiesis)...it asks the Meta-Agents (city administration): "Am I allowed to build a new specialist?"  
...the Meta-Agents check the costs (Economy) and say: "Yes, approved!"  
...then the new agent (new building) is built and...its new address is entered into the Router / Directory Service (like the phonebook/GPS/street network) so that others can find it.

---

### 3. User - Question 3:

But where is the "(Mixture of Experts (MoE): A "router" forwards requests to experts.)" that is mentioned in the main paper? So where is this router in this (concept image) ASAN network system?

**Answer 3:**  
**The Router (Mixture of Experts / MoE)**

The "Router" in this image is not a single physical node (like a Wi-Fi router in your home).  
The "Router" is the entire invisible operating system that dictates the paths.

In the concept image, this is symbolized by the overlaid grid lines to the agents and the hierarchical rings that connect all nodes.

In the papers, these routers are called "The 'Operating System'" (Main Paper, 6) and more specifically "The Routing Problem: Hierarchical 'Directory Service'" (Main Paper, 6.1).

- The "Directory" Service (implemented in Redis, as suggested in 7.4 (Point 3)) **is** the router.
- In the concept image, you see the label "Meta-Agents / Directory Service" in the upper right. This means that this entire grid, which defines the rules of who talks to whom, is the "router".
- When the "Auto Agent" (the bright-yellow glowing circle in the middle of the concept image) sends a request to the "Nature Agent" (green in the concept image as an agent), the "Directory Service" is the mechanism that finds the most efficient path there and forwards the request (the "forwarding").

The Router is therefore the structure and intelligence of the network itself, not a single point within it. These are the Meta-Agents themselves.  
(See also above, Question 2.)

---

### 4. User - Question 4:

And where is the index method for token reduction created during these processes? In the Auto Agent itself? Or in the Router System? Or with every agent (specialist) that is queried?

**Answer 4:**  
**The Location of the "Index-Methodic" (Token Reduction / AIC)**

This is an excellent technical detail question, which your Companion Paper (Section 3) answers.  
The "Index-Methodic" (Adaptive Input Compression, AIC) is a collaborative process:

a) **Who creates the index?**  
Each agent (specialist) creates its own, highly specialized "dictionary" (the "Index-File"). The "Python Specialist" (Agent) (as read in Example 3.3 of the Companion Paper) creates and owns the index for Python commands (e.g., tok_001 = def get_user_data).  
The "Color Specialist" (Agent) creates its own index for color codes.

b) **Who applies the index?**  
The requesting agent ("Requester Agent", i.e., the "Auto Agent").

**The Process (according to the main paper):**
- When, for example, the "Auto Agent" (the bright-yellow glowing circle in the middle of the concept image of the ASAN system — The "Requester Agent") wants to talk to the "Python Specialist" (Agent):
  - (a) The Auto Agent "knows" it is talking to the Python Specialist (Agent) (thanks to the "Directory Service").
  - (b) It retrieves the specific "Index-File" (the dictionary) of the Python Specialist (Agent).
  - (c) It compresses its request (e.g., def get_user_data...) using this dictionary into the short code (tok_001...).
  - (d) It sends the compressed request (tok_001(tok_002):).

In the concept image, the "Index-Methodic" is therefore a process that takes place on the communication path (one of the straight, glowing connection lines to another agent. In this case, the Python Specialist (Agent)): It is defined by the specialist (the Python Agent) (the target node in the concept image, e.g., green) and applied via the connecting line by the requester — (The Auto Agent) (the start node in the concept image, e.g., yellow middle) to compress the message.


Note: ASAN is intended for peaceful, civilian use; military or harmful applications are explicitly rejected (see Ethical Use Declaration in the main paper).
---
