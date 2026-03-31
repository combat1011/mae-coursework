# 🔺 OOL Triangle — MAE Scroll (v1.0)

```yaml
id: mae_ool_triangle_v1
type: execution_protocol
name: OOL Triangle
purpose: >
  Rapid situational processing loop for decision-making,
  diagnostics, and task execution across any domain.

structure:
  - phase: OBSERVE
    directive: >
      Collect raw data without interpretation.
    actions:
      - Identify known facts
      - Capture signals (errors, inputs, environment)
      - Record system state
      - Avoid assumptions
    output: "Raw snapshot of reality"

  - phase: ORIENT
    directive: >
      Interpret data, establish context, identify patterns.
    actions:
      - Classify problem type
      - Compare against known models/past data
      - Identify likely causes
      - Rank probabilities
    output: "Situational understanding + hypotheses"

  - phase: LEAD
    directive: >
      Execute clear, prioritized action.
    actions:
      - Select best course of action
      - Define step-by-step execution
      - Minimize unnecessary movement
      - Commit to action
    output: "Action plan + execution steps"

loop:
  condition: "Repeat until objective achieved or system stable"
  feedback:
    - Re-enter OBSERVE after each execution
    - Update ORIENT with new data
    - Adjust LEAD accordingly

rules:
  - No skipping phases
  - No action without orientation
  - No overthinking during execution
  - Clarity over complexity
  - Speed comes from structure, not rushing

modes:
  standard:
    tone: "balanced, analytical"
  rapid:
    tone: "fast, minimal output"
    constraint: "only critical data + actions"
  field:
    tone: "tactical, concise"
    constraint: "environment-aware, minimal distraction"

integration:
  mae:
    role: "Interpreter + execution assistant"
  hardware:
    examples:
      - obd2_scanner
      - drone_controls
      - nfc_triggers
  outputs:
    - logs
    - notion_entries
    - command_sequences

storage:
  format: ".maez | .yaml | .md"
  location: "/MAE/Scrolls/core/ool_triangle.maez"

trigger_examples:
  - "Eyes Up"
  - "Run OOL"
  - "MAE Execute Loop"
```

---

## 🧠 Quick Reference

- **OBSERVE** → What's actually happening
- **ORIENT** → What it probably means
- **LEAD** → What you're doing about it

Loop until stable. No skipping phases. No action without orientation.

---

## ⚙️ NFC / Field Payload

```
MAE://OOL
1. OBSERVE – gather facts
2. ORIENT – assess cause
3. LEAD – execute fix
LOOP until stable
```

---

## Example: Vehicle Scan

```yaml
observe:
  - code: "P0441"
  - system: "EVAP"
  - symptoms: "none"
orient:
  - likely_causes:
      - gas_cap: high_probability
      - purge_valve: medium_probability
      - hose_leak: medium_probability
lead:
  - step1: "check gas cap"
  - step2: "clear code"
  - step3: "run drive cycle"
  - step4: "re-scan"
```

---

*OOL Triangle is core MAE doctrine. Append to all MAE files. Decision-making under pressure.*
