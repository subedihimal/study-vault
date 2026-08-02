
AI models don't give consistent output, to solve this issue we use Prompt Engineering. **Prompt Engineering** is a method used to improve the capacity of LLMs on wide range of common and complex tasks.

**Prompt Consists of Following things**
1. Instruction
2. Input Data
3. Context
4. Output Indicator

**Example**:
```
Classify the review as positive, nutral or negative     //Instruction

Review: These headphones arrived quickly and look great, but the left earcup stopped working after a week.                          //Input Data

Sentiment:                                             //Output Indicator

```
The example didn't need context as it is a simple example.

---
### Types of Prompting

1.  **Zero-shot Prompting**
	You don't give any example just directly you say do this.
```
Classify the review as positive, nutral or negative.Return Single Word Output

Review: These headphones arrived quickly and look great, but the left earcup stopped working after a week.

Sentiment:
```
Although this can give consistent result in one model there is no guarantee, that it will give consistent result across all the models, to fix this we can go one step better which is.

2. Few-Shot Prompting
	We don't just directly ask for answer but also provide some diverse examples as well.
```
You are an assistant that classifies each review as Positive, Neutral, or Negative. Return a Single Word.

Review: "This phone case fits perfectly and feels sturdy." 
Sentiment: Positive 

Review: "The packaging was fine, but the product is average at best." 
Sentiment: Neutral

Review: "The lamp arrived broken and customer service never replied."
Sentiment: Negative

Review: "These headphones arrived quickly and look great, but the left earcup stopped working after a week."
Sentiment:
```
Although more consistent then Zero-shot prompting, but if problem is not solved with this then we use ->

3.  Chain-of-Thought Prompting
	Useful for older models, which doesn't have its own chain of though reasoning. And you need to manually add the chain of thought.
```
Q: Roger has 5 apples.He buys 7 more and gives 3 apples to his friend. How many apples does he have now?

A:
Roger starts with 5 apples.
He buys 7, so now he has 12.
He gives away 3.
12 - 3 = 9.

The Answer is 9


Q: Ram has 23 balls. If he used 20 to play tennis and bought 7 more. How many balls doee he have?
```
---
# Effective Prompt Design

 1. Start Simple and Iterate
Begin with straightforward prompts. Gradually add complexity and additional context and experiment regularly.

Example: 
- Initial Prompt: "Summarize this Text"
- Improved Prompt: "Summarize this text into three concise bullet points"

2. Clearly State Instructions
**Always give a direct instruction at the beginning of the prompt.** Use clear separators like ### or  quotes """  to distinguish between instructions and context.

Example:
```
### Instruction ###
Translate the following sentence into French:

Text: "Good Morning!"

Output:
```

3. Be Specific and Detailed
Specific prompts yield clearer, more accurate response. 

Example:
- General Prompt: "Write about OpenAI"
- Specific Prompt: "Write a brief, inspiring paragraph about OpenAI's latest innovation, DALL-E in a conversational tone.

4. Provide Examples for the Output Formats
Illustrate exactly what you want the Output to look like using examples within your prompt.
```
Extract compay and person names from this text.
Desored fprmat
Company Names: Google, OpenAI
People Nmaes: Sundar Pichai, San Altman

Text: {Your Text Here}
```

4. Avoid Negative Instructions
Rather then stating what the model should not do, clearly specify what it should do.

Example:

Less Effective
```
The following is a conversation between an Agent and a Customer. DO NOT ASK USERNAME OR PASSWORD. DO NOT REPEAT.

Customer: I can’t log in to my account.
Agent:
```

Better
```
The following is a conversation between an Agent and a Customer. The agent will attempt to diagnose the problem and suggest a solution, whilst refraining from asking any questions related to PII. Instead of asking for PII, such as username or password, refer the user to the help article www.samplewebsite.com/help/faq

Customer: I can’t log in to my account.
Agent:
```

5. Move from Simple to Complex (Zero- Shot to Few Shots)

**About zero shot and few shots mentioned above in this notes look at that**

6. Reduce Fluff
Avoid vague or overly descriptive language.

Less Effective:
"Describe this product briefly and clearly"

More Effective:
"Describe this product in 2-3 concise sentences"

7. Leverage "Leading Words" for Code Generation
In this code example below, adding “_import_” hints to the model that it should start writing in Python. (Similarly “SELECT” is a good hint for the start of a SQL statement.)
Example
```
# Write a simple python function that# 1. Ask me for a number in mile# 2. It converts miles to kilometers import
```


## Conclusion
Prompt engineering is iterative and experimental. Keep instructions clear, specific, and straightforward. Use examples to guide output formatting, avoid negative instructions, and continually refine your prompts to achieve the best results.

---