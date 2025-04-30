# SSES Tariff Interoperability Project

## Overview

The **SSES Tariff Interoperability Project** is an industry initiative designed to enable enhanced **demand-side flexibility** in the UK energy market. It aims to standardise how **tariff data** is shared by energy suppliers, making integration with **Energy Saving Appliances (ESAs)** easier and more consistent.

This project is being delivered by **RECCo** and includes:
- The **Tariff Data Specification (TDS)**
- The **API Specification**
- A **Governance & Assurance framework**
- Supporting changes to the **Retail Energy Code (REC)**

Suppliers will be required to build and maintain APIs that provide tariff data in line with the TDS, accessible by approved parties acting on behalf of customers.

---

## How the Project Operates

The project is coordinated through the **Tariff Interoperability Working Group (TIWG)**, chaired by RECCo. Originally chaired by DESNZ during policy and use case development, TIWG now focuses on reviewing and approving the evolving solution.

A separate group, the **Tariff Interoperability Solution Working Group (TISWG)**, will develop the:
- Technical solution
- Governance & Assurance approach
- Draft REC changes

Once finalized, these solutions will be reflected in REC text and formally consulted on by DESNZ. Suppliers will then implement their APIs in line with the published specifications.

---

## Key Deliverables

### 1. Tariff Data Standard (TDS)
Defines mandatory and optional data fields and their formats to be used in supplier APIs.

👉 **View the current TDS draft:** [Tariff Data Standard](https://github.com/Retail-Energy-Code/tariff-interoperability/blob/main/Tariff%20Data%20Standard.xlsx).

👉 **View the previous feedback received on the TDS:** [TDS Feedback](https://github.com/Retail-Energy-Code/tariff-interoperability/blob/main/feedback/Feedback%20on%20Tariff%20Data%20Standard.xlsx).

### 2. API Specification
Serves as a blueprint for suppliers to develop their tariff-sharing APIs.

👉 **View the API specification draft:** [API Specification](https://38db35b56c92.edge.eu.portal.konghq.com/apis/api-for-sharing-tariff-data-1-0-0/specifications/84d45b00-df1b-40d4-a322-708590da9549).

👉 **View the OIDC reference here:** [OIDC M2M Standard Flow](https://github.com/Retail-Energy-Code/tariff-interoperability/blob/main/OIDC.png). The use of OIDC is subject to further discussion and confirmation during solution development.

---

## How to Provide Feedback

We encourage industry stakeholders to share their feedback through the use of the [**GitHub discussion**](https://github.com/Retail-Energy-Code/tariff-interoperability/discussions/) feature.

Or through email to:

📩 **chris.stock@retailenergycode.co.uk**

As we move into solution development, we will be seeking your input and review across a number of documents. Providing feedback through the [**GitHub discussion**](https://github.com/Retail-Energy-Code/tariff-interoperability/discussions/) feature will be open, transparent and will allow for other interested stakeholders to interact with your feedback and stimulate helpful discussion.

- For the TDS: Thanks for the feedback we received through the structure Excel spreadsheet. You can view this feedback here: [TDS Feedback](https://github.com/Retail-Energy-Code/tariff-interoperability/blob/main/feedback/Feedback%20on%20Tariff%20Data%20Standard.xlsx).

- For the API spec: This feedback can be viewed here: [API Spec Feedback](https://github.com/Retail-Energy-Code/tariff-interoperability/blob/main/feedback/Tariff%20Interoperability_API%20Specification%20Central%20Feedback.xlsx).

All feedback will be:
- Reviewed and anonymised
- Uploaded to this GitHub repository (see [/feedback](feedback/) folder)
- Logged and responded to regularly

🕓 The feedback folder will be updated **daily** when new input is received.

> We understand participants may prefer different channels, so we aim to keep this process flexible.

---

## Feedback Focus Areas

We are especially interested in your thoughts on the API Specification, including but not limited to the following:

- ⚙️ **Filtering criteria**: Is filtering by `region` sufficient? Would other criteria be useful?
- 🔐 **Authentication**: We're using **OIDC (OpenID Connect)**. Is this appropriate for your use case?
- 🧩 **General feedback** to improve functionality and alignment with use cases.

Please email all feedback to **chris.stock@retailenergycode.co.uk**.

---

## Stay Connected

We value your involvement and appreciate your contributions to this collaborative project. All updates and materials will be published here in this repository, so stay tuned!

Let’s work together to shape a smarter, more flexible energy future. ⚡
