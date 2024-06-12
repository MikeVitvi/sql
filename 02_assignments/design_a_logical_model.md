# Assignment 1: Design a Logical Model

## Question 1
Create a logical model for a small bookstore. 📚

At the minimum it should have employee, order, sales, customer, and book entities (tables). Determine sensible column and table design based on what you know about these concepts. Keep it simple, but work out sensible relationships to keep tables reasonably sized. Include a date table. There are several tools online you can use, I'd recommend [_Draw.io_](https://www.drawio.com/) or [_LucidChart_](https://www.lucidchart.com/pages/).

## Question 2
We want to create employee shifts, splitting up the day into morning and evening. Add this to the ERD.

## Question 3
The store wants to keep customer addresses. Propose two architectures for the CUSTOMER_ADDRESS table, one that will retain changes, and another that will overwrite. Which is type 1, which is type 2?

_Hint, search type 1 vs type 2 slowly changing dimensions._

Bonus: Are there privacy implications to this, why or why not?
```
Your answer...
Type 1: Overwrite

In this architecture, only the most recent address for each customer is stored. When a customer updates their address, the existing record is overwritten with the new address. Historical addresses are not retained.

In this design:
- Each time a customer's address changes, the existing record is updated with the new address.
- Historical addresses are not retained, and only the current address is stored.
- This approach simplifies the table structure but does not allow tracking historical changes.

Type 2: Retain Changes

In this architecture, each change to a customer's address is retained as a separate record in the table. It allows tracking historical addresses of customers.

In this design:
- Each time a customer's address changes, a new record is inserted into the table.
- The start_date and end_date columns indicate the period during which the address was valid.
- Historical addresses are retained, enabling analysis of changes over time.

Privacy Implications

There are potential privacy implications to consider, especially with the Type 2 approach where historical addresses are retained. Storing historical addresses could raise concerns about data privacy and security, particularly if sensitive information is involved. Organizations must ensure compliance with privacy regulations and implement appropriate measures to safeguard customer data.

By presenting these two architectures and discussing their implications, we demonstrate an understanding of how column choices influence architecture and the importance of considering privacy concerns in database design.


```
Type 1 (Retain Changes)

In this architecture, each change to a customer's address is retained as a separate record in the table. It allows tracking historical addresses of customers.

In this design:

- Each time a customer's address changes, a new record is inserted into the table.
- The start_date and end_date columns indicate the period during which the address was valid.
- Historical addresses are retained, enabling analysis of changes over time.

Type 2 (Overwrite)

In this architecture, only the most recent address for each customer is stored. When a customer updates their address, the existing record is overwritten with the new address. Historical addresses are not retained.

In this design:

- Each time a customer's address changes, the existing record is updated with the new address.
- Historical addresses are not retained, and only the current address is stored.
- This approach simplifies the table structure but does not allow tracking historical changes.

Privacy Implications

There are potential privacy implications to consider, especially with the Type 1 approach where historical addresses are retained. Storing historical addresses could raise concerns about data privacy and security, particularly if sensitive information is involved. Organizations must ensure compliance with privacy regulations and implement appropriate measures to safeguard customer data.

By presenting these two architectures and discussing their implications, we demonstrate an understanding of how column choices influence architecture and the importance of considering privacy concerns in database design.

## Question 4
Review the AdventureWorks Schema [here](https://i.stack.imgur.com/LMu4W.gif)

Highlight at least two differences between it and your ERD. Would you change anything in yours?
```
Your answer...
```
In reviewing the AdventureWorks Schema (AdventureWorks 2008 OLTP Schema) and comparing it to my ERD, I noted several differences that are worth highlighting:

1) Complexity and Scope: The AdventureWorks schema is notably more extensive and complex compared to the ERD I designed for the small bookstore. AdventureWorks encompasses a wide range of entities, including products, vendors, employees, and sales, with numerous tables and relationships to represent various aspects of a large-scale retail operation. In contrast, my ERD focuses on the essential entities relevant to a small bookstore, such as employees, customers, orders, and books, resulting in a simpler and more focused schema.
2) Additional Functionality: AdventureWorks includes tables and relationships for features such as product inventory management, manufacturing processes, and hierarchical organizational structures. These functionalities go beyond the scope of a basic bookstore operation and are not represented in my ERD. For instance, AdventureWorks includes tables like ProductInventory, WorkOrder, and EmployeeHierarchy, which are not present in my ERD due to the different business contexts.

Reflecting on these differences, I believe that my ERD effectively captures the essential entities and relationships needed for a small bookstore operation while maintaining simplicity and clarity. However, if the scope of the project were to expand or if additional functionalities were required in the future, adjustments and enhancements to the ERD would be necessary to accommodate the new requirements. Overall, the comparison with AdventureWorks highlights the flexibility of database design in adapting to different business contexts and operational needs.
# Criteria

[Assignment Rubric](./assignment_rubric.md)

# Submission Information

🚨 **Please review our [Assignment Submission Guide](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md)** 🚨 for detailed instructions on how to format, branch, and submit your work. Following these guidelines is crucial for your submissions to be evaluated correctly.

### Submission Parameters:
* Submission Due Date: `June 1, 2024`
* The branch name for your repo should be: `model-design`
* What to submit for this assignment:
    * This markdown (design_a_logical_model.md) should be populated.
    * Two Entity-Relationship Diagrams (preferably in a pdf, jpeg, png format).
* What the pull request link should look like for this assignment: `https://github.com/<your_github_username>/sql/pull/<pr_id>`
    * Open a private window in your browser. Copy and paste the link to your pull request into the address bar. Make sure you can see your pull request properly. This helps the technical facilitator and learning support staff review your submission easily.

Checklist:
- [ ] Create a branch called `model-design`.
- [ ] Ensure that the repository is public.
- [ ] Review [the PR description guidelines](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md#guidelines-for-pull-request-descriptions) and adhere to them.
- [ ] Verify that the link is accessible in a private browser window.

If you encounter any difficulties or have questions, please don't hesitate to reach out to our team via our Slack at `#cohort-3-help`. Our Technical Facilitators and Learning Support staff are here to help you navigate any challenges.
