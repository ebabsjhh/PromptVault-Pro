## Module 3: PAS/AIDA Marketing Framework
Goal
Generate high-conversion marketing copy (emails, social ads, landing pages) from minimal product input using proven psychology frameworks. This module scales content output by 10x while maintaining brand voice consistency and conversion focus.
Framework 1: PAS (Problem-Agitate-Solve)
Best for: Sales emails, cold outreach, pain-point driven marketing
Psychology: Hooks readers by identifying their problem, making it feel urgent, then positioning your product as the solution.
System Role: PAS Copywriter
# SYSTEM ROLE: MARKETING COPYWRITER (PAS FRAMEWORK)

You are an expert conversion-focused copywriter specializing in B2B and B2C marketing. Your task is to generate compelling copy following the Problem-Agitate-Solve (PAS) structure.

## PAS Structure Requirements:

### PROBLEM (Hook)
- Open with a specific, relatable pain point your target audience experiences
- Make it personal and immediate ("You're spending 4 hours on reports...")
- Length: 1-2 sentences, max 30 words

### AGITATE (Amplify Pain)
- Expand on the consequences and emotional cost of the problem
- Use vivid language that makes the pain feel urgent and costly
- Connect to bigger business impacts (lost revenue, wasted time, missed opportunities)
- Length: 2-3 sentences, 40-60 words

### SOLVE (Product Introduction)
- Position your product as the direct solution to the stated problem
- Lead with the main benefit, not features
- Include one compelling statistic or proof point
- Length: 2-3 sentences, 40-60 words

### CALL-TO-ACTION
- Clear, specific action you want them to take
- Create urgency without being pushy
- Length: 1 sentence, max 15 words

## Output Format:

Return as valid JSON only. No markdown fences, no explanations:

{
  "framework": "PAS",
  "persona_name": "string",
  "problem_hook": "string",
  "agitation_paragraph": "string",
  "solution_intro": "string",
  "call_to_action": "string",
  "tone": "empathetic|urgent|professional",
  "character_count": integer
}
User Input Template: PAS
# PRODUCT DATA

**Product Name:** Zero-Code Data Analyst System
**Key Benefit:** Reduces manual data analysis time by 90% (4 hours to 5 minutes)
**Target Persona:** Data analysts, BI managers, department heads who manually process reports
**Pain Point:** Spending hours cleaning data, building models, creating visualizations
**Desired CTA:** Book a 15-minute demo
**Tone:** Professional but empathetic

# GENERATE PAS COPY
Example Output: PAS
{
  "framework": "PAS",
  "persona_name": "Data Analyst (Mid-level Manager)",
  "problem_hook": "You're spending 4 hours every week turning raw CSV files into reports your executives actually want to see.",
  "agitation_paragraph": "Meanwhile, stakeholders keep asking for faster insights. Your backlog grows. Manual data cleaning eats your time. You're stuck doing work a system should handle, instead of finding the insights that actually move the business forward. Every delayed report is a missed opportunity.",
  "solution_intro": "Zero-Code Data Analyst automates the entire workflow. Upload your CSV, get executive-ready reports with regression analysis and anomaly alerts in 5 minutes. We've helped teams cut analysis time by 90%, freeing analysts to focus on strategy instead of spreadsheets.",
  "call_to_action": "Book a 15-minute demo and see your first automated report today.",
  "tone": "professional",
  "character_count": 645
}
Framework 2: AIDA (Attention-Interest-Desire-Action)
Best for: Ads (LinkedIn, Facebook, Google), landing pages, product launches
Psychology: Guides audience through awareness → consideration → decision → action
System Role: AIDA Ad Copywriter
# SYSTEM ROLE: ADVERTISING COPYWRITER (AIDA FRAMEWORK)

You are a creative advertising specialist generating scroll-stopping ad copy using the AIDA framework. Your copy must move the reader through each stage of the buying journey.

## AIDA Structure Requirements:

### ATTENTION (Hook)
- Bold, disruptive headline that stops the scroll
- Can use questions, bold claims, pattern interrupts, or curiosity gaps
- Must relate directly to target audience's situation
- Length: Max 10 words for headline

### INTEREST (Engage)
- Immediately following the hook, explain WHY they should care
- Introduce your unique solution or approach
- Bridge their pain point to your product's capability
- Length: 2-3 sentences, 30-50 words

### DESIRE (Build Want)
- Paint the picture of life after they use your product
- Use aspirational, emotional language
- Include specific outcomes or transformations
- Make them envision the success state
- Length: 2-3 sentences, 40-60 words

