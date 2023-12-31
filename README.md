# Title: Analyzing Corrosion Rate % in Carbon Steel Pipelines Considering the Gas Flowrate and Water Cut %

# Background and Analysis Motivation:
Corrosion is one of the greatest challenges in the oil and gas industry. There are multiples methods which are used in industry to control corrosion inside carbon steel pipes such as chemical injection (corrosion inhibitor). However, most of these methods are expensive and they consume up to 20% of the operating cost. My role as an operation engineer at one of the oil and gas companies is to develop an economical mechanism to control corrosion rates and operate with more efficiency. 

Therefore, I decided to analyze the historical data of operating parameters (gas flowrate and water cut %) of number of carbon steel pipelines that are used to transport a natural gas and try to capture the most contributing factor to the corrosion in terms of operation parameters. Then, develop a controlling method to minimize/eliminate the corrosion inside gas pipelines. 

In fact, there are several factors which can cause corrosion. These factors are not limited to the operation parameters, but they could involve other factors such as pipelines configuration (geometries). In my analysis, I am neglecting other corrosion factors since there is no enough information about them and they are not measurable.  In addition to that I am assuming that all these pipelines have the same diameter and length. 

The collected data is related to 110 pipelines with their average gas flowrate for two years in MMSCFD, water cut % from the total flowrate and the measured corrosion rate % (The percentage of metal loss) inside the pipes using an instrument in-line scraper which is being utilized to measure the metal loss inside the pipelines. 

# Analysis Summary: 
Initially, I plotted the water cut % versus corrosion rate % and water cut % group versus corrosin rate % to find out if there is a linear relationship: 

  ![image](https://github.com/AhmedJabbari/CHE-2410-Project-1/assets/148829971/319f73f4-38f0-49b8-8996-ce1dc21139dd)


![image](https://github.com/AhmedJabbari/CHE-2410-Project-1/assets/148829971/2f6db0de-4594-4633-9232-38cf6ced3742)




  ![image](https://github.com/AhmedJabbari/CHE-2410-Project-1/assets/148829971/4e6a3756-99d4-4949-9981-627d9df7855a)



By just looking at the graphs I can see that there is a linear relationship between the water cut % and the corrosion rate % and to confirm that I used Python’s OLS linear regression model package, I found that the Corrosion Rate %=0.1429* Water Cut% -0.4131 and the p-value for water cut % is less than 0.05, which indicates that there is a statistical significant positive linear relationship between the water cut % and the corrosion rate %, meaning that as the water % increase, the corrosion rate tends to increase. In fact, this observation is expected because as the amount of water increase there will be more water accumulated inside the pipe, which will react with iron and cause internal corrosion in the pipe.   

Then, I plotted gas flowrate versus the corrosion rate % and gas flowrate group versus corrosion rate %. Then, I applied the Python’s OLS linear regression model package, I found that the Corrosion Rate %=-0.5* Gas-Flowrate +0.4131 and the p-value for gas flowrate is less than 0.05, which indicates that there is a statistical significant negative linear relationship between the gas flowrate and the corrosion rate %, meaning that as the gas flowrate increase, the corrosion rate will increase. This observation is expected as the flowrate increase the fluid velocity will increase and minimize the water accumulation at the bottom of the pipe. 

  ![image](https://github.com/AhmedJabbari/CHE-2410-Project-1/assets/148829971/032984e0-b6f5-42ef-a37d-f7ddd1c446c6)



 ![image](https://github.com/AhmedJabbari/CHE-2410-Project-1/assets/148829971/982f462d-4a40-441d-957b-7de697fd046f)




  ![image](https://github.com/AhmedJabbari/CHE-2410-Project-1/assets/148829971/0e1e9e81-5c99-45c9-9476-6d9065c1a5f7)



 
  ## Linear Model Considering Two Factors:


To figure out which parameter has more effect on corrosion rate %, I used linear models considering two factors. The result shows that Corrosion Rate % = -0.366 * Gas-Flowrate + 0.1298 * Water Cut % + 1.43 and the p-values less than 0.05 indicates that the relationships between these variables and the corrosion rate are statistically significant. So, based on this model, it appears that water percentage has a stronger positive effect on corrosion rate than flowrate has a negative effect. To find a correlation between gas flowrate and water cut % when the corrosion rate % is equal to zero, I put corrosion Rate % equal to zero and then, I solve for water cut % in term of gas flowrate. I found that Water Cut %= 2.81*Gas-Flowrate -11, and mathematically speaking as long as value of the Gas-Flowrate or Water Cut % is calculated by that equation then the corrosion rate % should be zero.  


  ![image](https://github.com/AhmedJabbari/CHE-2410-Project-1/assets/148829971/eb074105-8a1d-4e6d-957a-b39f3fa91e49)



 ## Linear Model Considering Two Factors with Interactions:

At the final stage of my analysis, I utilized linear models considering two factors with interactions to find if there is an interaction between the operating parameters, I got that the Corrosion Rate% = -0.275* Gas-Flowrate+0.15* Water-Cut % -0.81*Gas-Flowrate-Group*Water-Cut-%-Group + 0.95. The p-value of the flowrate-group*water-cut-%-group is less than 0.05 which suggests that there is an interaction between flowrate and water cut % and this interaction is highly significant in predicting corrosion rate %.


  ![image](https://github.com/AhmedJabbari/CHE-2410-Project-1/assets/148829971/86a3a74e-b246-4bd7-a683-ad142404eb2d)


 
# Conclusion:
As a conclusion of my detail analysis, there is a positive linear relationship between corrosion rate percentage and water cut percentage and there is a negative linear relationship between corrosion rate percentage and gas flowrate. However, the water percentage has a stronger positive effect on corrosion rate than flowrate negative effect. Furthermore, there is an interaction between flowrate and water cut percentage in predicting corrosion rate percentage. As for proposing a mechanism to control corrosion rate by controlling the operating parameters the value of the Gas-Flowrate or Water Cut % should be governed by this correlation (Water Cut %= 2.81*Gas-Flowrate -11), then mathematically speaking the corrosion rate % should be zero. However, in real life, it is not an easy mission to have both Gas-Flowrate or Water Cut % values based on that correlation since in natural gas production, the amount of water is coming from the reservoir with gas is unpredicted. Therefore, to implement the proposed solution further analysis should be performed in order to evaluate the feasibility of implementing this proposed method to control the corrosion rate. 
