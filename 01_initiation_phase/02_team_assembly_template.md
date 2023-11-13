# Team Assembly Template

## {{project_name}}:

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
