# GenAI Security Platform Evaluation
## Architecture Team Presentation

**Date**: January 2026  
**Purpose**: Vendor selection for GenAI security platform  
**Evaluation Framework**: 29 security & governance requirements  
**Vendors Evaluated**: 6 platforms

---

## PROBLEM STATEMENT

### Why We Need GenAI Security

**Business Risk**:
- **Data Leakage**: Employees paste sensitive data (PII, PHI, IP, trade secrets) into AI tools
- **Compliance Violations**: AI usage not aligned with SOC2, ISO27001, GDPR, HIPAA, EU AI Act requirements
- **Shadow AI**: Unapproved AI tools used without IT/Security oversight
- **Reputational Damage**: AI-generated outputs causing brand/legal issues

**Technical Gap**:
- **AI-Specific Threats**: Traditional security tools (firewalls, DLP, EDR) don't detect prompt injection, jailbreaks, model poisoning
- **No Visibility**: Can't see what AI tools are being used or what data flows through them
- **Multi-Cloud Complexity**: AI workloads span AWS, Azure, GCP, SaaS - need unified control
- **Agentic AI Risk**: Autonomous agents with tool access create blast radius concerns

**Use Cases Requiring Protection**:
1. **BuyAgent-B**: SaaS AI tools (ChatGPT Teams, Microsoft Copilot, Google Gemini, Salesforce Einstein, ServiceNow)
2. **BuildAgent**: Custom AI applications and agents we develop (using OpenAI, Anthropic, AWS Bedrock, Azure OpenAI)
3. **Shadow AI**: Personal AI tools employees use without approval

### What We're Evaluating

**Objective**: Select a GenAI security platform to:
- Discover all AI usage (sanctioned and shadow)
- Enforce DLP policies on AI prompts and responses
- Detect and block AI-specific threats (prompt injection, jailbreaks, toxic outputs)
- Provide governance and compliance controls
- Enable secure AI innovation

**Methodology**:
- **29 Requirements**: 21 security + 8 governance
- **Scoring**: 0-10 per requirement (290 max points)
- **Pass Criteria**: 0 Must-Have gaps (27 of 29 requirements)
- **Sources**: Vendor documentation only (no sales pitches)

---

## VENDOR EVALUATION SUMMARY

### Production-Ready Vendors (0 Must-Have Gaps)

| Rank | Vendor | Score | % | Tier | Deployment | Cost |
|------|--------|-------|---|------|------------|------|
| **1** | **Noma Security** | 248/290 | **85.5%** | **Tier 1** | SaaS \| Agentless \| Customer VPC | $$$ |
| **2** | **Palo Alto AIRS** | 231/290 | **79.7%** | **Tier 2** | SaaS or On-Prem \| Inline+API \| Hybrid | $$$$ |
| **3** | **Aim Security** | 225/290 | **77.6%** | **Tier 2** | SaaS \| Inline \| Customer | $$ |

### Non-Production Vendors (8-13 Must-Have Gaps)

| Rank | Vendor | Score | % | Tier | Category | Gaps |
|------|--------|-------|---|------|----------|------|
| 4 | Dataiku | 160/290 | 55.2% | Fail | Dev Platform | 8 |
| 5 | MuleSoft | 141/290 | 48.6% | Fail | Integration Platform | 10 |
| 6 | Boomi | 118/290 | 40.7% | Fail | Integration Platform | 13 |

**Key Finding**: Only 3 vendors are GenAI security platforms. The other 3 are development/integration platforms incorrectly evaluated against security requirements.

---

## VENDOR PROFILES

### 1. NOMA SECURITY (Tier 1 - 85.5%)

**Company**: Tel Aviv, Israel / San Francisco, USA | Founded 2022 | Series A funding

**What It Is**: 
Pure-play GenAI security platform with agentless deployment. Discovers and protects AI usage across SaaS tools, custom apps, and shadow AI through native cloud API integrations. No software to deploy.

