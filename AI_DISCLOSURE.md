# AI Usage Disclosure

**Please include this with your submission.**

## What is Appropriate AI Use? ✅

We encourage you to use AI tools for:
- **Explanations**: "What is one-hot encoding?" or "Explain data leakage"
- **Debugging**: "Why doesn't this code work?" + error message
- **Syntax help**: "How do I use pd.get_dummies()?"
- **Learning resources**: "Recommend a tutorial on standardization"
- **General concepts**: "What's the difference between mean and median?"

## What is NOT Appropriate? ❌

Do NOT:
- Ask AI to write your entire function for you
- Copy code from AI without understanding it
- Submit code without testing/modifying it
- Hide the fact that you used AI
- Use AI to do the assignment for you

## Your Disclosure

**Did you use any AI tools to help with this assignment?**

_____ Yes     _____ No

**If yes, please tell us:**

1. **What tools did you use?** (e.g., ChatGPT, Claude, GitHub Copilot)
   
   ChatGPT

2. **What specific things did you ask them to do?** (Be specific)
   
   - For the data_processing.py file, I used 
      df = df.apply(pd.to_numeric, errors='coerce')
      df = df.fillna(df.mean())
      df = pd.get_dummies(df, columns=['sex', 'cp', 'fbs', 'restecg', 'thal', 'exang'], drop_first=True)

      return df

I was getting errors when trying to run the example_workflow.ipynb and couldn't figure out what I was doing wrong. I made sure my variables were all matching, which they were. 

I asked people in the class and they said to look at the pd.to_numeric part. I initially changed errors='coerce' to errors='ignore'. This worked for the heatmap, however the following section wasn't working.

Someone else suggested to encode all of the nonnumeric codes instead. I was having issues this this too, so I asked ChatGPT where I was going wrong and it put back in coerce, which I'm assuming because we still want to convert missing values to NaN, and tell the system not to use things that aren't numeric? 

It also added the below section, which helped with the next part of the notebook. 
      for col in existing_cats:
         df[col] = df[col].fillna(df[col].mode()[0])

I'm not entirely clear why it was added, I'm guessing it's to loop through the columns and show the most frequent vaue in that column, so if we're looking at sex, for example, if 0 is the most common number, it would just return 0, not 1 or NaN.

I also asked it to debug the kNN classification code. It suggested to re-add in the from sklearn.metrics import roc_auc_score line again, even though we used it before. It also flagged the broken dictionary, so I had to adjust that. 
   _________________________________________________________________

3. **How much of your final code came from AI vs. your own work?** (e.g., "AI gave me the formula, I wrote the loop" or "AI helped me debug an error")
   
AI helped me debug an error. Notes above, but please let me know if you want me to explain further. 

4. **Can you explain your code?** (Can you walk through what each function does and why you wrote it that way?)
   
   _____ Yes, I can explain it well
   
   X Mostly, but I have some questions
   * See above notes. I think I understanding but not entirely clear on those couple of changes it gave me. 
   
   _____ No, I'm not sure I understand it

**Additional comments:**

_________________________________________________________________

_________________________________________________________________

---

## Why This Matters

- **Honesty helps you**: Complete and honest disclosure is viewed positively
- **We care about learning**: If you used AI appropriately, that's fine
- **Understanding is key**: We need to know you actually learned the concepts
- **Dishonesty is serious**: Hiding AI usage or submitting others' work is academic misconduct

---

## Questions?

If you're unsure whether your AI usage was appropriate, **ask your instructor before submitting**. We'd rather help you understand the guidelines than penalize you later.
