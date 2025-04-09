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

### 1. Tariff Data Specification (TDS)
Defines mandatory and optional data fields and their formats to be used in supplier APIs.

👉 **View the current TDS draft:** [Data Specification](https://view.officeapps.live.com/op/view.aspx?src=https%3A%2F%2Fraw.githubusercontent.com%2FRetail-Energy-Code%2Ftariff-interoperability%2Frefs%2Fheads%2Fmain%2FTariff%2520Data%2520Specification.xlsx&wdOrigin=BROWSELINK).
👉 **View the previous feedback received on the TDS:** [TDS Feedback](https://view.officeapps.live.com/op/view.aspx?src=https%3A%2F%2Fraw.githubusercontent.com%2FRetail-Energy-Code%2Ftariff-interoperability%2Frefs%2Fheads%2Fmain%2Ffeedback%2FFeedback%2520on%2520Tariff%2520Data%2520Specification%2520(TDS).xlsx&wdOrigin=BROWSELINK).

### 2. API Specification
Serves as a blueprint for suppliers to develop their tariff-sharing APIs.

👉 **View the API specification draft:** [API Specification](https://38db35b56c92.edge.eu.portal.konghq.com/apis/api-for-sharing-tariff-data-1-0-0/specifications/84d45b00-df1b-40d4-a322-708590da9549).

---

## How to Provide Feedback

We encourage industry stakeholders to share their feedback through **email** to:

📩 **chris.stock@retailenergycode.co.uk**

- For the TDS: We will provide a structured Excel template for feedback.
- For the API spec: Please provide direct comments or documents.

All feedback will be:
- Reviewed and anonymised
- Uploaded to this GitHub repository (see [/feedback](feedback/) folder)
- Logged and responded to regularly

🕓 The feedback folder will be updated **daily** when new input is received.

> We understand participants may prefer different channels, so we aim to keep this process flexible.

---

## Feedback Focus Areas

We are especially interested in your thoughts on:

- ⚙️ **Filtering criteria**: Is filtering by `region` sufficient? Would other criteria be useful?
- 🔐 **Authentication**: We're using **OIDC (OpenID Connect)**. Is this appropriate for your use case?
- 🧩 **General feedback** to improve functionality and alignment with use cases.

Please email all feedback to **chris.stock@retailenergycode.co.uk**.

---

## Stay Connected

We value your involvement and appreciate your contributions to this collaborative project. All updates and materials will be published here in this repository, so stay tuned!

Let’s work together to shape a smarter, more flexible energy future. ⚡
