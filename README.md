# Titled: Analyzing Corrosion Rate % in Carbon Steel Pipelines Considering the Gas Flowrate and Water Cut %. 

# Background and Analysis Motivation:
Corrosion is one of the greatest challenges in the oil and gas industry. There are multiples methods which are used in industry to control corrosion inside carbon steel pipes such as chemical injection (corrosion inhibitor). However, most of these methods are expensive and they consume up to 20% of the operating cost. My role as an operation engineer at one of the oil and gas companies is to develop an economical mechanism to control corrosion rates and operate with more efficiency. 

Therefore, I decided to analyze the historical data of operating parameters (gas flowrate and water cut %) of number of carbon steel pipelines that are used to transport a natural gas and try to capture the most contributing factor to the corrosion in terms of operation parameters. Then, develop a controlling method to minimize/eliminate the corrosion inside gas pipelines. 

In fact, there are several factors which can cause corrosion. These factors are not limited to the operation parameters, but they could involve other factors such as pipelines configuration (geometries). In my analysis, I am neglecting other corrosion factors since there is no enough information about them and they are not measurable.  In addition to that I am assuming that all these pipelines have the same diameter and length. 

The collected data is related to 110 pipelines with their average gas flowrate for two years in MMSCFD, water cut % from the total flowrate and the measured corrosion rate % (The percentage of metal loss) inside the pipes using an instrument in-line scraper which is being utilized to measure the metal loss inside the pipelines. 

# Analysis Summary: 
Initially, I plotted the water cut % versus corrosion rate % to find out if there is a linear relationship between the two: 

  ![image](https://github.com/AhmedJabbari/CHE-2410-Project-1/assets/148829971/319f73f4-38f0-49b8-8996-ce1dc21139dd)


  ![image](https://github.com/AhmedJabbari/CHE-2410-Project-1/assets/148829971/4e6a3756-99d4-4949-9981-627d9df7855a)



By just looking at the graph I can see that there is a linear relationship between the water cut % and the corrosion rate % and to confirm that I used Python’s OLS linear regression model package, I found that the Corrosion Rate %=0.1429* Water Cut% -0.4131 and the p-value for water cut % is less than 0.05, which indicates that there is a statistical significant positive linear relationship between the water cut % and the corrosion rate %, meaning that as the water % increase, the corrosion rate tends to increase. In fact, this observation is expected because as the amount of water increase there will more water accumulated inside the pipe, which will react with iron and cause internal corrosion in the pipe.   

Then, I plotted gas flowrate versus the corrosion rate % and I applied the Python’s OLS linear regression model package, I found that the Corrosion Rate %=-0.5* Gas-Flowrate +0.4131 and the p-value for gas flowrate is less than 0.05, which indicates that there is a statistical significant negative linear relationship between the gas flowrate and the corrosion rate %, meaning that as the gas flowrate increase, the corrosion rate will increase. This observation is expected as the flowrate increase the fluid velocity will increase and minimize the water accumulation at the bottom of the pipe. 

  ![image](https://github.com/AhmedJabbari/CHE-2410-Project-1/assets/148829971/032984e0-b6f5-42ef-a37d-f7ddd1c446c6)



  ![image](https://github.com/AhmedJabbari/CHE-2410-Project-1/assets/148829971/0e1e9e81-5c99-45c9-9476-6d9065c1a5f7)



 
  ## Linear Models Considering Two Factors:


To figure out which parameter has more effect on corrosion rate %, I used linear models considering two factors. The result shows that Corrosion Rate % = -0.366 * Gas-Flowrate + 0.1298 * Water Cut % + 1.43 and the p-values less than 0.05 indicates that the relationships between these variables and the corrosion rate are statistically significant. So, based on this model, it appears that water percentage has a stronger positive effect on corrosion rate than flowrate has a negative effect.

  ![image](https://github.com/AhmedJabbari/CHE-2410-Project-1/assets/148829971/eb074105-8a1d-4e6d-957a-b39f3fa91e49)



 ## Linear Models Considering Two Factors with Interactions:
At the final stage of my analysis, I utilized linear models considering two factors with interactions to find if there is an interaction between the operating parameters, I got that the Corrosion Rate% = -0.0234* Gas-Flowrate+0.244* Water Cut %-0.0263*Gas-Flowrate*Water Cut % - 0.151. The p-value is less than 0.05 of gas-flowrate*water% which suggests that there is an interaction between gas-flowrate and water cut % and this interaction is highly significant in predicting corrosion rate %.


  ![image](https://github.com/AhmedJabbari/CHE-2410-Project-1/assets/148829971/71eff791-482c-4b35-a065-4b11b34bbdb4)



 
# Conclusion:
As a conclusion of my detail analysis, there is a positive linear relationship between corrosion rate percentage and water cut percentage and there is a negative linear relationship between corrosion rate percentage and gas flowrate. However, the water percentage has a stronger positive effect on corrosion rate than flowrate negative effect. Furthermore, there is an interaction between flowrate and water cut percentage in predicting corrosion rate percentage. 
