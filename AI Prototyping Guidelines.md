AI Prototyping Guidelines
===========================
Let’s hope I convinced you to prototype before you buy. Of course, as a consultant, I believe the best way to go about prototyping is getting me involved. That belief is almost a prerequisite for an honest person going into consulting. However, you are within your rights to be sceptical—and you may also be geographically remote or constrained by procurement rules in your jurisdiction. I still want you to succeed. 

So to help you to succeed, I'm providing the guidelines for running your own prototype, or engaging a local consultant. It is provided under Creative Commons Attribution 4.0 International, so feel free to change it to suit your needs, and remove the text above. Just provide an attribution to Business Abstraction Pty Ltd somewhere in the document.

# What is a Prototype?

Let’s clear up some confusion between the terms which are often used interchangeably, incorrectly:

* MVP (Minimal Viable Product): in the startup and business-to-consumer game, an MVP is created to test customer acceptance. In enterprise IT, MVP means the minimal solution that can be deployed and usually makes sense for sites that embrace DevOps, continuous deployment, or that take Agile seriously.  
* Pilot: a limited-scope deployment of a service, application, or feature to staff or customers. It also presumes the existence of a viable system or service.   
* Prototype: short, cheap, disposable proof to reduce uncertainty across feasibility and workflow fit, failure modes, data reality, integration constraints, and cost/latency.  
* PoC (Proof of Concept): a kind of prototype that focuses on a specific claim, usually to do with technology/model.

We will be using the term "prototype" rather than “PoC” because it can (and, unless classified, should) cover real data, as well as workflow fit.

# Making your Claims

As you see above, a prototype (or PoC) is built around specific claims. It is important to write such claims down, then review them against the following checklist:

- [ ] Does it contain any claim related to scalability?  
- [ ] Does it contain any claim related to integration with other systems?  
- [ ] Does it contain any claim to do with the development process?  
- [ ] Does it have any claim related to the user interface?  
- [ ] Does it have any claim related to the capabilities of an internal or external team?  
- [ ] Are the claims in the list disjoint enough to split it into two groups which are not mutually dependent?   
- [ ] Can you think of any claim that is more critical to the success, or as critical yet more questionable?

If you ticked any of the boxes, review your list: this is where prototypes quietly become projects.

# Setting up time and budget constraints

The key problem for failing prototypes is turning them into projects. More time and more money create opportunities to hide behind non-essential activities. On the other hand, tight time and budget constraints will likely scare away any vendor hoping to learn on the job, upsell the project, then find excuses. Once again, a checklist:

- [ ] Did you allocate more than 10 (preferably 6) weeks?  
- [ ] Did you allocate more than 50 (preferably 30) person-days?  
- [ ] Does the quote exceed the threshold that makes it harder to procure?

If you tick any of the boxes, it is not a prototype. 

# Business Processes Review
Most established processes consist of steps performed by humans. One of the common anti-patterns is to slavishly follow such processes, trying to assist individual steps. There are situations where re-engineering several steps of a process is easier than taking care of an individual step. So please answer the following:
- [ ] Have you reviewed the relevant Business Processes?
or
- [ ] Have you allocated time to review the relevant Business Processes as a part of the prototype?

If you haven’t ticked any of the boxes, you need to review such decision. There are situation when the task is so obvious and clearly defined, that you don't need to review processes. However, such situations are rare. Allocating five consulting days to review the relevant processes can materially change scope, risks, and success criteria.

# Data checklist

You can’t de-risk an enterprise AI use case without representative data. To start, answer the following:

- [ ] Can you provide sufficient information about data you have, either by providing a comprehensive dictionary, or a data dictionary and a domain expert?  
- [ ] Can you allocate staff time to assist in locating and acquiring data?

If not all boxes are checked, you cannot do a prototype. Without data, you can go for a technology demonstrator on unrelated data—those rarely provide enough certainty. General demonstrations of technology are available on YouTube for free - the real problem at hand is what can be done for your enterprise to solve your problems. 

If you are still in the game, complete the following:

- [ ] Can you provide real data to the consultant?  
- [ ] Can you allow uploading real data to a cloud service?

If all boxes are ticked, you are ready to go, progress to the next section. If not all boxes are ticked, proceed to figuring out whether anonymisation of data can solve the problem. Anonymised data can potentially leave important information out and complicate evaluation of results, but it is better than no data at all.

- [ ] Do you have an accepted anonymisation capability?   
- [ ] Would you be able to provide anonymised data to the consultant?  
- [ ] Would you be able to upload anonymised data to a cloud service?

If all boxes are ticked, you can proceed to the next section.

If not all boxes ticked, you need to consider using a local model. While publicly available models, especially open-source, may not match top proprietary models on your task, but can be good enough for a prototype.

- [ ] Do you have, or can you procure, an AI workstation that can run a model your consultant is happy with?  
- [ ] Can you allow the consultant to work with your data, real or anonymised, on that workstation?

We've exhausted all options. If you haven’t ticked both boxes above, you cannot run a prototype.

If, however, you conclude that you have data, and the project does not involve Agentic AI, you are good to go. 

# Agentic Checklist

Agentic AI uses LLMs and interfaces to control existing applications. Because LLM outputs are probabilistic, one cannot guarantee that an intelligent agent would not do something seriously wrong and damaging. Therefore, anything to do with Agentic AI requires an additional checklist, created to reduce risk of damaging or catastrophic outcome.

If you consider an Agentic AI pilot, please complete the separate Agentic AI Prototype Checklist available at https://github.com/businessabstraction/resources/

# The 7 deliverables you require in any GenAI pilot
No matter what kind of prototype you are running, if it involves generative AI, you need to ensure that the deliverables include the following 7 items:
- [ ] An evaluation harness (test set + scoring + pass/fail gates)  
- [ ] A failure taxonomy (how it breaks in your domain)  
- [ ] Traceability/provenance approach (what sources were used, when, and how)  
- [ ] Logging and “what becomes a record” decision (especially gov/regulated)  
- [ ] A red-team plan (prompt injection, data leakage, policy failure cases)  
- [ ] Cost/latency guardrails (what happens when prompts blow out context/cost)  
- [ ] A handover kit (so you’re not locked into the vendor)

See "GenAI Prototype Deliverables.md" in https://github.com/businessabstraction/resources/ for a detailed description of each deliverable. 

# **Use AI help, but no Vibe Coding**

“Vibe Coding” is the name given to the practice of developing apps where actual coding is trusted to a coding agent like Codex, or to an IDE integrating AI like Cursor. The process of Vibe Coding resembles the original "eXtreme Programming", with a few modifications:

* AI acts as the development team, delivering code candidates  
* The solo developer acts as an On-site Customer as well as a Tester.   
* Iterations are two to three hours rather than two to three weeks. 

The solo developer provides the coding agent with requirements in the form of prompts, and reviews the results. However, the developer doesn’t understand the code or every tool and platform used, focusing on visible behaviour of the system.

I have no religious objections to Vibe Coding. If it works, if you deliver and the client is happy - enjoy your massive productivity boost. However, Vibe Coding doesn’t give you certainty that it is validating whatever you were trying to validate. If you Vibe Code a prototype - you do not know whether it validated your assumptions, or learned to mimic them. 

In a prototype, you need to be in control of the code and understand it. You can use AI coding assistants to speed up your work, but you need to know exactly what is happening. You need to own the code. 