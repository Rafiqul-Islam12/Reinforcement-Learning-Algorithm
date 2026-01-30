# ***Reinforcement Learning***

- ***Feedback-based machine learning approach.***
- ***An `agent` interacts with an `environment` with an objective to `maximize` its total `reward`.***
 
***The agent takes an action based on the environment state and the environment returns the reward and the next state. The agent learns from trial and error, initially taking random actions and over time identifying the actions that lead to long-term rewards.***   

<img src="https://github.com/Rafiqul-Islam12/Reinforcement-Learning-Algorithm/blob/main/images/img01.png" width="600">  

- ***`Agent`: Learns and makes decisions.***
- ***`Environment`: The external system the agent interacts with.***
- ***`Action`: What the agent does.***
- ***`State`: The current situation of the agent.***
- ***`Reward`: Feedback from the environment.***
  
### ***`Feedback`***:
- ***Correct actions receive positive feedback.***
- ***Incorrect actions receive negative feedback or penalties.***

---
### ***We can break down reinforcement learning into five simple steps:***   
- ***The agent is at state zero in an environment.***
- ***It will take an action based on a specific strategy.***
- ***It will receive a reward or punishment based on that action.***
- ***By learning from previous moves and optimizing the strategy.*** 
- ***The process will repeat until an optimal strategy is found.***

---
# ***Core Components***   
## 🔹***Policy (π)***  
- ***Policy মানে হলো agent-এর `decision-making rule`***  
  ***এই state এ থাকলে কোন action নিবো — এই rule টাই Policy.***

***Math এ, `π(s)=a`***    
***মানে, state s এ গেলে action a নেবে।***   

- ***Policy কেন দরকার?***   
  ***Reinforcement Learning / MDP তে agent সবসময় প্রশ্ন করে: “এখন আমি কী করবো?”***  
  ***এই প্রশ্নের উত্তর দেয় Policy।***  

***Policy হতে পারে:***  
***`Deterministic` → always same action***  
***`Stochastic` → probability দিয়ে action নেয়***  

***Goal:***  
***best policy (π*) খুঁজে বের করা, যাতে total reward maximum হয়।***  

## 🔹***Value Function***  
- ***এটা বলে দেয় কোন state বা action কতটা ভালো।***   

***V(s) → এই state এ থাকলে future এ মোট reward কত পাওয়া যাবে***   
***Q(s, a) → এই state এ এই action নিলে কত ভালো হবে***   
***এই Q-value দিয়েই Q-Learning কাজ করে।***   

## 🔹***Episode*** 
- ***“A complete sequence from initial state to terminal state.”***    
  ***Episode হলো, Start state থেকে শুরু করে terminal state পর্যন্ত complete journey.***

## 🔹***Iteration***  
- ***Algorithm এর একবার update হওয়া***

***Example:***   
***Q-table একবার update → 1 iteration***  
***Value iteration এ একবার Bellman update → 1 iteration***   
***Iteration ≠ Episode***   

## 🔹***Exploration vs Exploitation*** 
***“Exploration tries new actions, exploitation uses known best actions.”***   
- ***Exploration (নতুন জিনিস try করা): Agent নতুন action try করে, যেগুলোর outcome সে ঠিক জানে না।***  
- ***Exploitation (জানা ভালো জিনিস use করা): Agent যেটা আগে থেকে best জানে, সেটাই করে।***

## 🔹***Convergence*** 
***Training চলতে চলতে যখন:***   
***Q-values আর change হয় না, Policy stable হয়ে যায়***   
***তখন বলি algorithm converge করেছে।***   

---
# 📌 ***Policy-based Method vs Value-based Method***   
## ***Value-based Method***    
***Agent আগে শেখে: `“এই state বা action কতটা ভালো?”`***  
***মানে Value Function শেখে, তারপর সেখান থেকে policy বের করে***   
***Indirectly policy শেখে***   

***Algorithms***   
- ***Q-Learning***
- ***SARSA***
- ***Deep Q Network (DQN)***

## ***Policy-based Method***  
***Agent directly policy শেখে।***  
***মানে agent নিজেই শেখে: `“এই state এ কোন action নিলে ভালো”`***    
***No value table required***    

***Algorithms***   
- ***Policy Gradient***  
- ***REINFORCE***   
- ***Actor-Critic (hybrid)***   

---
# ***Markov Decision Process (MDP)***  
- ***It is a `decision making framework`.***    
  ***যেটা Reinforcement Learning-এ use করা হয়। এখানে একটা agent থাকে, সে একটা environment-এর ভিতরে কাজ করে, action নেয়, আর reward পায়।***

***MDP কে আমরা normally এইভাবে define করি: `(S, A, P, R, γ)`***   
- ***`S = States`***  
  ***State মানে agent এখন কোন situation-এ আছে।***  
  ***যেমন, একটা game এ player কোন position-এ আছে, অথবা car কোন জায়গায় আছে—এগুলো state***  

- ***`A = Actions`***  
  ***Agent state দেখে action নেয়।***   
  ***যেমন: left, right, accelerate, brake, up, down ইত্যাদি।***
  
- ***`P = Transition Probability`***  
  ***P(s′ | s, a) মানে, current state s থেকে action a নিলে next state s′ এ যাওয়ার probability কত।***  
  ***সব environment deterministic না, তাই probability লাগে।***  

- ***`R = Reward`***  
  ***Agent action নেয়ার পরে environment তাকে একটা reward দেয়।***  
  ***ভালো কাজ করলে positive reward, খারাপ করলে negative reward।***  
  ***যেমন: goal এ পৌঁছালে +10, দেয়ালে ধাক্কা দিলে −5।***  

- ***`γ (Gamma) = Discount Factor`***  
  ***Future reward কতটা important সেটা control করে।***   
  ***γ ≈ 1 হলে → long-term reward বেশি important***   
  ***γ ≈ 0 হলে → immediate reward বেশি important***   

---
## ***Markov Property***   
***Future শুধু current state + current action এর উপর depend করে, past history এর উপর না।***   
***Math এ লিখলে:*** ***`P(sₜ₊₁ | sₜ, aₜ)`***    
***মানে agent কে আগের সব মনে রাখতে হয় না, শুধু এখন কোথায় আছে সেটাই যথেষ্ট।***   

---
