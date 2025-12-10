---
title: Regulatory Filings
description: Writing SEC filings and regulatory compliance documents.
---

# Regulatory Filings

Regulatory filings communicate required information to government agencies and investors. These documents must meet strict formatting, content, and timing requirements while providing clear, accurate information.

## SEC Filing Types

### Periodic Reports

**Form 10-K (Annual Report):**
Comprehensive annual report including:

- Business description
- Risk factors
- Financial statements
- Management discussion and analysis (MD&A)

**Form 10-Q (Quarterly Report):**
Quarterly financial update including:

- Financial statements (unaudited)
- MD&A
- Controls assessment

**Form 8-K (Current Report):**
Material events reported promptly:

- Leadership changes
- Acquisitions/divestitures
- Earnings announcements
- Material agreements

### Registration Statements

**Form S-1:**
Initial public offering registration:

- Business description
- Financial information
- Use of proceeds
- Risk factors

**Form S-3/S-4:**
Shelf registration and business combinations.

### Proxy Materials

**Schedule 14A:**
Shareholder meeting materials:

- Proposals for vote
- Executive compensation
- Board nominees
- Auditor ratification

## 10-K Structure

### Required Sections

```markdown
# FORM 10-K

## PART I

### Item 1. Business
Description of the company's business operations,
products, services, and competitive environment.

### Item 1A. Risk Factors
Material risks that could affect the business,
financial condition, or results of operations.

### Item 1B. Unresolved Staff Comments
Any unresolved SEC staff comments on filings.

### Item 2. Properties
Description of principal physical properties.

### Item 3. Legal Proceedings
Pending material legal proceedings.

### Item 4. Mine Safety Disclosures
If applicable.

## PART II

### Item 5. Market Information
Trading market, stock performance, dividends.

### Item 6. [Reserved]

### Item 7. MD&A
Management's Discussion and Analysis of Financial
Condition and Results of Operations.

### Item 7A. Quantitative and Qualitative Disclosures
About Market Risk.

### Item 8. Financial Statements
Audited financial statements and notes.

### Item 9. Changes and Disagreements with Accountants

### Item 9A. Controls and Procedures
Assessment of disclosure controls and internal controls.

### Item 9B. Other Information

## PART III

### Item 10. Directors and Executive Officers
Background on board and management.

### Item 11. Executive Compensation
Detailed compensation information.

### Item 12. Security Ownership
Ownership by management and principal holders.

### Item 13. Related Party Transactions

### Item 14. Accountant Fees

## PART IV

### Item 15. Exhibits and Financial Statement Schedules

### Item 16. Form 10-K Summary (optional)
```

## Writing SEC Filings

### Risk Factors

Write clear, specific risk factors:

```markdown
# Too Generic
Our business is subject to various risks.

# Specific and Useful
**Concentration of Revenue Risk**

Approximately 35% of our revenue comes from our three largest
customers. The loss of any of these customers could materially
adversely affect our revenue and results of operations.
For the fiscal year ended December 31, 2024, Customer A
accounted for 15%, Customer B for 12%, and Customer C for 8%
of total revenue.
```

### MD&A Best Practices

Management's Discussion and Analysis should:

**Explain the numbers:**
```markdown
# Just Numbers
Revenue increased 15% to $500 million.

# With Explanation
Revenue increased 15% to $500 million, primarily driven by:
- $45 million increase in subscription revenue from new
  enterprise customers acquired during 2024
- $20 million increase from price adjustments effective
  January 2024
- $10 million increase from expansion within existing accounts
```

**Discuss trends:**
```markdown
## Trends Affecting Our Business

We expect the following trends to continue to affect our
business in the near term:

**Favorable Trends:**
- Growing adoption of cloud-based solutions in our target market
- Expansion of remote work driving demand for collaboration tools

**Challenges:**
- Increasing competition from well-funded competitors
- Rising costs of customer acquisition
- Potential economic slowdown affecting enterprise IT spending
```

**Address known uncertainties:**
```markdown
## Known Uncertainties

The extent of the impact of [specific event] on our business
is uncertain and will depend on future developments, including:
- Duration and severity of the event
- Governmental and regulatory responses
- Impact on customer purchasing behavior
- Effects on our supply chain and workforce

We cannot predict with certainty the impact on our future
results of operations, cash flows, or financial position.
```

### Forward-Looking Statements