**Deployment Model**:
- **Control**: SaaS (noma.security cloud)
- **Runtime**: Agentless + API-based telemetry
- **Data**: Customer VPC (prompts stay local, metadata only to SaaS)

**Pros**:
- ✅ Highest security score (85.5%)
- ✅ Zero infrastructure deployment (agentless)
- ✅ Best data sovereignty (AI traffic never leaves customer VPC)
- ✅ 80+ native integrations (AWS, Azure, GCP, Databricks, Salesforce, etc.)
- ✅ Best agent security (10/10)
- ✅ Best discovery & visibility (10/10)
- ✅ Best observability (10/10)
- ✅ Fast deployment (1-2 weeks)

**Cons**:
- ❌ No on-prem control plane (SaaS only)
- ❌ Not suitable for air-gapped environments
- ❌ Inline enforcement is optional, not primary

**Best For**: Most organizations, cloud-first companies, data sovereignty requirements, teams wanting zero ops burden

---

### 2. PALO ALTO NETWORKS PRISMA AIRS (Tier 2 - 79.7%)

**Company**: Santa Clara, California, USA | Founded 2005 (AIRS launched April 2025) | Public company (NASDAQ: PANW)

**What It Is**: 
Enterprise security vendor extending into AI security. Provides dual-mode enforcement: inline AI Runtime Firewall (network intercept) and API SDK (application intercept). Integrates with existing Prisma Cloud and VM-Series deployments.

**Deployment Model**:
- **Control**: SaaS (Strata) OR On-Prem (Panorama) - customer choice
- **Runtime**: Inline Firewall + API SDK (can use both)
- **Data**: Hybrid (Network mode in VPC, API mode sends to cloud)

**Pros**:
- ✅ Only vendor with on-prem control plane (Panorama)
- ✅ Best inline firewall enforcement (10/10 - only vendor)
- ✅ Air-gapped support (Panorama + Network Intercept)
- ✅ Kubernetes-native (namespace-level traffic steering)
- ✅ Prisma Cloud / VM-Series integration (existing customers)
- ✅ Best model security (9/10)
- ✅ Best supply chain security (9/10)
- ✅ Dual enforcement modes (inline + API)

**Cons**:
- ❌ Requires infrastructure deployment (not agentless)
- ❌ API Intercept mode sends prompts to cloud (data residency concern)
- ❌ Lower overall score than Noma (79.7% vs 85.5%)
- ❌ Agent security lower than Noma (8/10 vs 10/10)
- ❌ Longer deployment (4-6 weeks)

**Best For**: Air-gapped environments, existing Palo Alto customers, Kubernetes workloads, organizations needing inline network firewall

---

### 3. AIM SECURITY (Tier 2 - 77.6%)

**Company**: Tel Aviv, Israel / New York, USA | Founded 2022 | Series A ($32M, June 2024)

**What It Is**: 
Pure-play GenAI security platform with inline enforcement. Focused on DLP, guardrails, and compliance for enterprise AI deployments. Proven customer base in finance sector.

**Deployment Model**:
- **Control**: SaaS (aim.security)
- **Runtime**: Inline enforcement
- **Data**: Customer environment (prompts stay local)

**Pros**:
- ✅ Most affordable production-ready option ($$)
- ✅ Zero Must-Have gaps (production-ready)
- ✅ Strong DLP & guardrails (9/10)
- ✅ Proven in finance sector (Finance of America customer)
- ✅ Good shadow AI detection (9/10)
- ✅ Lower cost than Noma/PANW

**Cons**:
- ❌ Lower overall score (77.6% vs Noma 85.5%, PANW 79.7%)
- ❌ Limited public architecture documentation
- ❌ No on-prem control option
- ❌ Agent security lower than Noma (8/10 vs 10/10)
- ❌ Tool security lower than Noma (8/10 vs 9/10)

**Best For**: Budget-conscious organizations, finance/healthcare sectors, cost-sensitive enterprises needing production-ready security

---

### 4. DATAIKU (Fail - 55.2%, 8 Gaps)

