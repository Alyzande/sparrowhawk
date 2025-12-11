# Project Pitch: глаз перепелятника (Sparrowhawk)

## Executive Summary

глаз перепелятника ("sparrowhawk's eye") is an open-source, automated intelligence platform that detects sanctions-evading tankers in real-time by identifying deliberate AIS disappearance patterns. Unlike existing tools, it provides investigation-ready leads with complete forensic vessel histories.

## The Investigative Problem

### Current Workflow (Manual & Reactive)
\`\`\`
Analyst monitors ports → Spots suspicious vessel → Searches history → 
Requests satellite imagery → Traces ownership → Days/Weeks per lead
\`\`\`

### Our Automated Workflow (Proactive)
\`\`\`
System scans 15,000+ tankers → Pre-filters 500 high-risk targets → 
Flags hiding vessels in real-time → Provides complete dossier → 
Minutes per investigation-ready lead
\`\`\`

## Core Innovation: Two-Tier Detection

### 1. Smart Pre-Filtering
We don't monitor everything. First, identify vessels with **shadow fleet characteristics**:
- **Age**: 15+ years (too old for legitimate operators)
- **Flag**: Cameroon, Comoros, Togo (high-risk registries)
- **Ownership**: Shell companies in Dubai/Hong Kong
- **Insurance**: Unverified or "ghost" insurance

**Result**: 15,000+ tankers → 500-1,000 high-probability targets

### 2. Behavioral Detection (The "Smoking Gun")
Monitor these targets for the **primary shadow fleet tactic**: deliberate AIS disabling.

\`\`\`
ALERT LOGIC:
High-risk vessel → Leaves sanctioned port → 
AIS disappears in open ocean (>12 hours) → 
System raises alert with coordinates → 
Provides forensic vessel history
\`\`\`

## The Investigator's Dashboard

### Real-Time Interface
\`\`\`
��� ACTIVE ALERTS - Updated Hourly
─────────────────────────────
��� HIGH RISK (92/100)
• SKY GEM (IMO: 9456789)
• 36h gap | Last seen: Mediterranean STS zone
• 22-year-old tanker | Cameroonian flag
• [CLICK FOR COMPLETE DOSSIER]
\`\`\`

### One-Click Forensic Dossier
- **Ownership chain** with shell company mapping
- **Behavior history** (past disappearances, patterns)
- **Network associations** (vessels met during gaps)
- **Satellite tasking coordinates** (exact time/location)

## Technical Differentiators

| | Existing Tools (Windward, MarineTraffic) | **Our Tool** |
|---|---|---|
| **Focus** | All maritime traffic | **Exclusively shadow fleet behavior** |
| **Alerting** | Manual monitoring | **Automated real-time alerts** |
| **Intelligence** | Raw AIS data | **Context-rich leads with forensic history** |
| **Cost** | \$0-\$100,000+ annually | **\$0 (open-source)** |
| **Methodology** | Generic analytics | **Specialized shadow fleet detection** |
| **Deployment** | Web apps/expensive platforms | **Containerized - runs anywhere** |

## Practical Benefits

### 1. Time Savings
- **Before**: 40 hours/week manual monitoring
- **After**: **5 minutes/day** reviewing auto-prioritized alerts
- **Gain**: Analysts focus on **investigation** not **monitoring**

### 2. Lead Quality
Every alert includes:
- Pre-vetted target (already matches shadow fleet profile)
- Actionable coordinates (exact last known position)
- Historical context (past behavior patterns)
- Network intelligence (associated vessels)

### 3. Sample Investigation Flow
**Monday, 9:00 AM**: Analyst logs in
- Dashboard shows: 3 new alerts overnight
- **Priority 1**: Tanker disappeared 28h ago in Med STS zone
- **Click alert**: Complete dossier shows 4 previous disappearances

**9:15 AM**: Investigation begins
- Satellite tasking using provided coordinates
- Ownership research following shell company trail
- Network analysis of associated vessels

**9:45 AM**: Lead ready for publication
- **Result**: **45 minutes** from alert to investigation-ready lead

## Technical Implementation

### Zero-Cost Architecture
\`\`\`
DATA SOURCES (All Free):
• Global Fishing Watch AIS archive
• Equasis vessel registry
• Public port/zone databases

INFRASTRUCTURE:
• Docker containers (runs on any laptop)
• Local storage (external HDD for AIS data)
• No cloud costs required

DELIVERABLE:
• Single container package
• Web dashboard + API
• Complete documentation
\`\`\`

### Development Roadmap
- **Phase 1 (4 weeks)**: Core detection engine
- **Phase 2 (2 weeks)**: Web dashboard interface
- **Phase 3 (2 weeks)**: Testing & calibration
- **Phase 4 (ongoing)**: Integration & enhancements

## Why This Is Uniquely Valuable

1. **Sanctions Evasion Gap**: Current tools miss deliberate AIS manipulation
2. **Resource Constraint**: Newsrooms can't afford \$100k commercial licenses
3. **Investigative Need**: Real-time leads beat after-the-fact analysis
4. **Open-Source Advantage**: Customizable, transparent, free for all journalists

## Request

**30-day pilot program** to:
1. Deliver working containerized tool
2. Demonstrate detection of active shadow fleet vessels
3. Train team on investigative workflows
4. Provide weekly intelligence reports

**Cost**: \$0 (open-source)
**Time commitment**: 2 hours/week for testing
**Potential impact**: Transform shadow fleet investigation from reactive to proactive

---

## Next Step

**30-minute briefing** to:
1. Show detection system in action
2. Demonstrate investigation workflow
3. Discuss integration with current processes

**глаз перепелятника** - Tracking the untrackable
