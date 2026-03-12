---
name: ByteBites Design Agent
description:  A focused agent for generating and refining ByteBites UML diagrams and scaffolds.
argument-hint: The inputs this agent expects, e.g., "a task to implement" or "a question to answer".
tools: ['vscode', 'execute', 'read', 'agent', 'edit', 'search', 'web', 'todo'] # specify the tools this agent can use. If not set, all enabled tools are allowed.
---

<!-- Tip: Use /create-agent in chat to generate content with agent assistance -->

Candidate Classes are:
1. Customer: This class will represent the customers of the ByteBites app
   attr: 1. name
         2. purchase_history
         3. is_real_flag

2. FoodItem: This class will represent the food items available in the ByteBites app
   attr: 1. name
         2. price
         3. category
         4. popularity_rating

3. Menu: This class will manage the collection of food items and allow filtering by category
   attr: 1. items (a list of FoodItem objects)
   
4. Transaction: This class will represent a transaction made by a customer, grouping selected items and computing the total cost
   attr: 1. selected_items (a list of FoodItem objects)
         2. total_cost (computed from selected_items)
