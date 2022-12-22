# Microsoft Sentinel
Security Information Event Management (SIEM) and Security Orchestration Automated Response (SOAR) provide security insights and security automation that can enhance an organisation's threat visibility and response.

### What is SIEM
A SIEM system is a tool that collects data from across the whole estate, including infrastructure, software and resources. It does analysis, looks for correlations or anomalies and generates alerts and incidents.

### What is SOAR
A SOAR system takes alerts from many sources such as a SIEM system. The SOAR system then triggers action-driven automated workflows and processes to run security tasks that mitigate the issue.

## Microsoft Sentinel provides integrated threat management
Microsoft Sentinel is a scalable, cloud-native SIEM/SOAR solution that delivers intelligent security analytics and threat intelligence across the enterprise. It provides a single solution for alert detection, threat visibility, proactive hunting and threat response.

End-to-end functionality of Microsoft Sentinel:
* **Collect** data at cloud scale across all users, devices, applications and infrastructure, both on-premises and in multiple clouds.
* **Detect** previously uncovered threats and minimise false positives using analytics and unparalleled threat intelligence.
* **Investigate** threats with AI and hunt suspicious activities at scale, tapping into decades of cybersecurity work at Microsoft.
* **Respond** to incidents rapidly with built-in orchestration and automation of common security tasks.

### Connect Sentinel to your data
To on-board Microsoft Sentinel, you first need to connect to your security sources. Microsoft Sentinel comes with many connectors for Microsoft solutions, availabe out of the box and providing real-time integration. Included are [[365-defender|Microsoft 365 Defender]] solutions and Microsoft 365 sources, including Office 365, [[azure-ad|Azure AD]] and more. In addition, there are built-in connectors to the broader security ecosystem of non-Microsoft solutions. Community-built data connectors are also available to connect your data sources, listed in the Microsoft Sentinel GitHub repository or by following generic deployment procedures.

### Workbooks
After connecting data sources to Microsoft Sentinel, you can monitor the data using the Microsoft Sentinel integration with Azure Monitor Workbooks. You'll see a canvas for data analysis and the creation of rich visual reports within the Azure portal. Through this integration, Microsoft Sentinel allows you to create custom workbooks across your data. It also comes with built-in workbook templates that allow quick insights across your data as soon as you connect a data source.

### Analytics
Microsoft Sentinel uses analytics to correlate alerts into incidents. Incidents are groups of related alerts that together create an actionable possible-threat that can be investigated and resolved. With analytics in Microsoft Sentinel, you can use the built-in correlation rules as-is, or use them as a starting point to build your own. Microsoft Sentinel also provides machine learning rules to map your network behavior and then look for anomalies across your resources. These analytics connect the dots, by combining low fidelity alerts about different entities into potential high-fidelity security incidents.

### Manage incidents in Microsoft Sentinel
Incident management allows you to manage the lifecycle of the incident. View all related alerts that are aggregated into an incident. Can also triage and investigate and review all related entities in the incident and additional contextual information, meaningful to the triage process. Investigate the alerts and related entities to understand the scope of breach. Trigger playbooks on the alerts grouped in the incident to resolve the threat detected by the alert. You can also do standard incident management tasks like changing status or assigning incidents to individuals for investigation.

### Security automation and orchestration
Microsoft Sentinel can be used to automate some of your security operations and make the Security Operations Center (SOC) more productive. Microsoft Sentinel integrates with Azure Logic Apps, so automated workflows can be created, or playbooks, in reponse to events. A security playbook is a collection of procedures that can help SOC engineers and analysts of all tiers to automate and simplify tasks and orchestrate a response. Playbooks work best with single, repeatable tasks and require no coding knowledge.

### Investigation
Currently in preview, Microsoft Sentinel's deep investigation tools help understand the scope of a potential security threat and find the root cause. An entity can be chosen on the interactive graph to ask specific questions, then drill down into that entity and its connections to get to the root cause of the threat.

### Hunting
Use Microsoft Sentinel's powerful hunting search-and-query tools, based on the MITRE framework (a global database of adversary tactics and techniques), to proactively hunt for security threats across the organisation's data sources, before an alert is triggered. After the discovering which hunting query provides high-value insights into possible attacks, you can also create custom detection rules based on the query and surface those insights as alerts to the security incident responders.

While hunting, bookmarks can be created for interesting events. Bookmarking events enables you to return to them later, share them with others and group them with other correlating events to create a compelling incident for investigation.

### Notebooks
Microsoft Sentinel supports Jupyter notebooks, which is an open-source web application that allows creation and sharing of documents that contain live code, equations, visualisations and narrative text. Jupyter notebooks can be used in Microsoft Sentinel to extend the scope of what can be done with Microsoft Sentinel data. 

### Community
The Microsoft Sentinel community is a powerful resource for threat detection and automation, as Microsoft security analysts constantly create and add new workbooks, playbooks and hunting queries. 

## Sentinel Costs
The data used for security analytics is stored in an Azure Monitor Log Analytics workspace, and billing is based on the volume of data ingested for analysis in Microsoft Sentinel. There are 2 ways to pay for Microsoft Sentinel:
* **Capacity Reservations**: Billed a fixed fee based on the selected tier, enabling a predictable total cost
* **Pay-As-You-Go**: Billed per gigabyte for the volume of data ingested for analysis in Microsoft Sentinel and stored in the Azure Monitor Log Analytics workspace