**Company**: New York, USA / Paris, France | Founded 2013 | Unicorn ($4.6B valuation)

**What It Is**: 
AI development and governance platform, NOT a security platform. Provides LLM Mesh gateway for development-time controls: cost tracking, PII detection during dev, quality evaluation, LLM registry. Designed for data scientists building models.

**Why It Failed**:
- ❌ Wrong product category (development platform, not security)
- ❌ 8 Must-Have gaps (critical security missing)
- ❌ Weak runtime security (46.2% on security requirements)
- ❌ No inline enforcement (4/10)
- ❌ No agent security (5/10)

**Pros**:
- ✅ Best governance among all vendors (73.5%)
- ✅ Strong EU AI Act compliance features
- ✅ Good cost tracking and attribution

**Recommendation**: **Do NOT use as primary security platform.** Possible use: Pair with Noma/PANW (Dataiku for dev governance, Noma/PANW for runtime security).

---

### 5. MULESOFT (Fail - 48.6%, 10 Gaps)

**Company**: San Francisco, USA (Salesforce subsidiary) | Founded 2006 | Acquired by Salesforce 2018

**What It Is**: 
API integration and agent orchestration platform, NOT a security platform. Agent Fabric and Flex Gateway enable agent connectivity via MCP/A2A protocols. Focused on integration, not security.

**Why It Failed**:
- ❌ Wrong product category (integration platform, not security)
- ❌ 10 Must-Have gaps
- ❌ Weak security (52.2% on security requirements)
- ❌ No inline enforcement (4/10)
- ❌ No guardrails (4/10)
- ❌ No model security (2/10)

**Pros**:
- ✅ Good multi-cloud support (8/10)
- ✅ Cloud-agnostic architecture

**Recommendation**: **Do NOT use as primary security platform.** Use for agent orchestration only, pair with Noma/PANW for security.

---

### 6. BOOMI (Fail - 40.7%, 13 Gaps)

**Company**: Chesterbrook, Pennsylvania, USA | Founded 2000 | Private equity owned

**What It Is**: 
Low-code integration and agent development platform, NOT a security platform. Agentstudio enables business users to build agents without coding. Focus on agent development, not security.

**Why It Failed**:
- ❌ Wrong product category (dev platform, not security)
- ❌ 13 Must-Have gaps (most of any vendor)
- ❌ Weakest security (36.2% on security requirements - lowest)
- ❌ Lowest overall score (40.7%)
- ❌ No inline enforcement (3/10)
- ❌ No guardrails (3/10)
- ❌ No agent security (3/10)

**Recommendation**: **Do NOT use as primary security platform.** Use for low-code agent development only, pair with Noma/PANW for security.

---

## ARCHITECTURE RECOMMENDATIONS

### Recommended Vendor by Scenario

| Scenario | Recommended Vendor | Rationale |
|----------|-------------------|-----------|
| **General Enterprise** | **Noma (85.5%)** | Highest security, agentless, data sovereignty, fast deployment |
| **Air-Gapped / Defense** | **PANW (79.7%)** | Only vendor with on-prem control (Panorama), full air-gap support |
| **Existing Palo Alto Customer** | **PANW (79.7%)** | Consolidation with Prisma Cloud/VM-Series, unified management |
| **Budget-Constrained** | **Aim (77.6%)** | Most affordable production-ready option, proven in finance |
| **Kubernetes Workloads** | **PANW (79.7%)** | Best K8s-native support, namespace-level traffic steering |
| **Strict Data Sovereignty** | **Noma (85.5%)** | AI traffic never leaves VPC (metadata only to SaaS) |
| **Zero Ops Burden** | **Noma (85.5%)** | Only agentless option, no infrastructure to deploy |

### Multi-Vendor Strategy (Optional)

**Development + Production Split**:
- **Development Governance**: Dataiku (LLM Mesh, cost tracking, EU AI Act compliance)
- **Production Security**: Noma or PANW (runtime threat detection, DLP, guardrails)

