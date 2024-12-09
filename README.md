**Developed a financial analysis agent for managing expenses for students with a given income, expenses and country of residence.** 

•	This agent uses inbuilt blocks of AutoGPT thus making it easier for non-developers to develop applications.

•	Output of agent also contains financial advises regarding investments which the user/student should make to reach the target savings.
 
**Observations:**

a.	While dataflow looks like that of ComfyUI, Autogpt wins in terms of combining multiple open-source models into one application – addition of customized modules is easy. Whereas ComfyUI wins when it comes to understanding the actual data flow because of easy visibility of configuration tags.

b.	ComfyUI also provides a more granular control over the dataflow which would help programmers control & even modify/add functionality on the go while developing the application whereas AutoGPT doesn’t include such facility.

**Details of blocks used:**

i.	Agent input blocks used to provide user inputs – income, expenses, country and user goal to the model.

ii.	Add to dictionary block used to add a new key-value pair to the dictionary – which in this case 
Looks like:
{"country": "United States",
 "income": "100000", 
 "expenses": "50000", 
 "goal": "I want to maximise the passive income I can gain from my investment capital"}

iii.	Fill Text Template block used to format given text using format template, used here:
Financial Analyst Briefing:
Student's Country: {{ country }}
Student's Financial Goal: {{ goal }}
Current Capital Available for Investment: {{ capital }}
Income and Expenses Summary:
- Income: {{ income }}
- Expenses: {{ expenses }}

Advisor Notes:
The student aims to achieve the above financial goal with their current capital. Please evaluate their income and expense structure to recommend an optimal strategy for reaching their goal. Focus on ways to maximize the student's investment potential while considering their current financial standing. 
Ensure that their expenses are manageable and provide actionable steps to help them achieve better savings or investment returns to align with their goal.
Give clear advise on specifically what their investment capital could be invested in to help them achieve their goals. Consider stocks, savings accounts, gold, crypto, pension funds and every other possible investment.

iv.	AI text generator block – used to call LLM model using the prompt generated here through ‘Fill text template block’ to generate required output string. LLM used here is: GPT -4o

v.	Agent Output blocks – to display output of the agents

**Dependencies:**

You need to download and setup AutoGPT following steps listed on : https://agpt.co/blog/introducing-the-autogpt-platform and then import the project file to run on AutoGPT platform.

Along with this user may also be required to add relevant API keys of the models being used.