Include safe harbor language:

```markdown
## Forward-Looking Statements

This report contains forward-looking statements within the
meaning of Section 27A of the Securities Act of 1933 and
Section 21E of the Securities Exchange Act of 1934. These
statements involve known and unknown risks, uncertainties,
and other factors that may cause our actual results,
performance, or achievements to be materially different
from any future results, performance, or achievements
expressed or implied by the forward-looking statements.

Forward-looking statements include, but are not limited to,
statements about:
- Our future financial performance
- Growth plans and strategies
- Market trends and opportunities
- New product introductions

These statements are based on management's current
expectations and assumptions. We undertake no obligation
to update any forward-looking statement except as required
by law.
```

## Plain English Requirements

### SEC Plain English Rule

The SEC requires prospectuses to use plain English:

**Principles:**
- Short sentences
- Active voice
- No legal jargon
- Definite, concrete language
- Tabular presentation of complex information

**Before Plain English:**
```
Notwithstanding the foregoing, in the event that the
undersigned shall fail to remit payment in accordance
with the terms herein specified, the party of the first
part shall be entitled to pursue all remedies available
at law or in equity.
```

**After Plain English:**
```
If you don't pay on time, we may take legal action to
collect what you owe.
```

### Readability Tips

| Avoid | Use |
|-------|-----|
| Utilize | Use |
| Prior to | Before |
| Subsequent to | After |
| In the event that | If |
| For the purpose of | To |
| With respect to | About |
| Pursuant to | Under |

## XBRL Tagging

### Inline XBRL Requirements

SEC filings require XBRL (eXtensible Business Reporting Language):

- Financial statement data tagged
- Standard taxonomy elements
- Custom extensions when needed
- Enables automated analysis

### Tagged Example

```xml
<ix:nonFraction contextRef="FY2024"
                name="us-gaap:Revenues"
                unitRef="USD"
                decimals="-6">
  500000000
</ix:nonFraction>
```

## Form 8-K Current Reports

### Timing Requirements

| Event Type | Filing Deadline |
|------------|-----------------|
| Most items | 4 business days |
| Earnings release | When released |
| Trading suspension | Immediately |

### Common 8-K Items

```markdown
# FORM 8-K

## Item 1.01 Entry into a Material Definitive Agreement

On January 15, 2024, the Company entered into a Credit
Agreement with [Bank] providing for a $100 million
revolving credit facility. The Credit Agreement matures
on January 15, 2029 and bears interest at SOFR plus
150 basis points.

A copy of the Credit Agreement is filed as Exhibit 10.1
to this Current Report on Form 8-K.

## Item 5.02 Departure of Directors or Certain Officers

On January 18, 2024, the Board of Directors appointed
Jane Smith as Chief Financial Officer, effective
February 1, 2024. Ms. Smith, age 52, previously served
as CFO of [Company] from 2018 to 2023.

Ms. Smith will receive an annual base salary of $500,000
and will be eligible for an annual bonus with a target
of 75% of base salary. Ms. Smith will also receive a
sign-on equity grant valued at approximately $1,000,000.

## Item 9.01 Financial Statements and Exhibits

(d) Exhibits

10.1  Credit Agreement dated January 15, 2024
104   Cover Page Interactive Data File
```

## Filing Process

### Preparation Timeline

```markdown
## 10-K Filing Timeline (Large Accelerated Filer)

Fiscal Year End: December 31
Filing Deadline: 60 days (February 28)

Week 1-4 (January):
- Finalize financial statements
- Obtain audit opinion
- Draft disclosure sections
- Management review

Week 5-6:
- Internal review and sign-offs
- Audit committee review
- Board approval

Week 7-8:
- XBRL tagging
- Edgar formatting
- Final review
- File with SEC
```

### Quality Checklist

```markdown
## Pre-Filing Checklist

□ All financial data reconciled to source
□ Period-over-period comparisons accurate
□ Forward-looking statement legend included
□ Risk factors updated
□ Material contracts filed as exhibits
□ Signatures page complete
□ XBRL tagging validated
□ Edgar formatting tested
□ Legal review complete
□ Officer certifications signed
```

## Summary

Regulatory filings require:

- Understanding of SEC requirements
- Clear, accurate disclosure
- Plain English principles
- Proper formatting and tagging
- Rigorous review processes

Well-prepared filings build investor confidence and demonstrate regulatory compliance.
