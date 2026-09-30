*Intuz — Your automation partner, one workflow at a time.*

<p align="center">
  <picture>
    <img alt="Banner Image" src="https://github.com/user-attachments/assets/210f97fc-0fce-404a-b647-7dfe1302cd37" />
  </picture>
</p>

[Intuz](https://www.intuz.com) helps organizations orchestrate AI, automation, and enterprise systems through scalable workflows. Our repository showcases proven implementations across healthcare, operations, customer support, document processing, sales, and back-office functions, enabling teams to accelerate automation initiatives without starting from scratch.

[N8N Creator](https://n8n.io/creators/intuz/) · [Enterprise AI Development](https://www.intuz.com/ai/) · [Custom AI Development Company](https://www.intuz.com/company/) · [For Custom Workflow Automation](https://www.intuz.com/get-started/)

# Automate QuickBooks sales receipts & customer creation from Stripe payments

This n8n template from Intuz provides a complete solution to automate your accounting by instantly creating QuickBooks sales receipts for every new Stripe payment.

This workflow automates the process of recording successful payments from Stripe into QuickBooks by creating corresponding Sales Receipts. It ensures payment data is captured accurately, checks whether the customer exists in QuickBooks, and creates a new customer if necessary before generating the receipt.

This integration streamlines bookkeeping by eliminating manual data entry and ensuring all payment records are synchronized between systems.

## Who’s this workflow for?

- Accountants & Bookkeepers
- Small Business Owners
- E-commerce Managers
- Finance Teams

## How it works

1. **Trigger on Successful Payment:** The workflow starts instantly when a `payment_intent.succeeded` event is received from Stripe via a webhook. This means it only runs after a payment is confirmed.

2. **Get Customer Details:** It uses the customer ID from the payment to fetch the customer’s full details (name and email) from Stripe.

3. **Check for Customer in QuickBooks:** The workflow then searches your QuickBooks account to see if a customer with that name already exists.

4. **Create Customer if New:** If the customer is not found in QuickBooks, a new customer record is automatically created using the information from Stripe.

5. **Generate Sales Receipt:** Finally, using the correct customer record (either existing or newly created) and the payment amount, the workflow creates and saves a new sales receipt in QuickBooks, perfectly matching the Stripe transaction.

## Key Requirements to Use This Template

1. **n8n Instance:** An active n8n account (Cloud or self-hosted).
2. **Stripe Account:** An active Stripe account with API access. You must be able to create and manage webhooks.
3. **QuickBooks Online Account:** An active QuickBooks Online account with API access to manage customers and sales receipts.

## Setup Instructions

### 1. Configure the Webhook Trigger

- Copy the webhook URL from the **Capture Payment (Webhook)** node in n8n.
- In your Stripe dashboard, go to **Developers > Webhooks** and add a new endpoint.
- Paste the n8n webhook URL and have it listen for the `payment_intent.succeeded` event.

### 2. Connect Stripe

- In the **Get a customer** node, connect your Stripe account credentials.

### 3. Connect QuickBooks

- In all three QuickBooks nodes (**Find Customer**, **Create a customer**, and **Create a payment**), connect your QuickBooks Online account using OAuth2 credentials.

### 4. Activate Workflow

- Save the workflow and toggle the **Active** switch to ON. Your accounting automation is now live!

## FAQ

**Is this template free to use?**
Yes. It's an open-source n8n workflow published by Intuz — copy the workflow JSON from this repo and import it into your own n8n instance at no cost.

**Do I need a paid n8n plan to run this?**
No. It runs on n8n's free self-hosted Community Edition or on n8n Cloud. You'll need your own Stripe and QuickBooks credentials, not a specific n8n pricing tier.

**What happens if the customer already exists in QuickBooks?**
The workflow reuses that customer. It searches QuickBooks by name after fetching Stripe customer details; if no match is found, it creates the customer first, then writes the sales receipt.

## Related n8n templates from Intuz

- [Automate QuickBooks customers & sales receipts generation from a Google Sheet](https://github.com/Intuz-production/Automate-QuickBooks-Customer-Sales-Receipt-Creation)
- [Automate full-cycle invoicing from Airtable to QuickBooks and Stripe](https://github.com/Intuz-production/QuickBooks-Invoice-Payment-Automation)
- [Automate real-time QuickBooks invoice sync to Google Sheets](https://github.com/Intuz-production/QuickBooks-Invoice-Sync)

[See all of Intuz's free n8n templates](https://www.intuz.com/n8n-workflow-automation-templates/)

## Connect with us

Intuz is a USA-based AI & workflow automation company with 16+ years of experience building custom AI-enabled workflow automations for SMBs and Enterprises, specializing in agentic AI, LLM integrations, and CRM/ERP sync across Healthcare, FinTech, eCommerce, Manufacturing, and Real Estate.

* **Website:** [https://www.intuz.com](https://www.intuz.com)
* **Email:** [getstarted@intuz.com](mailto:getstarted@intuz.com)
* **LinkedIn:** https://www.linkedin.com/company/intuz/
* **Get Started:** https://n8n.partnerlinks.io/intuz

## For Custom Workflow Automation

[Click here - Get Started](https://www.intuz.com/get-started/)
