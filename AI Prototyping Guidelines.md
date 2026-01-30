AI Prototyping Guidelines
===========================
Let’s hope I convinced you to prototype before you buy. Of course, as a consultant, I believe the best way to go about prototyping is getting me involved. Such belief is a prerequisite for an honest person going into consulting. However it is in your right to be sceptical, or geographically remote and limited by procurement to your jurisdiction. I still want you to succeed. 

So I am providing the guidelines for running your own prototype, or engaging a local consultant. 

# What is a Prototype?

Let’s clear some confusions between the terms which are often used interchangeably, incorrectly:

* MVP (Minimal Viable Product): in the startup and business-to-consumer game, an MVP is created to test customer acceptance. In enterprise IT, MVP means the minimal solution that can be deployed, and usually makes sense for sites that embrace DebOps, continuous deployment, or that take Agile seriously.  
* Pilot is a limited scope deployment of a service, application or feature, to staff or customers. It also presumes the existence of a viable system or service.   
* Prototype: short, cheap, disposable proof to reduce uncertainty across feasibility and workflow fit, failure modes, data reality, integration constraints, and cost/latency.  
* PoC (Proof of Concept): a kind of prototype that is focusing on a specific individual claim, usually to do with technology/model.

We will be using the term "prototype" rather than “PoC” because it can (and should unless classified) cover real data, as well as workflow fit.

# Making your Claims

As you see from above a prototype (or PoC) is built around specific claims. It is important to write such claims down, then review them against the following checklist:

- [ ] Does it contain any claim related to scalability?  
- [ ] Does it contain any claim related to integration with other systems?  
- [ ] Does it contain any claim to do with the development process?  
- [ ] Does it have any claim related to user interface  
- [ ] Does it have any claim related to the capabilities of an internal or external team?  
- [ ] Are the claims in the list disjoint enough to split it into two groups which are not mutually dependent? One-way dependency is fine  
- [ ] Can you think of any claim that is more critical to the success, or as critical yet more questionable?

If you ticked at least one box, review your list. 

# Setting up time and budget constraints

The key problem for failing prototypes is turning them into projects. More time and more money create opportunities to hide behind non-essential activities. On the other hand, tight time and budget constraints will likely scare away any vendor hoping to learn on the job, upsell the project, then find excuses. Once again, a checkbox:

- [ ] Did you allocate more than 8 weeks?  
- [ ] Did you allocate more than 40 person/days?  
- [ ] Does the quote exceed the threshold that makes it harder to procure?

If you tick any of the boxes it is not a prototype. 

# Data checklist

You cannot do anything with AI without data. To start, answer the following:

- [ ] Can you provide sufficient information on the data you have, either by providing a comprehensive dictionary, or a lesser dictionary and a domain expert?  
- [ ] Can you provide a part-time staff to assist in locating and acquiring data?

If not all boxes are checked, you cannot do a prototype. Without data, you can go for a technology demonstrator on unrelated data \- those, however, rarely provide necessary certainty. General demonstrations of technology are available on YouTube for free \- the real problem at hand is what can be done for your enterprise to solve your problems. 

If you are still in the game, fill the following:

- [ ] Can you provide real data to the consultant?  
- [ ] Can you allow uploading real data to a cloud service?

If all boxes are ticked, you are ready to go, progress to the next section. If not all boxes are ticked, proceed to figuring out whether anonymisation of data can solve the problem. Anonymised data can potentially leave important information out and complicate 

- [ ] Do you have an accepted anonymisation capability?   
- [ ] Would you be able to provide anonymised data to the consultant?  
- [ ] Would you be able to upload anonymised data to a cloud service?

If all boxes are ticked, you can proceed to the next section.

If not all boxes ticked, you need to consider using a local model. While publicly available models, especially open source, are not in the same league as proprietary offers, they are good enough for a good prototype. 

- [ ] Do you have, or can you procure, an AI workstation that can run a model your consultant is happy with?  
- [ ] Can you allow the consultant to work with your data, real or anonymised, on that workstation?

We exhausted all options. If you haven’t ticked both boxes above, you cannot run a prototype.

If however you conclude that you have data, and the project does not involve Agentic AI, you are good to go. 

# Agentic Checklist

Agentic AI uses LLM and interfaces to control existing applications. Because LLM outcome is probabilistic, one cannot guarantee an intelligent atgent not to do something seriously wrong and damaging. That As a result, all responsibilities for safety and If you are prototyping an Agentic AI implementation, you need another step. Agentic AI prototypes are complex enough to warrant a separate checklist. 
However before going into such a checklist, it is important to verify the sanity of even contemplating an Agentic AI project. Therefore, please answer the following questions:

- [ ] Are the processes the Agentic AI implementation will be contributing to known?  
- [ ] Have the processes been reviewed for relevance?

As the processes are split into steps to be performed by humans, you may find that it is harder for Agentic AI to implement an individual step than a larger part of the project. Doing more work to deliver an unconvincing result is the very opposite of a well-defined prototype.

If you reviewed the processes, and believe you have viable scope, please complete separate Agentic AI Prototype Checklist available at https://github.com/businessabstraction/resources/

# The 7 deliverables you require in any GenAI pilot
No matter what kind of prototype you are running, if it involves Generative AI, you need to ensure that the deliverables include the following 7 items:
- [ ] An evaluation harness (test set \+ scoring \+ pass/fail gates)  
- [ ] A failure taxonomy (how it breaks in your domain)  
- [ ] Traceability/provenance approach (what sources were used, when, and how)  
- [ ] Logging and “what becomes a record” decision (especially gov/regulated)  
- [ ] A red-team plan (prompt injection, data leakage, policy failure cases)  
- [ ] Cost/latency guardrails (what happens when prompts blow out context/cost)  
- [ ] A handover kit (so you’re not locked into the vendor)

The file "GenAI Prototype Deliverables.md" in https://github.com/businessabstraction/resources/ provides detailed descriptions of each deliverable. 

# **Use AI help, but no Vibe Coding**

“Vibe Coding” is the name given to the practice of developing apps where actual coding is trusted to a coding agent like Codex, or to an IDE integrating AI like Cursor. The process of Vibe Coding resembles an original eXtreme Programming, with a few corrections:

* AI acts as the development team, delivering code candidates  
* The solo developer acts as an Onsite Customer as well as a Tester.   
* Iterations are two-three hours rather than two-three weeks. 

The solo Developer provides the coding agent with requirements in the form of prompts, and reviews the results. However, the Developer doesn’t understand the code nor every tool and platform used, focusing on visible behaviour of the system.

I have no religious objections to vibe coding. If it works, if you deliver and the client is happy \- enjoy your massive productivity boost. However, vibe coding doesn’t give you certainty that it is validating whatever you were trying to validate. If you vibe code a prototype \- you do not know whether it validated your assumptions, or learned to mimic them. 

In a prototype, you need to be in control of the code, and understand it. You can use AI coding assistants to speed up your work, but you need to knjow exactly what is happening. Y ou need to own the code. 