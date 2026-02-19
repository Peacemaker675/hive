# Recipe: Document Processing

Extracting structured information (name, date, amount) from messy, unstructured text and documents.

## Why

Reading through invoices, receipts, and emails manually is tedious, error-prone, and doesn't scale. When data is trapped in unstructured formats, it creates a bottleneck for accounting, data entry, and operations. This agent automates the extraction of key data points from unstructured text, turning messy documents into clean, structured data (like JSON) ready for your database or automation workflows.

## What

- Ingest raw text from emails, PDFs, or scanned documents
- Identify and extract specific structured entities (e.g., Vendor Name, Transaction Date, Total Amount)
- Format the extracted information into a strict, predictable JSON schema
- Validate the extracted data (e.g., ensuring dates follow a standard format and amounts are valid numbers)
- Handle edge cases like varying date formats, different currencies, or typos in the source text

## Integrations

| Platform | Purpose |
|----------|---------|
| AWS Textract / Google Document AI | OCR (Optical Character Recognition) to extract raw text from images or PDFs |
| Gmail / Outlook | Monitoring an inbox for incoming attachments (invoices/receipts) |
| Google Sheets / Airtable | Storing the extracted, structured data for reporting |
| QuickBooks / Xero | Pushing extracted financial data directly into accounting software |
| Slack / Discord | Sending notifications when a document is successfully processed |

## Escalation Path

| Trigger | Action |
|---------|--------|
| Missing required field (e.g., no date found) | Route document to a human queue for manual entry |
| Extraction confidence is low | Flag the document for human review |
| Multiple conflicting amounts found | Escalate to user to verify the correct total |
| Document text is completely illegible | Automatically reply to the sender requesting a clearer copy |
| Extracted date is in the future | Flag as a potential error or anomaly for immediate review |