**Rationale**: Dataiku excels at dev governance (73.5%) but weak at runtime security (46.2%). Combine for best of both worlds in large enterprises with complex AI pipelines.

---

## DEPLOYMENT COMPARISON

### Control Plane (Management)

| Vendor | SaaS Control | On-Prem Control | Air-Gapped Support |
|--------|--------------|-----------------|-------------------|
| **Noma** | ✅ Only option | ❌ No | ❌ No |
| **PANW** | ✅ Strata | ✅ **Panorama** | ✅ **Yes** |
| **Aim** | ✅ Only option | ❌ No | ❌ No |

**Decision Point**: If you need on-prem control or air-gapped → **PANW is the only production-ready option**

---

### Runtime Plane (Enforcement)

| Vendor | Agentless | Inline Firewall | Ops Burden |
|--------|-----------|-----------------|------------|
| **Noma** | ✅ **Primary** | Optional | **Lowest** |
| **PANW** | ❌ No | ✅ **Best (10/10)** | Medium |
| **Aim** | ❌ No | ✅ Yes | Medium |

**Decision Points**: 
- If you need zero deployment → **Noma is the only agentless option**
- If you need inline firewall → **PANW has best inline enforcement (10/10)**

---

### Data Plane (Where AI Traffic Flows)

| Vendor | 100% Customer VPC | Prompts to Vendor Cloud? |
|--------|-------------------|-------------------------|
| **Noma** | ✅ **(metadata only to SaaS)** | ❌ **No** |
| **PANW** | ⚠️ Network mode only | ⚠️ API mode yes |
| **Aim** | ✅ Likely | ❌ Likely no |

**Decision Point**: If you need strict data sovereignty (no prompts to cloud) → **Noma** (best) or **PANW Network Intercept mode** (good)

---

## NEXT STEPS

### Week 1-2: Architecture Review & Requirements
1. Review this evaluation with Architecture, Security, Compliance, Engineering teams
2. Finalize deployment requirements:
   - SaaS control acceptable or on-prem required?
   - Agentless preferred or inline firewall required?
   - Data residency requirements (prompts stay in VPC?)
   - Air-gapped environment?
3. Align on budget and timeline

### Week 3: Vendor Selection
Based on deployment requirements, select:
- **SaaS + Agentless** → Noma
- **On-Prem Control** → PANW
- **Budget-Constrained** → Aim
- **Existing PANW Customer** → PANW

### Week 4-8: POC/Pilot
1. Engage selected vendor for architecture review
2. POC deployment in non-production
3. Test: DLP policies, threat detection, SIEM integration, performance
4. Architecture sign-off

### Week 9-12: Production Deployment
1. Phase 1: High-risk AI usage (PII/PHI/IP)
2. Phase 2: All SaaS AI tools
3. Phase 3: Custom AI applications
4. Ongoing: Monitoring, policy tuning

---

## EVALUATION ARTIFACTS PROVIDED

**Scorecards**:
- `AIS_V9_Scorecard.csv` (16 columns) - Complete requirement comparison with deployment models
- `AIS_V9_Vendor_Summary.csv` (6 columns) - High-level rankings

**Guides**:
- `AIS_V9_Guide.md` - How to use scorecards and decision filters
- `AIS_V9_Architecture_Team_Presentation.md` (this document)

**References** (optional deep-dive):
- `AIS_V8_Evidence_Reference.csv` - Detailed evidence and source URLs
- `AIS_V6_Deployment_Architecture_Comparison.md` - Deep-dive deployment analysis

---

## QUESTIONS FOR DISCUSSION

1. **Control Plane**: Can we accept SaaS control, or is on-prem required?
2. **Runtime**: Do we prefer agentless (Noma) or inline firewall (PANW/Aim)?
3. **Data Residency**: Can prompts/responses leave our VPC for analysis?
4. **Air-Gapped**: Do we have environments requiring full air-gap support?
5. **Existing Investment**: Are we using Palo Alto Networks (Prisma Cloud, VM-Series)?
6. **Kubernetes**: Do we have K8s-native AI workloads needing pod-level security?
7. **Timeline**: Fast deployment (1-2 weeks) or acceptable for 4-6 weeks?
8. **Budget**: Premium (Noma/PANW) or cost-sensitive (Aim)?

