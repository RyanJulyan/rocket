# Team Assembly Template

## {{project_name}}:

**Ensure You Consider Team Composition:**
- [ ] **Project Manager:**
    - {{project_manager_excluded_reason}}
- [ ] **Lead Developer:**
    - {{lead_developer_excluded_reason}}
- [ ] **UX Designer:**
    - {{ux_excluded_reason}}
- [ ] **UI Designer:**
    - {{ui_excluded_reason}}
- [ ] **Data Specialist:**
    - {{data_specialist_excluded_reason}}
- [ ] **Lead Backend Developer:**
    - {{lead_backend_developer_excluded_reason}}
- [ ] **Lead Frontend Developer:**
    - {{lead_frontend_developer_excluded_reason}}
- [ ] **Quality Assurance Lead:**
    - {{quality_assurance_lead_excluded_reason}}
- [ ] **Other Specialists:**
    - {{other_specialists_excluded_reason}}

{% for phase in phases %}
- **{{phase.name}}:**
    ### Team Composition:
    {% for role in team_member_details %}
    - **{{role.phase}} - {{role.name}}:** {{role.allocated_name}} 
    {% endfor %}

    ### Team Member Details:

    | Name                    | Project Phase  | Expected Allocation | Role in Project    | Contact Information           | Additional Resources | Responsibilities          |
    |-------------------------|----------------|---------------------|--------------------|-------------------------------|----------------------|---------------------------|
    {% for role in phase.team_member_details %}
    | {{role.allocated_name}} | {{role.phase}} | {{role.allocation}} | {{role.name}}       | {{role.email}}/{{role.cell}} | {{role.resources}}   | {{role.responsibilities}} |
    {% endfor %}

    ### Availability & Scheduling:
    {% for meeting in phase.standard_meetings %}
    - **{{meeting.name}}:**
        - **Type:**{{meeting.type}}
        - **Date Range:** {{meeting.date_range}}
        - **Time:** {{meeting.time}}
    {% endfor %}

    ### Team Approval:
    {% for role in phase.team_member_details %}
    - {{role.name}}
        - **Name:** {{role.allocated_name}} 
        - **Title:** {{role.allocated_name_title}}
        - **Date:** {{ now() }}
        - **Signature:** _________________________
    {% endfor %}
{% endfor %}
