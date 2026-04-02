---
title: "なぜCLAUDE.mdは100行より35行が最強なのか？公式仕様で解説"
date: 2026-04-02T07:52:27+09:00
draft: false
categories: ["tech"]
tags: ["claude.md", "aiプロンプト", "プロンプトエンジニアリング", "claude", "llm", "開発効率", "ai開発"]
slug: "-claude-md-100-35-"
---

Ever feel like you’re writing a constitution for your AI, only to have it ignore half the rules? You spend hours crafting a detailed `CLAUDE.md`, meticulously defining every architectural pattern and directory structure, convinced that more is better. Then you send a prompt, and the AI immediately reverts to generic habits, completely ignoring the specific library versions or formatting styles you spent all afternoon codifying.

If this sounds familiar, you aren't alone. You’ve fallen victim to the "AI Ritual"—the tendency to over-engineer prompts to appease an AI that is already smarter than we give it credit for. Honestly, I’ve been guilty of this more times than I care to admit.

According to a viral report by developer @nogataka from March 1, 2026, the secret to high-performance AI collaboration isn't a massive, exhaustive instruction manual. It’s brevity. The article struck a nerve with the developer community, racking up over 1,200 likes and 3,500 saves in its first week. The core takeaway is radical: trimming your `CLAUDE.md` from 100 lines down to 35 actually improves performance.

Your "bible" for AI is sabotaging your workflow. Here is why.

---

## The "Attention" Problem: Why More is Less

![Simple cartoon illustration: An AI brain symbol with a spotlight effect; the spotlight flickers and dims when overloaded with too much text.](/images/-claude-md-100-35-_0.png)

Most of us have a fundamental misunderstanding about how LLMs handle instructions. We treat `CLAUDE.md` like a permanent database entry, but in reality, it’s just the first thing the AI reads in our conversation.

When you shove 100 lines—roughly 1,500 tokens—into the start of a session, you are flooding the AI’s attention window. Attention is a finite resource. Give the model too much background noise, and it struggles to distinguish between the hard constraints that actually matter and the ambient context it already understands. Honestly, if you write a novel in your system prompt, the AI is going to check out.

There is also a massive **Recency Bias** problem. Research shows that as a chat session stretches beyond 15 or 20 turns, adherence to those massive, front-loaded rule sets drops off a cliff. If your critical instructions are buried in 100 lines of fluff, the AI loses the thread. Keep it brief.

## The 35-Line Sweet Spot: What to Keep (and What to Delete)

![Simple cartoon illustration: A pair of scissors cutting a long document in half, with the shorter piece labeled "High ROI" and the rest "Fluff."](/images/-claude-md-100-35-_1.png)

If you’re trimming your config, what should actually stay? The data shows a clear shift in strategy. Instead of burning your tokens teaching an AI how to code, use that space to define **how it behaves** in your specific ecosystem. Honestly, most base models already know how to write code—they just don't know how *you* want it written.

### The Redundancy (What to Cut)

![Simple cartoon illustration: A trash can labeled "Redundancy" where a developer is throwing away papers labeled "DRY," "SOLID," and "Linting Rules."](/images/-claude-md-100-35-_2.png)

*   **Stop preaching to the choir:** Don’t waste tokens telling Claude to follow "DRY," "SOLID," or "YAGNI." It already knows these principles. Listing them just dilutes the attention the model pays to your actual project-specific needs.
*   **Trust your tools:** If you already have ESLint or Prettier config files, stop repeating those formatting rules in `CLAUDE.md`. Let your tools handle the linting. Honestly, watching someone manually describe code style in a prompt is like watching someone use a calculator to do 2+2. Keep your focus on the logic.
*   **Skip the directory map:** Describing every folder in your project is a massive waste of time. The AI can explore your file system way faster than you can write out a map.

### What to Keep (The High-ROI Rules)

![Simple cartoon illustration: A checklist showing three items: "Version Specs," "3-Step Plan Rule," and "Meta-Rules," all with big green checkmarks.](/images/-claude-md-100-35-_3.png)

