# Discovery Workshop Template
A process defined from a combination of [UX Design](https://www.uxdesigninstitute.com/blog/ux-design-process/), [Design Thinking](https://www.thinkwithgoogle.com/future-of-marketing/creativity/design-thinking-principles/), the book [Sprint: How to Solve Big Problems and Test New Ideas in Just Five Days by Jake Knapp et al](https://www.amazon.com/Sprint-audiobook/dp/B01BXB1B7K), the book [Marketing Made Simple: A Step-by-Step StoryBrand Guide for Any Business by Donald Miller et al](https://www.amazon.com/Marketing-Made-Simple-Step-Step/dp/B07TTTYZRK), the book [Business Made Simple: 60 Days to Master Leadership, Sales, Marketing, Execution, Management, Personal Productivity and More by Donald Miller et al](https://www.amazon.com/Business-Made-Simple-Leadership-Marketing/dp/B0868V7TZG), the book [Hooked: How to Build Habit-Forming Products by Nir Eyal, Ryan Hoover](https://www.amazon.com/Hooked-How-Build-Habit-Forming-Products/dp/B00HZY1N0K), the book [Actionable Gamification: Beyond Points, Badges, and Leaderboards by Yu-kai Chou](https://www.amazon.com/Actionable-Gamification-audiobook/dp/B06XSWX7BN), the book [Lean Marketing: More leads. More profit. Less marketing. by Allan Dib](https://www.amazon.com/Lean-Marketing-Less-More-Business/dp/1774583941), the book [$100M Offers: How To Make Offers So Good People Feel Stupid Saying No (Acquisition.com $100M Series Book 1) by by Alex Hormozi](https://www.amazon.com/100M-Offers-People-Stupid-Saying-ebook/dp/B099QVG1H8), the book [$100M Leads: How to Get Strangers To Want To Buy Your Stuff (Acquisition.com $100M Series Book 2) by Alex Hormozi](https://www.amazon.com/100M-Leads-Strangers-Stuff-Acquisition-com-ebook/dp/B0CFDR3TYV), the book [Start Small, Stay Small: A Developer's Guide to Launching a Startup by by Rob Walling et al](https://www.amazon.com/Start-Small-Stay-Developers-Launching/dp/0615373968) and many more…

**NOTE:** This process might be overwhelming and is geared towards longer/larger engagements with established companies. If you are looking for the quick-start or this is your first business, consider [Alex Hormozi's 5 Step Process to Starting a Business](https://github.com/RyanJulyan/rocket/blob/main/02_discovery_and_planning_phase/quickstarts/alex_hormozi_5_step_process.md)

## {{project_name}}:

### Discovery Workshop: {{title}}:

### Workshop Purpose:  
- Understand User and Business Needs
- Ideation and Concept Development
- Design Thinking and Prototyping
- Roadmap and Prioritization

### Discovery Workshop Date: {{workshop_date}}
### Time: {{workshop_start_time}} - {{workshop_end_time}}
### Location [Physical Location / Online Platform]: {{workshop_location}}

#### Materials Provided:
- [List any handouts, guides, or equipment that will be provided]

#### Preparation Required:  
- [List any pre-work or information participants should bring to the workshop]

#### Outcome Documentation:
- [Describe how the outcomes will be documented and shared post-workshop]

#### Participants

| Attendant Name          | Role               | Contact Information           |
|-------------------------|--------------------|-------------------------------|
{% for role in workshop %}
| {{role.allocated_name}} | {{role.name}}      | {{role.email}}                |
{% endfor %}

### Agenda:  
#### 1. **Introduction and Welcome**
- Opening remarks
- Overview of the revised agenda
- Icebreaker activity
   - [ ] e.g. What is your "silly" life hack

#### 2. **Session 1: Project Background and Client Expectations:**
- Complete the following in the [Client Briefing template](https://github.com/RyanJulyan/rocket/blob/main/01_initiation_phase/01_client_briefing_template.md)
   - [ ] Purpose of the Project
   - [ ] Key Objectives
   - [ ] Vision and End Goals
   - [ ] Expected Outcomes
   - [ ] Specific Features/Functions
   - [ ] Success Criteria

#### 3. **Session 2: Design Thinking, Ideation and Prototyping**
- Complete the following in the [Design Thinking Template](https://github.com/RyanJulyan/rocket/blob/main/02_discovery_and_planning_phase/03_design_thinking_template.md)
   - [ ] Introduction to design thinking principles
   - [ ] Team breakout sessions for idea generation
      - [ ] User research and expectations
         - User Types and personas
         - [User desired actions](https://github.com/RyanJulyan/rocket/blob/main/03_design_and_documentation_phase/01_design_document_template.md#user-types--desired-actions)
         - Link user-desired actions to business metrics
      - [ ] Identify Internal Solutions
         - [ ] Successes
         - [ ] Failures
         - [ ] Learnings
      - [ ] External Inspiration
         - [ ] Likes
         - [ ] Dislikes
         - [ ] Cool Factor
      - [ ] Current Trends
      - [ ] Actionable Insights
      - [ ] Hands-on prototyping of selected ideas
   - Group activity to present ideas and prioritize features 
      - [ ] Group presentations and feedback on prototypes
      - [ ] [Feature prioritization](https://github.com/RyanJulyan/rocket/blob/main/03_design_and_documentation_phase/01_design_document_template.md#features-and-priorities)

#### 4. **Session 3: User and Business Needs**
- Complete the following in the [Design Document Template](https://github.com/RyanJulyan/rocket/blob/main/03_design_and_documentation_phase/01_design_document_template.md)
   - [ ] [Business Metrics](https://github.com/RyanJulyan/rocket/blob/main/03_design_and_documentation_phase/01_design_document_template.md#business-metrics):
      - Detailed objectives with associated SMART metrics
      - Methodology for measurement and tracking
   - [ ] High-level [process flowchart](https://github.com/RyanJulyan/rocket/blob/main/03_design_and_documentation_phase/01_design_document_template.md#high-level-process-flowchart)
      - Detailed logical view with diagrams
      - Description of the 4+1 architectural view
      - Narratives for each high-level process
- Group activity to identify key business and user needs
   - [ ] Discussion on aligning user needs with business goals

#### 5. **Session 4: Technical Considerations and Constraints**
- Complete the following in the [Technical and Data Specifications Template](https://github.com/RyanJulyan/rocket/blob/main/03_design_and_documentation_phase/02_technical_and_data_specifications_template.md)
   - [ ] Discuss key technical considerations: 
      - Hardware limitations
      - Software limitations
      - system integration challenges
      - Security and compliance requirements
   - Group discussion on the technical feasibility of concepts
   - Identifying potential technical risks and mitigation strategies

#### 6. **Session 5: Data Considerations and Strategy**
- Discuss data governance, privacy, and compliance (e.g., GDPR, CCPA)
- Exploration of data collection, storage, and usage requirements
- Strategies for data integration, quality assurance, and scalability

#### 7. **Session 6: API Design and Integration**
- Overview of API development strategies and best practices
- Discussion on API integration with external/internal systems
- Considerations for API security, scalability, and documentation

#### 8. **Session 7: Roadmap and Prioritization**
- Presentation on project management frameworks
- Interactive session on prioritizing features and deliverables, considering user/business needs, technical constraints, data, and API aspects
- Creation of a preliminary roadmap integrating all discussed elements

#### 9. **Session 8: Scalability and Future Proofing**
- Discussion on project scalability, including data and API growth strategies
- Strategies for long-term support, maintenance, and continuous improvement
- Considerations for cross-platform compatibility and mobile optimization

#### 10. **Closing Remarks and Next Steps**
- Summary of the workshops findings, decisions, and identified considerations across all areas
- Outline of next steps, responsibilities, and business and technical follow-ups
- Feedback collection on the workshop, with an emphasis on the comprehensive approach

### Approvals:
- **Workshop Coordinator:**
   - **Name:** {{workshop_coordinator_name}}
   - **Title:** {{workshop_coordinator_title}}
   - **Date:** {{ now() }}
   - **Signature:** _________________________
- **Client Representative:**
   - **Name:** {{client_representative_name}}
   - **Title:** {{client_representative_title}}
   - **Date:** {{ now() }}
   - **Signature:** _________________________