---

## FINAL RECOMMENDATION

**For Most Organizations**: **Noma Security (85.5%, Tier 1)**
- Highest security coverage, zero deployment, best data sovereignty

**For Air-Gapped Environments**: **Palo Alto AIRS (79.7%, Tier 2)**
- Only production-ready vendor with on-prem control and air-gap support

**For Existing Palo Alto Customers**: **Palo Alto AIRS (79.7%, Tier 2)**
- Consolidation with existing infrastructure, unified management

**For Budget-Conscious**: **Aim Security (77.6%, Tier 2)**
- Most affordable production-ready option, proven in finance

**Do NOT Use**: Dataiku, MuleSoft, Boomi
- Wrong product category, too many gaps, not designed for runtime security

---

## DOCUMENTATION REFERENCES

All scores based exclusively on official vendor documentation. No hands-on testing, no sales materials.

### Noma Security Documentation
**Primary Sources**:
1. https://noma.security/ - Platform overview
2. https://noma.security/platform/ - Core capabilities
3. https://noma.security/solutions/ai-agent-security/ - Agent security features
4. https://noma.security/solutions/ai-governance-and-compliance/ - Governance capabilities

**Key Features Referenced**:
- Agentless deployment and API integrations
- Continuous discovery and monitoring
- Real-time guardrails and policy enforcement
- Agent security: tool registry, blast radius, MCP monitoring
- DLP: sensitive data detection and blocking
- Supply chain: AIBOM with provenance tracking
- Observability: full telemetry, SIEM integration, audit trails
- Governance: compliance automation, versioning, immutable logs

---

### Palo Alto Networks AIRS Documentation
**Primary Sources**:
1. https://docs.paloaltonetworks.com/ai-runtime-security - Product documentation
2. https://pan.dev/airs/ - API reference and developer docs
3. https://pan.dev/prisma-airs/api/airuntimesecurity/usecases/ - Use cases and API details
4. https://www.paloaltonetworks.com/prisma/prisma-ai-runtime-security - Product page
5. https://docs.paloaltonetworks.com/ai-runtime-security/administration/prisma-airs-overview - Administration guide
6. https://docs.paloaltonetworks.com/ai-runtime-security/administration/deploy-ai-instances-in-public-clouds-as-a-software - Deployment guides
7. https://docs.paloaltonetworks.com/ai-runtime-security/activation-and-onboarding/ai-runtime-security-api-intercept-overview - API Intercept
8. https://docs.paloaltonetworks.com/ai-runtime-security/ai-model-security/ - Model Security component
9. https://docs.paloaltonetworks.com/whats-new/new-features/august-2025/prisma-airs-aug-2025 - Release notes
10. https://www.paloaltonetworks.com/blog/2025/11/prisma-airs-integrates-azure-ai-foundry/ - Microsoft integration

**Key Features Referenced**:
- Dual enforcement: AI Runtime Firewall (network) + API SDK (application)
- Control planes: Strata Cloud Manager (SaaS) and Panorama (on-prem)
- Cloud deployments: AWS, Azure, GCP via Terraform
- Kubernetes support: namespace-level traffic steering
- AI Model Security: vulnerability scanning, backdoor detection
- SSL/TLS decryption for AI traffic inspection
- Unified logging via Strata Logging Service
- PII detection and masking with offset precision

---

### Aim Security Documentation
**Primary Sources**:
1. https://www.aim.security/ - Platform overview
2. https://aws.amazon.com/marketplace/pp/prodview-ndg445rb6axc2 - AWS Marketplace listing
3. https://www.businesswire.com/news/home/20240617016656/en/ - Funding announcement (June 2024)

