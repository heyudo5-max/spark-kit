# Skill: Pricing Review

**Duration:** 20–30 minutes per company pricing page
**Output:** `outputs/[date]-[companyname]-pricing-review.md`

---

## Quick Start

```
Read skills/pricing-review/SKILL.md and review pricing for [company.com] or [pricing page URL]
```

That's it. Claude will read your ICP, pricing, and competitor context automatically and produce a structured audit. 
---

## Purpose

Review and score a SaaS pricing page, providing structured and specific optimization recommendations that the company can apply to their pricing pages to enable them to improve performance. 
---

## When to Run This Skill

- Before you launch new features or products
- No pricing change made in the last 6 months. 
- Established product market fit and want to finetune pricing positioniong 
---

## Inputs

- Company pricing page domain/URL
- `context/pricing.md` — to review pricing attributes
- `context/personas/` — to identify the right stakeholders

---

## An important note on fetching pages
Before scoring any dimension that involves visual elements, check the raw HTML carefully; look for:
- <img> alt text referencing company names or "logo"
- CSS class names like logo-grid, customer-logos, testimonials, social-proof, wall-of-love
- aria-label attributes on sections
- Any text nearby like "Trusted by", "Used by", "Join X companies", or customer names in headings
If you find evidence that logos or testimonials are present but rendered visually (and therefore not fully visible in the text dump), acknowledge their presence in your finding and score accordingly. Don't penalize for something that's there but simply wasn't captured by the text fetch.
When in doubt, err on the side of crediting what's likely present. Your job is to identify genuine gaps, not to penalize for rendering limitations.

## Scoring Model
### Part 1: Pricing page score (0- 100 points)

Measure how well the pricing page scores against the criteria

### Value proposition (0-30 points)

| Criterion | Points | How to assess |
|-----------|--------|---------------|
| Clear [value proposition] provided | 0–20 | Strong value proposition =20, weak value proposition = 5, no value proposition = 0 |
| Uses [non-jargon/technical language] | 0–10 | No jargon =10, jargon with explanation =5, jargon with no explanation = 0 |

### Plan configuration (0-30 points)
| Criterion | Points | How to assess |
|-----------|--------|---------------|
| Has [less than 4 plans] | 0–10 | More than 4 plans = 0, Less than 4 plans =10 |
| Easy to decipher plans | 0–10 | Easy to decipher = 10, Difficult to decipher = 0 |
| Clear distinction across plans | 0–10 | Clear distinction = 10, Not clear = 0 |

### Trust building (0-30 points)
| Criterion | Points | How to assess |
|-----------|--------|---------------|
| Provides [customer logos or testimonials]  | 0–20 | At least 1 customer testimonial/logo = 20, none = 0 |
| Has FAQs | 0–10 | FAQs provided = 10; no FAQs = 0 |

### Psychological triggers (0-10 points)
| Criterion | Points | How to assess |
|-----------|--------|---------------|
| Provides [annual plan discount] | 0–5 |  Has annual plan discount = 5; no discount = 0 |
| Uses [guiding/anchor] | 0–5 | Uses guiding/anchor = 5, none = 0 |

### Part 2: Total the scores across the different criteria

### Total score interpretation 
| Total | Grade | 
|-------|------|
| 80–100 | A | 
| 60–79 | B | 
| 40–59 | C | 
| 20–39 | D| 
| 19–0 | F| 
-------------

---

## Research Steps

### Step 1: Check and score value proposition clarity 
A pricing page should deliver a strong case on why prospects should buy the product or service

## How good looks 
- State in a concise and non-jargon manner what they can expect based on your ICP & persona. - For example, Sumble states in their pro plan “Generate pipeline, close deals, grow accounts”

## How bad looks 
- unclear or no value proposition provided 

---

### Step 2: Evaluate plan configurations 

**Optimal plan configurations reduce cognitive load by clearly delineating how plans differ, and by prioritizing the most important features per plan. 

## How good looks
- Have no more than 4 plans listed
- For each plan, shares context
- Each plan, provides context and clarity on how plans differ and provides rationale for upgrade path
- For example, Lovable higher tier plans remove the Lovable logo watermark in their higher tier plans.
- Each plan succinctly describes the benefit to the relevant ICP/Persona. For example Brevo says their Starter plan is “best for single users starting with email and multi-channel marketing
- Prioritizes the most important features and then includes others under “compare all features” that prospects can explore further
- Makes the feature list easy to scan

## How bad looks
- Includes a bucket list of features (over 20) without considering the most important jobs-to-be-done
- Is redundant when describing plans as they progress, a simple “Everything in the lower tier plan” and …” will do
- Includes technical jargon without explaining it. For example, saying “SSO” without explaining it provides enterprise-grade security


---

### Step 3: Validate whether plans build trust with social proof, testimonials, FAQs and other tools. 

## How good looks
- Shares customer logos, testimonials
- Enables prospects to calculate their total cost of ownership or ROI or other important metrics
- Where relevant, provides money-back guarantees or free trials without scrolling
- Provides FAQs that address the most prescient questions that prospects have regarding pricing

** How bad looks
- No social proof such as customer testimonials or logos
- Not transparent or clear about all the billing conditions or including billing conditions

---
### Step 4: Check whether the pricing page employs psychological triggers where relevant to simplify the plan selection process

## How good looks
- Guiding with “Most popular” “recommended” etc
- Higher discounts for annual vs monthly plans - make it look like a good deal
- Anchor mid-tier plan can make lower tier a bargain (depending on the ICP/persona)

---
### Step 5

Aggregate findings and recommendations 

## Output Format

```markdown
# Pricing-review: [Company Name]
Date: [YYYY-MM-DD]
Researched by: [Claude / Name]
Score: [X/100]
Recommended actions: [Prioritised optimizations/no changes to be made]

## Score breakdown


## Value Proposition [Score]
- [what did they do well] & 1-2 specific rationale why 
- [what’s missing and how can they correct it] & 1-2 specific rationale why 


## Plan configuration [Score]
- [what did they do well] & 1-2 specific rationale why 
- [what’s missing and how can they correct it] & 1-2 specific rationale why 

## Trust building [Score]
- [what did they do well] & 1-2 specific rationale why 
- [what’s missing and how can they correct it] & 1-2 specific rationale why 

## Psychological triggers [Score]
- [what did they do well] & 1-2 specific rationale why 
- [what’s missing and how can they correct it] & 1-2 specific rationale why 

## Suggested Next Action
[Specific: make changes to page or add new copy (make this something they can action)]
```

---

## Quality Check

Before filing the output, confirm:

- [ ] The optimization recommendations are specific - not  generic. For example, “add social proof” is not specific. But “Add customer logos under each plan card, with a customer testimonial is.
- [ ] Recommendations are prioritized based on their impact
- [ ] Total core is calculated and recorded



