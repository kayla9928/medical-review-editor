# Trigger Evaluation Cases

## Positive Cases

| Prompt | Expected | Reason |
|---|---|---|
| Reconstruct this Chinese medical-review subsection in English, preserving its causal order and citations. | Trigger: `author-preserving-translation` | Medical translation with reasoning-skeleton protection |
| Give me four medically equivalent phrasings of this sentence; do not optimize for detectors. | Trigger: `expression-candidates` | Ordinary SCI wording candidates remain MRE work |
| Using this approved outline and evidence summary, draft the next Discussion paragraph. | Trigger: `direct-draft` | Existing review project with permitted inputs |
| Audit this figure legend against the algorithm and Section 4. | Trigger: `visual-table-alignment` | Figure and prose consistency |
| Does the authorized guideline support calling this treatment first-line? | Trigger with targeted verification | Claim calibration within a permitted source boundary |
| Design this review's structured abstract fields, but do not draft English. | Trigger: `component-design` | Independent component design |
| Draft an unstructured narrative-review abstract from this approved manuscript. | Trigger: `component-draft` | Authorized component drafting |
| Draft a medical-review paragraph from approved logic without original prose. | Trigger: `direct-draft` | Full language realization still applies |
| Align the contribution logic of this review's Introduction and Conclusion using all supplied chapters. | Trigger: `structure-design` | Authorized cross-section contribution design |
| Design a running title under a supplied character limit, but do not give me English candidates yet. | Trigger: `component-design` | Hard-limit short fields remain independent submission components |
| Check this author-assembled paragraph only for medical drift and assembly defects. | Trigger: permission-gated `post-selection-minimal-audit` | Explicit minimal audit authorization |
| Compare this local passage with our full-project reasoning map for terminology and claim-strength consistency. | Trigger with scope-aware expansion | Project map is available and relevant |
| Help respond to reviewer comment 2 about the review framework. | Trigger: `reviewer-response` | Reviewer-response content |
| Adapt these authorized sections to the selected journal requirements. | Trigger: `journal-adaptation` | Journal-specific medical review editing |

## Negative Cases

| Prompt | Expected | Reason |
|---|---|---|
| Reduce the AI-writing score of this iThenticate-highlighted passage and generate A/B/C authorship variants. | Do not trigger MRE; use academic-humanizer only when available, in scope, and authorized; otherwise explain separate handling | Detector and authorship work is excluded |
| Find recent papers on gastric varices. | Do not trigger by itself | Literature discovery belongs elsewhere |
| Explain portal hypertension to me. | Do not trigger | Ordinary medical education |
| What treatment should I give this patient? | Do not trigger | Clinical advice is outside manuscript editing |
| Update our durable project decision log. | Do not trigger | Project-memory maintenance belongs elsewhere |
| Generate an AI disclosure statement. | Do not trigger by itself | Generic disclosure belongs elsewhere |
| Find all literature and write a new medical review from scratch. | Do not trigger by itself | Evidence-set creation must precede editing |

## Boundary Cases

| Prompt | Expected | Reason |
|---|---|---|
| This paragraph is tested-final and accurate. Archive it; no audit. | Trigger only to exit without editing | Tested-final authority blocks automatic review |
| Here is my selected paragraph. | Suggest minimal audit and wait; do not run it | Selection alone is not audit permission |
| Read my whole manuscript before answering this small wording question. | Trigger but retain local scope unless full reading is authorized and needed | Scope-aware reading boundary |
| Give three alternative medical phrasings with identical meaning. | Trigger MRE only | Candidate count alone does not imply authorship work |
| I confirmed the running-title design. Give me three candidates within 45 characters, preserving the protected terminology. | Trigger: `component-draft`; validate exact counts and surface any infeasible combination | Explicit component-specific drafting authorization under a hard limit |
| I rejected colon-form running titles; revise the candidates without colons. | Continue the current component iteration; do not universalize the rejection beyond its scope | Author rejection changes the local form constraint, not the Skill's global style |
| Make this non-medical Results section sound less AI-generated. | Do not trigger MRE; optional academic-humanizer collaboration depends on availability, its scope, and authorization | Non-medical authorship work has no MRE dependency |
| Translate this medical paragraph; no other Skills are installed. | Trigger MRE translation and complete it independently | Core editing does not require collaborators |
| Translate this passage and handle a separate authorship task; academic-humanizer is unavailable. | Complete only the independently authorized medical portion and explain separate handling for the rest | Mixed requests do not create a dependency or expand MRE scope |
| Medical editing only; do not call academic-humanizer even though it is installed. | Trigger the applicable MRE mode and obey the collaboration restriction | Availability is not permission or a reason to transfer ordinary editing |

## Additional Layering Boundaries

| Prompt | Expected | Reason |
|---|---|---|
| Draft the approved narrative-review abstract; no target journal has been selected. | Use component defaults and language realization; no automatic journal lookup or extra approval gate | Missing venue does not block ordinary content drafting |
| The mechanism is already explained; this paragraph should discuss treatment objectives. | Inherit the necessary premise and draft the requested function | Understanding is not authorization to retell |
| Only remove the opening sentence's dependence on our withdrawn phenotype; retain the clinical pathway. | Local direct revision with claim calibration | No terminology ban or broad restructuring |