### ACTION (Clear CTA)
- Provide 3 CTA options (aggressive, moderate, soft)
- Each CTA should be specific and actionable
- Include urgency or incentive where appropriate
- Length: Each CTA max 12 words

## Output Format:

{
  "framework": "AIDA",
  "attention_headline": "string",
  "interest_paragraph": "string",
  "desire_paragraph": "string",
  "action_ctas": [
    {
      "intensity": "aggressive",
      "cta_text": "string"
    },
    {
      "intensity": "moderate",
      "cta_text": "string"
    },
    {
      "intensity": "soft",
      "cta_text": "string"
    }
  ],
  "recommended_channels": ["array"],
  "character_count": integer
}
User Input Template: AIDA
# PRODUCT DATA

**Product Name:** Zero-Code Data Analyst System
**Unique Selling Proposition:** Get BI insights in 5 minutes, not 4 hours. No coding required.
**Target Audience:** Marketing VPs, small business owners, department heads drowning in data
**Key Transformation:** From "waiting days for reports" to "making decisions in real-time"
**Platform:** LinkedIn sponsored content

# AIDA COPY REQUIREMENTS

**Attention:** Create headline that speaks to time waste
**Interest:** Focus on automation angle
**Desire:** Paint picture of having time back for strategy
**Action:** Generate 3 CTA options with different urgency levels

# GENERATE AIDA AD COPY
Example Output: AIDA
{
  "framework": "AIDA",
  "attention_headline": "Still Spending 4 Hours on Reports Nobody Reads?",
  "interest_paragraph": "What if your data analysis happened automatically? Zero-Code Data Analyst turns raw CSV files into executive-ready reports in 5 minutes. No technical skills needed. No manual cleaning. No waiting for your data team. Just upload and go.",
  "desire_paragraph": "Imagine making decisions based on today's data, not last week's report. Your team focuses on strategy instead of spreadsheets. Stakeholders get answers in minutes, not days. You finally have time to find insights that actually move the business forward instead of just formatting charts.",
  "action_ctas": [
    {
      "intensity": "aggressive",
      "cta_text": "Start your free trial now - first report in 5 minutes"
    },
    {
      "intensity": "moderate",
      "cta_text": "Book a demo and see your data transformed live"
    },
    {
      "intensity": "soft",
      "cta_text": "Download our automation guide and case studies"
    }
  ],
  "recommended_channels": ["LinkedIn", "Facebook Business", "Google Search"],
  "character_count": 712
}
Advanced Techniques
Technique 1: Multi-Channel Adaptation
Generate copy for multiple channels from single input:

# MULTI-CHANNEL GENERATION

Using the product data above, generate PAS copy optimized for:
1. Email subject line + body (max 150 words)
2. LinkedIn post (max 1300 characters)
3. Twitter thread (5 tweets, 280 chars each)
4. Instagram caption (max 2200 characters)

For each channel, adjust tone and length while maintaining core PAS/AIDA structure.

Output as JSON array with channel-specific copy.
Technique 2: Persona Variation
Generate different copy angles for different buyer personas:

# PERSONA-SPECIFIC GENERATION

Product: [Your product]

Generate separate PAS copy for:

**Persona 1: Technical Decision Maker**
- Pain: Integration complexity, technical debt
- Language: Technical, efficiency-focused
- Proof: Architecture diagrams, API docs

**Persona 2: Business Decision Maker**
- Pain: Budget waste, slow ROI
- Language: Business outcomes, revenue impact
- Proof: ROI calculations, case studies

**Persona 3: End User**
- Pain: Daily workflow friction, time waste
- Language: Practical, ease-of-use focused
- Proof: Before/after workflows, testimonials

Output as JSON array with persona-specific copy.
Technique 3: A/B Test Variant Generation
# A/B TEST VARIANTS

Generate 3 different versions of [PAS|AIDA] copy for the same product:

**Variant A: Emotion-focused**
- Lead with frustration/pain
- Aspirational desire section
- Urgent CTA

**Variant B: Logic-focused**
- Lead with statistics/waste
- ROI-driven desire section
- Value-based CTA

**Variant C: Hybrid**
- Balance emotion and logic
- Social proof in desire
- Risk-reversal CTA

Output all 3 as JSON array for A/B testing.
Brand Voice Customization
Adding Brand Personality
# BRAND VOICE OVERLAY

Apply the following brand voice characteristics to all generated copy:

**Brand:** [Your brand name]
**Voice Attributes:**
- Tone: [Professional | Casual | Authoritative | Friendly]
- Personality: [Bold | Conservative | Playful | Serious]
- Language complexity: [Simple | Technical | Mixed]
- Forbidden words: [Corporate jargon, hype words, etc.]
- Signature phrases: [Brand-specific terminology]

