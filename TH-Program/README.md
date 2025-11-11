# Cyber Threat Hunt Program Repository

This repository serves as the central location for all documentation, templates, and procedures related to the Cyber Threat Hunt (CTH) program.

## How to Use Hunt Plan Templates

All standardized hunt plan templates are located in the `/templates` directory. To start a new hunt:

1.  **Navigate** to the [`/templates`](./templates/) folder.
2.  **Select** the template that best fits your hunt type (e.g., `02-cti-based-template.md`).
3.  **Copy** the raw Markdown content from the template.
4.  **Create** a new file for your active hunt. It's recommended to create a new folder for active hunts and use a standard naming convention like `YYYY-MM-DD_[TTP-ID_or_Name].md`.
5.  **Paste** the template content into your new file and fill out all the required sections.
6.  **Link** to this new hunt plan file from your main `CTH Hunt Tracker` in SharePoint.



### Available Templates

* **[Base Template](./templates/01-base-template.md):** A generic, all-purpose hunt plan.
* **[CTI-Based Template](./templates/02-cti-based-template.md):** For hunts derived from a specific threat intelligence report or actor.
* **[TTP-Based Template](./templates/03-ttp-based-template.md):** For deep-dive hunts on a specific MITRE ATT&CK technique.
* **[Campaign-Based Template](./templates/04-campaign-based-template.md):** For hunting active, widespread campaigns like Log4Shell or SolarWinds.
* **[Purple Team Template](./templates/05-purple-team-template.md):** For validating detection controls against a planned emulation.
* **[Anomaly-Based Template](./templates/06-anomaly-based-template.md):** For investigating statistical or behavioral anomalies from UBA/ML tools.
