# Client Briefing Template

## {{project_name}}:

### Client Information:
- Client Name: {{client_name}}
- Key Contact: {{key_contact_name}}
- Contact Information Email: {{key_contact_email}}
- Contact Information Cell Phone: {{key_contact_cell_phone}}
- Industry: {{client_industry}}

### Project Background:
- Project Code: {{project_code}}
- Purpose of the Project: {{project_purpose}}
- Key Objectives: {{project_key_objectives}}
- Expected Outcomes: {{project_expected_outcomes}}

### Scope of Work:
### Client Expectations:
- **Vision and End Goals:**
{{project_client_vision}}
- **Specific Features/Functions:**
{{project_features_overview}}
- **Success Criteria:**
{{project_success_criteria}}

### Phases:
{% for phase in phases %}
#### {{phase.name}}:
- **Phase Total Budget:** {{phase.total_budget}}
- **Phase Total Timeframe:** {{phase.total_expected_timeframe}}

#### Client Expectations for Phase:
- **Phase Vision and End Goals:** {{phase.client_vision}}
- **Phase Specific Features/Functions:** {{phase.features_overview}}
- **Phase Success Criteria:** {{phase.success_criteria}}

    | Deliverable                  | Milestones                 | Expected Timeline          |
    |------------------------------|----------------------------|----------------------------|
    {% for deliverable in phase.deliverables %}
    | {{deliverable.description}}  | {{deliverable.milestones}} | {{deliverable.start_date}} - {{deliverable.end_date}}  |
    {% endfor %}
{% endfor %}

### Constraints and Considerations:
- **Total Budget:** {{project_total_budget}}
- **Expected Timeframe:** {{project_expected_timeframe}}
- **Legal/Compliance:**
    1. **Data Protection and Privacy Laws:**
        - **GDPR (General Data Protection Regulation):** If operating in or handling, compliance with the GDPR is mandatory if you operate in or handle on.
            * {{project_legal_gdpr}}
        **POPIA (Protection of Personal Information Act):** This is Similar to GDPR but for South African residents.
            * {{project_legal_popia}}
        - **Other National/Regional Data Protection Laws:** Depending on the project's geographical scope, consider relevant local data protection regulations.
            * {{project_legal_other}}
    1. **Intellectual Property Rights:**
        - **Copyright and Trademark Laws:** Ensure the project doesn't infringe on existing copyrights or trademarks.
            * {{project_legal_copyright_and_trademark}}
        - **Patent Considerations:** To avoid patent infringements, consider patenting novel technologies or processes developed during the project.
            * {{project_legal_patent}}
        - **Licensing Agreements:** Review all software and content licenses to ensure compliance.
            * {{project_legal_licensing}}
    1. **Contractual Obligations and Agreements:**
        - **Vendor Contracts:** Ensure agreements with vendors or partners comply with legal requirements.
            * {{project_legal_vendor_contracts}}
        - **Client Contracts:** Review the project's scope as defined in client contracts for any legal obligations.
            * {{project_legal_client_contracts}}
        - **Non-Disclosure Agreements (NDAs):** Compliance with NDAs and confidentiality agreements is critical.
            * {{project_legal_nda}}
    1. **Cybersecurity Laws and Regulations:**
        Industry-Specific Cybersecurity Standards:** Depending on the industry, specific cybersecurity standards may need to be adhered to.
            *  {{project_legal_cybersecurity_standards}}
    1. **Record-Keeping and Reporting Requirements:**
        - **Legal Documentation:** Ensure proper documentation and reporting as required by law for auditing and compliance purposes.
            *  {{project_legal}}
- **Technical Limitations:** {{project_technical_limitations}}

### Additional Notes:
- **Previous Work/References:**
    - {{project_previous_work_reference}}
- **Competitor Analysis:**
    - {{project_competitor_analysis}}
- **Any other relevant information:**
    - {{project_other_information}}
