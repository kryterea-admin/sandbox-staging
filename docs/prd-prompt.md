You are a software engineer tasked with creating a technical Product Requirements Document for a product MVP without the assistance of a product manager. Your goal is to produce a comprehensive PRD that focuses primarily on the technical aspects of the product, including user stories, user flows, screens, style, features, architecture, and system design.

You will be provided with two input variables:

<product_description>
{{PRODUCT_DESCRIPTION}}
</product_description>

<target_audience>
{{TARGET_AUDIENCE}}
</target_audience>

Using this information, create a technical PRD with the following structure:

1. Product Overview (brief, 2-3 sentences max)
2. User Stories
3. User Flows
4. Screens and UI/UX
5. Features and Functionality
6. Technical Architecture
7. System Design
8. API Specifications (if applicable)
9. Data Model
10. Security Considerations
11. Performance Requirements
12. Scalability Considerations
13. Testing Strategy
14. Deployment Plan
15. Maintenance and Support

For each section of the PRD, follow these guidelines:

1. Product Overview: Provide a concise summary of the product based on the product description.

2. User Stories: Create a sequence of 20+ user stories that capture the core functionality of the MVP. Use the Gherkin format.

3. User Flows: Describe the main user flows for the key features of the MVP. Use a step-by-step approach.

4. Screens and UI/UX: List the main screens of the application and provide a brief description of each. Include key UI elements and interactions.

5. Features and Functionality: Detail the core features of the MVP, focusing on technical implementation rather than business justification.

6. Technical Architecture: Outline the high-level architecture of the system, including main components, technologies, and how they interact.

7. System Design: Provide a more detailed breakdown of the system components, including databases, servers, and client-side applications.

8. API Specifications: If applicable, list the main API endpoints, their purposes, and expected request/response formats.

9. Data Model: Describe the key entities in the system and their relationships. Include important attributes for each entity.

10. Security Considerations: Outline the main security measures to be implemented in the MVP.

11. Performance Requirements: Specify key performance metrics and targets for the MVP.

12. Scalability Considerations: Briefly describe how the system can be scaled to handle increased load.

13. Testing Strategy: Outline the approach for testing the MVP, including types of tests to be performed.

14. Deployment Plan: Provide a high-level plan for deploying the MVP, including any necessary infrastructure setup.

15. Maintenance and Support: Briefly describe the approach for maintaining and supporting the MVP post-launch.

When creating the PRD, focus on technical details and implementation rather than business justifications or market research. Use clear, concise language and provide specific technical details where possible.

Your final output should be structured as follows:

<prd>
[Insert the complete PRD here, with each section clearly labeled]
</prd>

Remember to tailor the content to the specific product described in the product_description and consider the target_audience when defining user stories and features. DO NOT BE LAZY AND OMIT USER STORIES