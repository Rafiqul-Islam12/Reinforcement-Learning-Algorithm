# ***Proximal Policy Optimization***
- ***Model-free***  
- ***On-policy***  
- ***Policy gradient based Reinforcement Learning algorithm***  

***এটি agent-এর policy update করে, কিন্তু update করার সময় নিশ্চিত করে যে:***  
***নতুন policy আগের policy থেকে খুব বেশি দূরে না যায়।***  

- ***PPO-এর মূল ধারণা হলো:***  
  ***Policy update করো, কিন্তু একটি নির্দিষ্ট সীমার মধ্যে***  
  ***এই সীমা নিশ্চিত করা হয় clipping technique দিয়ে।***

***`Probability Ratio`: PPO পুরাতন এবং নতুন policy-এর probability তুলনা করে।***

---
## ***Working Process of Proximal Policy Optimization (PPO)***  
<img src="https://github.com/Rafiqul-Islam12/Reinforcement-Learning-Algorithm/blob/main/images/img02.jpg" width="600">  
<img src="https://github.com/Rafiqul-Islam12/Reinforcement-Learning-Algorithm/blob/main/images/img03.jpg" width="600"> 