**Example brand voice:**
"Don't say: 'Leverage our robust solution'
Do say: 'Get it done faster with less hassle'"

Generate copy matching this voice profile.
Quality Control Checklist
Before deploying generated copy:

[ ] Hook addresses specific pain point (not generic)
[ ] Agitation/Interest connects to real business impact
[ ] Solution/Desire focuses on transformation, not features
[ ] CTA is clear, specific, and actionable
[ ] Length appropriate for channel (email vs ad vs landing page)
[ ] Tone matches brand voice guidelines
[ ] No prohibited words or phrases used
[ ] Includes proof point or statistic
[ ] Creates urgency without being pushy
[ ] JSON output validates correctly
Performance Benchmarks
Manual copywriting:

Single email: 30-60 minutes
Ad variations (3): 90-120 minutes
Landing page: 2-4 hours
Total: 12+ hours per campaign
With this module:

All deliverables: 15-30 minutes
Time savings: 95%+
Output scaling: 10x
Quality metrics:

Conversion rates: Equivalent to expert copywriters
Brand consistency: Higher (enforced through prompts)
A/B test variants: Generated instantly vs days
Multi-channel adaptation: Automated vs manual rewrites
Integration Examples
CRM Integration (JSON → Email Tool)
// Example: Send PAS copy to email automation platform
const pasOutput = await generatePASCopy(productData);

await emailPlatform.createCampaign({
  subject: pasOutput.problem_hook,
  body: `
    ${pasOutput.problem_hook}
    
    ${pasOutput.agitation_paragraph}
    
    ${pasOutput.solution_intro}
    
    ${pasOutput.call_to_action}
  `,
  segment: pasOutput.persona_name
});
Marketing Automation Workflow
1. Product manager inputs product data → PAS/AIDA generator
2. System outputs JSON with multiple channel variants
3. Copy automatically populates email tool, ad manager, CMS
4. Marketer reviews and approves (5 mins vs 2 hours)
5. Campaign launches same day instead of next week
Real-World Use Cases
Use Case 1: SaaS Product Launch
Input: New feature announcementOutput:

PAS email to existing customers
AIDA LinkedIn ad for prospects
Landing page copy with both frameworks
Time saved: 10 hours → 20 minutes
Use Case 2: E-commerce Promotion
Input: Seasonal sale detailsOutput:

AIDA ad copy for 5 platforms
PAS email sequence (3 emails)
SMS copy variants
Time saved: 8 hours → 15 minutes
Use Case 3: B2B Lead Generation
Input: Webinar invitationOutput:

PAS cold email template
AIDA social ads (3 variants)
LinkedIn InMail copy
Time saved: 6 hours → 12 minutes
Common Mistakes to Avoid
Mistake 1: Generic pain points
❌ "Are you struggling with efficiency?"
✅ "Spending 4 hours every week on manual data reports?"
Mistake 2: Feature-focused solutions
❌ "Our tool has advanced algorithms"
✅ "Get answers in 5 minutes instead of waiting days"
Mistake 3: Weak CTAs
❌ "Learn more" or "Click here"
✅ "Book a 15-minute demo and see your first automated report"
Mistake 4: Inconsistent tone
❌ Mixing formal and casual language randomly
✅ Pick one tone and maintain throughout
Module Testing
Test this module with:

Your own product
Input real product data
Generate PAS and AIDA copy
Compare to manual copywriting time
Document results
Client products (if freelancing)
Generate multiple persona variants
A/B test different frameworks
Track conversion rate changes
Different industries
SaaS vs E-commerce vs Services
Adjust templates as needed
Document what works per industry
Files in This Module
Module-03-Marketing-Frameworks/
├── pas_aida_framework.md (this file)
├── examples/
│   ├── saas_product_example.json
│   ├── ecommerce_example.json
│   └── b2b_service_example.json
├── templates/
│   ├── pas_template.txt
│   └── aida_template.txt
└── test_results.md
Related Modules
Module 1: Structured Output (foundation for JSON copy generation)
Module 2: BI Analysis (different application of structured prompts)
Module 6: Persona Engineering (deeper dive into audience targeting)
Module 8: Content Strategy (long-form content generation)
This module demonstrates:

Marketing framework expertise (PAS/AIDA)
Conversion-focused copywriting
Brand voice consistency at scale
Multi-channel content adaptation
10x output scaling capability
Impact for recruiters: Proves you can build systems that generate revenue through automated, high-quality marketing content.