**Key Features Referenced**:
- Inline enforcement platform
- Bidirectional DLP for prompts and responses
- Guardrails: prompt injection, toxic content, malicious code detection
- Shadow AI discovery across sanctioned/unsanctioned tools
- Enterprise compliance features
- Finance sector deployment (Finance of America customer)
- Coverage: SaaS apps, enterprise chats, custom developments

**Documentation Limitation**: Aim has less detailed public documentation than Noma/PANW. Specific architecture details (agentless vs inline, control plane options) require vendor engagement.

---

### Dataiku Documentation
**Primary Sources**:
1. https://www.dataiku.com/product/key-capabilities/genai-and-agents/ - GenAI capabilities
2. https://www.dataiku.com/product/key-capabilities/llm-mesh/ - LLM Mesh gateway
3. https://www.dataiku.com/product/key-capabilities/ai-governance/ - Governance features
4. https://doc.dataiku.com/dss/latest/generative-ai/ - Technical documentation
5. https://blog.dataiku.com/ - Blog posts on AI governance and EU AI Act

**Key Features Referenced**:
- LLM Mesh gateway (customer-deployed)
- Safe Guard: PII detection, toxicity, prompt injection (dev-time)
- Cost Guard: usage tracking and attribution
- Quality Guard: LLM evaluation metrics
- Governance: EU AI Act compliance, AIBOM generation, risk workflows
- GenAI Registry and Agent Hub
- Approval workflows and staged rollout
- Multi-environment support (SaaS or self-hosted)

**Category**: Development and governance platform, NOT runtime security

---

### MuleSoft Documentation
**Primary Sources**:
1. https://www.mulesoft.com/platform/ai/ - AI platform overview
2. https://www.mulesoft.com/platform/ai/ai-agent-governance - Agent governance
3. https://docs.mulesoft.com/mule-gateway/ - Mule Gateway documentation
4. https://blogs.mulesoft.com/ - Technical blogs on AI gateway
5. https://www.salesforce.com/news/ - MCP and A2A announcements

**Key Features Referenced**:
- Agent Fabric for agent orchestration
- Flex Gateway and Mule Gateway (customer-deployed)
- MCP (Model Context Protocol) and A2A (Agent-to-Agent) support
- API management and lifecycle
- Agent-to-agent activity monitoring
- Custom policies for masking and toxicity (basic)
- Cloud-agnostic architecture
- Anypoint Platform (SaaS control)

**Category**: Integration and orchestration platform, NOT security

---

### Boomi Documentation
**Primary Sources**:
1. https://boomi.com/platform/agentstudio/ - Agentstudio overview
2. https://boomi.com/ - Platform features
3. https://developer.boomi.com/docs/GettingStarted/Boomi_AI_overview - Developer documentation
4. https://aimagazine.com/ - Third-party coverage of Boomi governance (for context)

**Key Features Referenced**:
- Agentstudio: low-code agent development
- Agent Control Tower: centralized monitoring
- Built-in guardrails and rule setting (basic)
- Activity logs and audit trails
- Agent runtime (Boomi-hosted or customer-hosted)
- Tool management and API key controls
- Integration platform capabilities
- DataDetective Early Access (in development)

**Category**: Integration and low-code development platform, NOT security

---

## DOCUMENTATION METHODOLOGY

**Scoring Approach**:
1. All scores based on capabilities documented in official vendor documentation
2. No hands-on testing conducted
3. No vendor sales materials or marketing claims used
4. Evidence quotes extracted directly from documentation
5. Source URLs preserved for verification

**Limitations**:
- **Aim Security**: Limited public architecture documentation; some features inferred from product positioning
- **Dataiku/MuleSoft/Boomi**: Evaluated against GenAI security requirements despite being dev/integration platforms (category mismatch)

**Verification**:
- All source URLs available in `AIS_V8_Evidence_Reference.csv`
- Every score includes: Score (0-10), Evidence (documentation quote), Source (URL)

---

**End of Presentation**
