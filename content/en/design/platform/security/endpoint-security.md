---
title: "Endpoints and Devices"
weight: 5
description: "This section describes the design decisions associated with managing endpoint security for system(s) built using ASD's Blueprint for Secure Cloud."
---

### Microsoft Defender for Endpoint

Microsoft Defender for Endpoint extends the standard Microsoft Defender capabilities to provide additional reporting, pre-breach protection, post-breach detection, automation, and response. Microsoft Defender for Endpoint does not require an agent on the endpoint or any on-premises infrastructure, instead it leverages Microsoft's cloud platform. A single dashboard allows administrators to monitor the compliance and security of all defender-enabled devices, as well as providing ISO27001 certified Endpoint Detection and Response (EDR) functionality.

Defender for Endpoint uses the following combination of technology built into Windows 10 and 11, and Microsoft's robust cloud service:

* **Endpoint behavioural sensors** - Embedded in Windows 10 and 11, these sensors collect and process behavioural signals from the operating system and send this sensor data to 'an organisation's private, isolated, cloud instance of Microsoft Defender for Endpoint.
* **Cloud security analytics** - Behavioural signals are translated into insights, detections, and recommended responses to advanced threats by leveraging big-data, device learning, and unique Microsoft optics across the Windows ecosystem, enterprise cloud products, such as Office 365, and online assets.
* **Threat intelligence** - Generated by Microsoft hunters, security teams, and augmented by threat intelligence provided by partners, threat intelligence enables Defender for Endpoint to identify attacker tools, techniques, and procedures, and generate alerts when they are observed in collected sensor data.

Microsoft Defender for Endpoint can be configured with the following options:

* **Data Retention Period** - defines how long gathered telemetry data is stored and available for use in online reporting.
* **Alert Notifications** - are configurable rule sets that enable a person or group of people to receive a notification on the occurrence of a pre-set event.
* **Secure Score Baseline** - configures the product baselines for calculating the score of Microsoft Defender security controls on the secure score dashboard. If third-party solutions are in use the corresponding controls should be excluded from the calculations.
* **Administration Roles and Machine Groups** - Administration roles provide the ability to configure role-based access and granular options for regulating permissions to portal features and data. Machine groups enable machines to be organised into groups and apply configured automated remediation levels and assigned administrators.

{{% alert title="Design Decisions" color="warning" %}}

| Decision Point                       | Design Decision                                                                                                                                                                                                                                                                           | Justification                                                                                                                                                                                                                                                                                                     |
| ------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Microsoft Defender for Endpoint      | [Configured](https://security.microsoft.com/securitysettings)                                                                                                                                                                                                                             | To provide increased security and meet the requirements of this document.                                                                                                                                                                                                                                         |
| Sample Collection                    | Enabled                                                                                                                                                                                                                                                                                   | Required configuration to enable<br>Deep Analysis on files when required.                                                                                                                                                                                                                                         |
| Data Storage Location                | Australia                                                                                                                                                                                                                                                                                 | All data used by Microsoft Defender for Endpoint is protected at minimum by Advanced Encryption Standard (AES) 256-bit encryption, both at rest and inflight.                                                                                                                                                     |
| Data Retention Period                | 180 Days                                                                                                                                                                                                                                                                                  | Default configuration and suitable for the organisation's requirements.                                                                                                                                                                                                                                           |
| Alert Notifications                  | Send Information, Low, Medium, High to Security team.                                                                                                                                                                                                                                     | Alerts will be sent to the organisation's Security Operation Centre (SOC) for action.                                                                                                                                                                                                                             |
| Secure Score Baseline                | Windows Defender Antivirus<br>Windows Defender Application Control<br>Windows Defender Exploit Guard<br>Windows Defender Application Guard<br>Windows Defender SmartScreen<br>Windows Defender Firewall<br>Windows Defender Credential Guard<br>Windows Defender Attack Surface Reduction | Meets the requirements of this design                                                                                                                                                                                                                                                                             |
| Administration Roles                 | Full Administrator                                                                                                                                                                                                                                                                        | Administrative roles will be segregated as per ASD's [Restricting Administrative Privileges (October 2021) guide](https://www.cyber.gov.au/resources-business-and-government/maintaining-devices-and-systems/system-hardening-and-administration/system-administration/restricting-administrative-privileges). |
| Machine Groups                       | All Clients                                                                                                                                                                                                                                                                               | Machines will be segregated into groups with automated remediation levels assigned the administrators that monitor these groups. Groups will be developed with the organisation and documented in the Configuration documentation.                                                                                |
| Machine onboarding and configuration | Configured                                                                                                                                                                                                                                                                                | Onboarding and configuration will be performed by Endpoint Manager.                                                                                                                                                                                                                                               |

{{% /alert %}}

### Related information

#### Security & Governance

* None identified

#### Design

* None identified

#### References

* [Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)
* [Microsoft Defender for Endpoint in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-365-security-center-mde)