*   **Version Specifications:** List your exact tech stack—like `Next.js 15 (App Router)` and `TypeScript 5.7`—right at the start. This is the single highest "Return on Investment" move you can make. It basically pre-loads the right documentation into the AI's brain before you even ask your question.

*   **Behavioral Triggers:** The "3-Step Rule" is a total game-changer. Tell the AI: *"For tasks with 3 or more steps, always start in Plan mode."* This forces it to map out a solution before writing any code, which keeps it from spiraling into hallucinations. (Trust me, save yourself the headache of debugging AI logic.)

*   **Meta-Rules:** Don't bother mapping out your entire directory tree. Instead, define the *logic* behind the structure. Telling the AI "UI components go into `/components` and follow a modular structure" works way better than listing every single sub-folder. 

## Efficiency Comparison: The Old Way vs. The New Way

![Simple cartoon illustration: A bar chart comparing two bars; the "100-Line" bar is low and red, the "35-Line" bar is high and bright green.](/images/-claude-md-100-35-_4.png)

| Feature | The "100-Line" Approach | The "35-Line" Approach |
| :--- | :--- | :--- |
| **Token Usage** | ~1,500 tokens | ~400 tokens |
| **Primary Goal** | Teach AI how to code | Guide AI project workflow |
| **Adherence Rate** | Drops as the chat goes on | Stays sharp the whole time |
| **Redundancy** | High (constantly restates the obvious) | Low (focuses strictly on constraints) |
| **Performance** | Causes "Attention Dilution" | Optimized for high-intent results |

## The OS Analogy: Constitution vs. Drivers

Think of the 100-line approach as a massive, bloated Constitution. You’re giving the AI a lecture on how the world works every time you prompt it. It sounds thorough, but honestly, the model just gets bored and stops paying attention to the details.

The 35-line approach is different. It acts more like a set of lean, efficient device drivers. You aren't teaching the AI how to code; you’re setting the specific parameters for the job at hand. It keeps the model focused on the actual output instead of drowning in your background philosophy. Stick to the constraints—you’ll get way better results.

![Simple cartoon illustration: A computer icon split into two parts: a "Constitution" book for core rules and a "Driver" gear for specific tasks.](/images/-claude-md-100-35-_5.png)



![Simple cartoon illustration: A frustrated developer at a computer screen buried under a massive, long scroll of paper labeled "AI RULES."](/images/-claude-md-100-35-_6.png)

Think of your project setup like a computer.

1.  **`CLAUDE.md` is the Constitution:** Keep only your core principles here. This is for the non-negotiables: your tech stack, coding style, and the "Plan mode" trigger.
2.  **`.claude/rules/` are the Drivers:** Use this for specific tasks like database migrations or CSS styling. These rules are ephemeral—they only load when they’re actually relevant. Honestly, this saves me from having to babysit the AI every time I switch contexts.

Keep your root configuration slim. If you clutter it up, the AI wastes its "attention budget" re-reading a massive laundry list of rules instead of focusing on your actual code.

## Practical Takeaways

*   **Audit your root file:** If a rule doesn’t apply to every single file in the project, move it to a specific directory rule.
*   **Declutter often:** Treat your rules like a junk drawer. If you haven't needed a specific instruction in a week, delete it.

![Simple cartoon illustration: A developer standing on a pedestal holding a trophy labeled "25% Better Success," looking confident and relaxed.](/images/-claude-md-100-35-_7.png)

Stop treating your `CLAUDE.md` like a junk drawer for your coding anxieties. If you want better results, dump the "AI Ritual" and try this three-step refactor today:

1. **Delete the fluff:** Cut any rule a linter can handle or any generic "best practice" sermon. 
2. **Focus on the "Meta":** Keep your directory rules to high-level organizational principles. Nobody needs an exhaustive list of every folder you’ve ever touched.
3. **Prioritize "Version Truth":** Put your tech stack versions at the very top. Seriously, this is the single fastest way to get the AI on the right page for your specific environment.

Developers who switched to this leaner approach saw a 25% jump in first-time success for complex tasks. It turns out that when we stop trying to "program" the AI with 100 lines of text and just give it clear boundaries, it finally has the room to do the job we actually hired it for. 

Stop writing a manifesto. Start writing a high-performance steering command. Sometimes, less really is more.