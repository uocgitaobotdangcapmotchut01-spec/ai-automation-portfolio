# WEBSITE SPECIFICATION

- Task: TASK-005 (Portfolio Website Foundation & Information Architecture)
- Context version: CTX-002
- Status: Revision 2, submitted for Human review. The Human's decisions of 2026-10-05 (#2 to #11) are applied. Final approval of TASK-005 is a Human decision and is not claimed here.
- Type: Planning and specification only. No code, build, or prototype exists.
- Authority: The Human is the final decision-maker. Items marked "decision #N" were specified by the Human for this revision. They are not recorded in `DECISIONS.md`. Everything else is a PROPOSAL.
- Sources: `PROJECT.md` (goal, audience, roles), `DECISIONS.md` (DEC-006, DEC-008), and the TASK-005 brief from the Human.

## 1. Executive summary

A small, evidence-first portfolio site for one person, written in the first person, who builds practical AI automation systems. It is a personal builder portfolio, not an agency site. One homepage with seven sections, plus one reusable case-study page per system. It will be built later with React, Vite, plain CSS with variables, and data-driven content. Dark, restrained, fast, accessible.

Core proposals:

1. Position the site on explained architecture, not on promises. Each system is shown as a readable flow (Trigger → Processing → AI → Actions → Output) with the decisions behind it.
2. Show only real, demonstrable systems. The site has as many systems as exist, with no filler.
3. Every claim has evidence or is left out. Prototype and production are labeled differently.
4. Homepage: Hero, Selected Systems, Approach, Stack, About, Contact, Footer. Case studies are separate pages.
5. Primary CTA "View selected systems". Secondary CTA "Get in touch". No booking, pricing, forms, or newsletter at this stage.
6. Static site, English only. No backend, analytics, or cookies in the first version.
7. The main risk is content, not design. The site is only as strong as the documented systems behind it (see section 16).

Implementing this specification is a separate, later task (section 14).

## 2. Positioning

### 2.1 Core positioning (proposal)

A personal builder of practical AI automation systems, documented as architecture (decision #3). Not an agency, a studio, or a "we", and not a guru: one person who designs workflows that connect tools, process data, and use AI where it helps, and who explains how each one works and where its limits are.

### 2.2 The 10-second message

Headline, specified by the Human (decision #2):

> I build practical AI automation systems.

Supporting line, specified by the Human (decision #2):

> I design workflows that connect tools, process data, and use AI where it helps. Each system is documented from trigger to output.

First-person voice is kept. The headline describes what is built. It must not be extended into a claim about revenue, expertise, client results, or performance.

In 10 seconds a visitor should be able to answer: what does this person build, and where can I see it?

### 2.3 Target audience

From `PROJECT.md`.

- Primary: potential automation clients, small businesses, founders, people evaluating the owner's AI automation skills.
- Secondary: technical people evaluating the projects and implementation ability.

Design implication: primary readers skim and care about the problem solved. Secondary readers open the case study for architecture and decisions. The homepage serves the first group. Case studies serve both.

### 2.4 Value proposition (each statement must stay true)

1. Systems are explained end to end, from trigger to output, in plain language.
2. Technical decisions and trade-offs are documented, not hidden.
3. Scope is stated honestly: what is a prototype, what runs for real, what is not built.

No promise about time saved, cost, revenue, or accuracy unless it is measured and shown (section 13).

### 2.5 Tone

Plain, specific, calm, first person singular (decision #2). Short sentences. Name the tool or the step instead of describing it abstractly. Say "prototype" when it is a prototype.

Avoid: "cutting-edge", "revolutionary", "supercharge", "10x", "seamless", "leverage", "solutions", "AI agency", "end-to-end AI transformation". Avoid any implied authority (awards, years of experience, client counts) unless it is real and shown.

### 2.6 Technology claim register

The site may name a technology only if the Human confirms the owner actually used it in a shown system and evidence exists (a workflow screenshot, a sanitized export, a run record, or a repository). Status of each technology listed in the task brief:

| Technology | Evidence required before it appears on the site | Status |
|---|---|---|
| Make.com | A shown scenario (sanitized screenshot or export) | Human to confirm per system |
| APIs | The named API and the calls it serves in a shown system | Human to confirm per system |
| Webhooks | The trigger or endpoint described in a shown system (no live URLs) | Human to confirm per system |
| AI models | The model actually used, its role, and its input and output shape | Human to confirm per system |
| Google Sheets | A shown system that reads or writes it | Human to confirm per system |
| Discord | A shown system that posts to it | Human to confirm per system |
| GitHub | This repository (public) | Evidenced in this repository |

Any other technology is added only by the same rule. Of this list, this repository evidences only GitHub.

Evidence-first, per system (decision #4): a technology appears on the site only when there is evidence for a specific shown system. The site does not carry a technology stack to look more professional. Evidence means a workflow, an export, a run record, a repository, or another suitable artifact. Make.com, APIs, webhooks, AI models, Google Sheets, Discord, and any other technology stay "Human to confirm" until that evidence exists for the system that uses them.

## 3. Information architecture

Site map (version 1):

- `/` Home
- `/systems/<slug>` One case-study page per featured system
- A not-found page

Out of scope for version 1: blog, pricing, services pages, login, dashboards, forms, newsletter, analytics, and a language switcher. Version 1 is English only (decision #7).

Homepage order: Hero, Selected Systems, Approach, Stack, About, Contact, Footer.

Section anchors: `#systems`, `#approach`, `#stack`, `#about`, `#contact`. The Hero is the top of the page.

Each section has one h2 (the Hero has the h1) and one idea. The order follows the visitor's questions: What do you build? Show me. How do you think? With what? Who are you? How do I reach you?

## 4. Homepage section specification

### Hero

- Purpose: deliver the 10-second message and the two CTAs.
- Content: h1 (headline), one supporting line, primary CTA, secondary CTA, and an optional compact strip Trigger → Processing → AI → Actions → Output, labeled "How my systems are structured".
- Rules: no stock photo, no illustration, no fake dashboard, no animation. The strip is a static concept diagram, not data. It sits below the CTAs and is one line high on desktop. Headline and CTAs must be visible without scrolling on a 375×667 viewport.

### Selected Systems

- Purpose: prove capability with real systems.
- Content: a one-line section intro and a grid of project cards (section 5).
- Rules: show only systems that pass the readiness rule (13.5). Show as many cards as there are qualifying systems: one qualifying system means one card, two means two. The site is not required to reach three or four (decision #5). Never use placeholders, "coming soon" cards, fake projects, fake metrics, or systems that have not run. When the status is uncertain, use `prototype`. The Human sets the order (default: strongest evidence first).

### Approach

- Purpose: show how the owner thinks, so a client can judge the working style.
- Content: 3 to 5 short principles, each a heading plus one or two sentences. Each links to the system where it is visible.
- Draft principles (copy to be confirmed by the Human): start from the manual process, not the tool; design trigger to output first; validate data early; use AI only where fixed rules are not enough, and keep its output checkable; document decisions and limits.
- Rules: no numbered "proprietary framework", no process buzzwords, no promises.

### Stack

- Purpose: show the tools used, factually.
- Content: tools grouped by role (Automation, Integrations, AI, Data and messaging, Code and version control). Each item is a text name with a required "used in" link to the system that evidences it. GitHub links to this repository.
- Rules: only technologies that pass the register (2.6), each backed by evidence for a specific shown system (decision #4). If few technologies qualify, the list stays short and is never filled out for appearance. No logos, no skill bars, no percentages, no "years of experience".

### About

- Purpose: say who is behind the work, briefly and truthfully.
- Content: short, honest, first person, using the Human's personal name when real content is prepared (decision #3). Four points only: building AI automation systems, workflow architecture, practical business problems, and the fact that the systems are where the work should be judged. Personal builder identity, not an agency.
- Rules: do not add age, school, address, phone number, clients, years of experience, credentials, awards, or social accounts, unless the Human later decides to publish them. No invented experience. No photo by default.

### Contact

- Purpose: give one realistic way to start a conversation.
- Content: one sentence on what to send (the manual process they want to automate), and the contact channels (decision #6): GitHub, and an email link only if the Human accepts a public email address. If the Human does not accept a public email, GitHub is the only channel.
- Rules: no contact form in version 1 (it needs a backend, spam handling, and privacy handling). No calendar booking, chat widget, or availability badge. No response-time promise unless it is true and kept.

### Footer

- Purpose: orientation and closure.
- Content: name, year, link to the GitHub repository, back-to-top link.
- Rules: no duplicate marketing, no logos, no "built with" line until the site is built, no tracking notice unless tracking is added.

## 5. Project card specification

Fields:

| Field | Rule |
|---|---|
| name | Plain system name, 6 words or fewer. Rendered as an h3 and used as the card's link text. |
| problem | One sentence, 140 characters or fewer. Starts from the manual pain. No metrics. |
| workflow | Compact workflow of 3 to 5 steps in the order Trigger → Processing → AI → Actions → Output. Each step 4 words or fewer. The AI step is omitted if no AI is used. |
| tools | 2 to 6 tool names as text. All must pass the register (2.6). |
| status | `prototype`, `working-demo`, or `production` (definitions in 13.4). Shown as a text badge. |
| link | To `/systems/<slug>`, with the link text "Read case study". |

There are no fields for metrics, results, clients, testimonials, or logos.

Structure and behavior:

- The card is an `<article>`. The name is an h3 containing the link. The whole card may be clickable by extending the link's hit area. One tab stop per card.
- Hover and focus change the border color to the accent. No movement, shadow, or scaling. The focus ring follows section 11.
- Text is never cut off with an ellipsis. Cards in a row grow to the tallest.
- The compact workflow is an ordered list. It is shown inline with `→` separators on wide cards and as a stacked list on narrow ones (section 10).

Data shape (structure only; the values are placeholders, not real content):

```js
{
  slug: "example-system",
  name: "Example System",
  problem: "One-sentence manual problem.",
  workflow: [
    { stage: "trigger", label: "Form submitted" },
    { stage: "processing", label: "Clean and validate" },
    { stage: "ai", label: "Classify" },
    { stage: "actions", label: "Update records" },
    { stage: "output", label: "Notify team" }
  ],
  tools: ["Tool A", "Tool B"],
  status: "prototype"
}
```

Stage ids are `trigger`, `processing`, `ai`, `actions`, `output`.

## 6. Case-study specification

Page header: system name, status badge, tools list, "Last updated" date, and a one-sentence scope statement ("What this is, and what it is not").

Sections, in this order (each is an h2):

| Section | Content | Evidence to show | Must NOT be fabricated |
|---|---|---|---|
| 1. Problem | Who does what by hand, what goes wrong, what the constraints are | Description of the original process; a sanitized sample input | Invented clients, pain, or volumes |
| 2. Architecture | The whole system at a glance: workflow diagram (section 7), components, data stores | Sanitized diagram or screenshot of the real scenario | Components that do not exist |
| 3. Trigger | What starts it: form, schedule, webhook, or manual; payload shape; validation | Sample payload with fake data; sanitized trigger configuration | Live URLs, tokens, real user data |
| 4. Processing | The deterministic steps: transformations, mapping, branching, error handling | Sanitized module views or a precise description; before/after with synthetic data | Steps that are not implemented |
| 5. AI reasoning | Where and why AI is used: the model actually used, the task, input and output shape, sanitized prompt structure, how output is checked, failure handling, limits | Prompt and output samples with synthetic data; a description of the checks | Accuracy rates, "autonomous" claims, a model that was not used |
| 6. Actions | What the system does in other tools: writes, messages, notifications; duplicate handling if any | Sanitized screenshots of the resulting records or messages (fake data) | Actions that never ran |
| 7. Output | What the person receives: a sheet row, a message, a report | Real output using synthetic or sanitized data | Polished mockups presented as real output |
| 8. Business value | What changes, for whom: which manual step is removed, who benefits, what still needs a human | If measured: method, sample size, and date | Any number not measured from real runs; revenue; estimated savings presented as results |
| 9. Technical decisions | Why it is built this way: the decision, alternatives considered, trade-off, known limitations, what would change next | Notes, issue history, an approach that was tried and replaced | Rewriting history to hide real limits |

End of page: "Known limitations" (required), an explanation of the status label, previous and next system (only when there is more than one), and the CTA "Get in touch".

Evidence rules:

- Each section has either a real artifact or an honest statement that none exists (for example, "No test run recorded yet").
- Screenshots and exports are sanitized before publishing (DEC-008): no webhook URLs, tokens, API keys, connection identifiers, real names, emails, or client data. Use placeholders or synthetic data.
- Metrics appear only when measured from real runs, with date, method, and sample size. Otherwise they are omitted.
- Run evidence (execution history, test output) is dated, and the date is shown.

Pre-publish checklist for each case study: (1) every tool passes the register; (2) the status label matches reality; (3) no secret or identifier is visible, including inside zoomed screenshots; (4) every number has a source; (5) the limitations section is written; (6) the Human has approved it.

## 7. Workflow visualization standard

Pattern: Trigger → Processing → AI → Actions → Output.

- At most five stages at the top level. Omit a stage that does not exist. Never show an empty stage. If the system has no AI, the AI stage is absent and nothing is said about AI.
- A node has a stage label (small, uppercase, muted, monospace), a title of 4 words or fewer, and, in the case-study variant only, one line of detail and at most 3 sub-items.
- Connectors are 1px lines with small arrowheads in the strong border color: horizontal on desktop, vertical on mobile.
- Color: neutral nodes (surface and border). The AI node uses the accent border and label, so a reader sees at once where AI is used. No other accent use inside diagrams. No color-coded rainbow stages.
- Branching: show at most one level, as a labeled sub-list inside a node (for example "If score is at or above the threshold / Otherwise"), never as crossing lines. If the real flow is more complex, show the simplified five-stage view and link to a full sanitized screenshot of the real scenario.
- Two variants: compact (project cards: step labels only) and full (case-study Architecture: node diagram).
- Implementation: an ordered list of nodes in HTML and CSS, or inline SVG with real text. Never an image only. Screenshots are supporting evidence, not the only representation.
- No animation, except an optional single fade-in on load that is disabled under reduced motion. Icons are optional; if used, simple line icons only. No brand logos.
- Accessibility: ordered-list semantics, visible stage labels, and the list itself is the text equivalent of the diagram.

## 8. Navigation and CTA

- Header on all pages: site name (links to `/`) and navigation Systems, Approach, Stack, About, Contact, pointing to `/#systems`, `/#approach`, `/#stack`, `/#about`, `/#contact`. A sticky header is optional. If it is sticky, it must not cover focused elements.
- Case-study pages: "← All systems" at the top (to `/#systems`), and previous/next system links at the bottom (only when more than one system exists).
- A "Skip to main content" link is first in the tab order.
- Anchors: lowercase ids, `scroll-margin-top` equal to the header height. Smooth scrolling only when reduced motion is not requested.
- Primary CTA (decision #6): "View selected systems" (to `#systems`), in the Hero. Secondary CTA: "Get in touch" (to `#contact`). At the end of a case study: "Get in touch" (primary) and "All systems" (secondary).
- The contact channels are GitHub and, only if the Human accepts a public email address, a `mailto:` link (decision #6).
- CTAs not allowed in version 1 (decision #6): "Book a call", "Free audit", "Hire me", "Start your project", pricing, newsletter signup, chat widget, an availability badge, or anything that implies a service or process that does not exist.

## 9. Visual system

Principles: dark-first, restrained, quiet, readable. Content over decoration.

Tokens, as CSS custom properties. The accent `#6FCFB4` and the token set are specified by the Human (decision #11) and are kept unless a clear error is found. The contrast ratios were calculated with the WCAG formula on 2026-10-05 and must be re-verified during implementation.

| Token | Value | Use | Contrast |
|---|---|---|---|
| `--color-bg` | `#0B0B0C` | Page background (near-black) | n/a |
| `--color-surface` | `#131315` | Cards and nodes | n/a |
| `--color-text` | `#EDEDEA` | Primary text (off-white) | 16.77:1 on bg, 15.82:1 on surface |
| `--color-text-muted` | `#A3A3AB` | Secondary text | 7.85:1 on bg, 7.41:1 on surface |
| `--color-accent` | `#6FCFB4` | Links, primary button, AI node, focus ring | 10.55:1 on bg, 9.95:1 on surface |
| `--color-on-accent` | `#0B0B0C` | Text on an accent background | 10.55:1 |
| `--color-border` | `#2A2A2E` | Decorative borders (cards, dividers) | 1.38:1, decorative only |
| `--color-border-strong` | `#6B6B72` | Borders of interactive controls | 3.72:1 on bg, 3.51:1 on surface |

- Typography: system font stacks, no web fonts in version 1. Sans for text, monospace for stage labels and code. Base size about 17px, line height 1.6. h1 `clamp(2rem, 5vw, 3.25rem)`, h2 `clamp(1.5rem, 3vw, 2rem)`, h3 1.125 to 1.25rem. Prose line length 70 characters or fewer.
- Spacing: a variable scale of 4, 8, 12, 16, 24, 32, 48, 72, and 112px. Section padding `clamp(4rem, 10vw, 7rem)`. Container max width 1080px, side padding 1.25rem on mobile and 2rem on desktop.
- Borders and radius: 1px solid borders. Radius 10px for cards and nodes, 8px for buttons, fully rounded for badges. No shadows.
- Motion: none by default. Color and border transitions of 150ms or less. No parallax, scroll-triggered animation, typing effects, or looping animation.
- Buttons and links: primary button is an accent background with on-accent text. Secondary button is transparent with the strong border and primary text. Links are accent colored and underlined.

Explicitly rejected: neon gradients; glassmorphism and blur panels; particle or animated backgrounds; fake dashboard visuals (invented charts, KPIs, graphs); excessive animation; fake logos (including "trusted by" rows and third-party marks that imply endorsement); fake testimonials; fake metrics or counters; stock photography; 3D graphics.

## 10. Responsive behavior

Breakpoints (proposal): mobile below 640px, tablet 640 to 1023px, desktop 1024px and above. Design mobile-first. Test at 320, 375, 768, 1024, and 1440px. No horizontal page scroll at 320px. Layout reflows at 200% zoom.

| Area | Mobile | Tablet | Desktop |
|---|---|---|---|
| Header | Site name plus a menu button (`aria-expanded`, `aria-controls`). The list opens inline and closes on link activation and on Escape. | Inline navigation if it fits, otherwise as mobile | Inline navigation |
| Hero | One column. Headline and CTAs visible without scrolling at 375×667. CTAs stack at full width. | One column, CTAs side by side | One column, text block up to about 720px wide |
| Project cards | 1 column, full width | 2 columns | 2 columns (3 only if there are 3 or more systems and each card stays at least 320px wide) |
| Compact workflow (cards) | Vertical list, one step per line, down-pointing connectors | Inline with `→` if it fits, otherwise vertical | Inline with `→` |
| Full workflow diagram | Vertical stack, connectors pointing down | Horizontal if each node stays at least 140px wide, otherwise vertical | Horizontal row |
| Stack | 1 to 2 columns of grouped lists | 2 to 3 columns | 3 columns |
| Case-study page | Single column, prose 70 characters or fewer | Same | Single column prose, diagram may use the full container |

Rules:

- Diagram text is never smaller than 14px. Never shrink a diagram until it is unreadable.
- Prefer reflowing a diagram to vertical. If a sanitized screenshot is wider than the viewport, show it fit-to-width and link to the full-size image. Fallback only: a scrollable container with `tabindex="0"`, `role="region"`, an `aria-label`, and a visible scroll cue.
- Project cards never depend on hover for content.
- Touch targets are at least 44×44px with spacing between them.

## 11. Accessibility

Target (proposal): WCAG 2.2 level AA.

- Semantic HTML: `header`, `nav` (with an accessible name), `main`, `section` with headings, `article` for cards, `footer`. Lists for lists, links for navigation, buttons for actions.
- Headings: one h1 per page, h2 for sections, h3 for cards and subsections. No skipped levels. Headings describe their content.
- Keyboard: everything is reachable and operable by keyboard. Tab order matches visual order. No keyboard traps. A skip link. Escape closes the mobile menu. On a route change, focus moves to the new page's h1 and the document title updates.
- Focus: every interactive element shows a visible focus indicator, a 2px solid accent outline with a 2px offset. Never remove an outline without a replacement. A sticky header must not hide the focused element.
- Contrast: text at least 4.5:1 (large text at least 3:1). Boundaries of interactive controls and focus indicators at least 3:1 (use `--color-border-strong`). Do not convey information by color alone: status badges contain text.
- Reduced motion: honor `prefers-reduced-motion: reduce`. No smooth scrolling, no transitions beyond an instant state change, no animation.
- Touch targets: at least 44×44px. Never below the 24px minimum of WCAG 2.2.
- Link and button labels: meaningful out of context. Repeated "Read case study" links include the system name (visually hidden text or an `aria-label` that starts with the visible text). No "click here". External links are indicated.
- Images and diagrams: alt text for meaningful images, a text equivalent for every diagram, empty alt for decorative images.
- Document: `lang="en"` (version 1 is English only), a unique `<title>` per page, a viewport that allows zoom (no `user-scalable=no`), text resizable to 200%.
- Verification during implementation: a keyboard-only pass, a 200% zoom and 320px reflow check, an automated audit (axe or Lighthouse), and one screen-reader spot check. None of these has been run, because nothing is built.

## 12. Technical architecture

Intended stack: React, Vite, plain CSS with CSS variables, reusable components, data-driven content.

Principles: the smallest dependency set; static output; no backend; no secrets in the client (everything in a Vite build is public).

Proposed dependencies: `react`, `react-dom`, `vite`, `@vitejs/plugin-react`, and `react-router-dom` for the `/systems/:slug` route (decision #8). No UI kit, Tailwind, CSS-in-JS, state library, animation library, icon pack, or analytics in version 1.

Structure, inside the `website/` subfolder so governance files stay at the repository root (decision #9):

```
website/
  index.html
  package.json
  vite.config.js
  public/
  src/
    main.jsx
    App.jsx
    styles/        tokens.css, base.css, components.css
    components/    Layout (SkipLink, Header, Footer), Section, Hero, SystemCard,
                   WorkflowDiagram (compact and full), StackList, ContactBlock,
                   StatusBadge, CaseStudy (one component per section)
    pages/         Home.jsx, CaseStudyPage.jsx, NotFound.jsx
    data/          site.js, systems.js
```

- Data-driven: all homepage copy lives in `site.js`. Each system and its case study lives in `systems.js` (or one file per system). Components read data and contain no copy beyond interface labels.
- Validation: a small development-time check that each system has the required fields, a valid status, and only tools from the claim register. A simple script or runtime warning, no heavy tooling.
- CSS: `tokens.css` holds the variables from section 9. Simple class names. Component styles in `components.css`. No `!important`. Mobile-first media queries.
- Routing (decision #8): two route types (`/` and `/systems/:slug`) plus not-found. With React Router, the host must support a single-page-app fallback. If the chosen host does not make that convenient, use hash routing instead.
- Build and hosting (decision #8): `vite build` produces static files for static hosting. No backend, no server code, and no paid domain in version 1. The specific host is an implementation choice to settle before deployment. Deployment is not part of TASK-005.
- Repository prerequisites for the implementation task: `.gitignore` currently ignores `node_modules/` but not the build output folder (`dist/`), so the implementation task must add it. DEC-008 applies: no secrets, no `.env` files with keys, and anything with a `VITE_` prefix is public.
- Quality gates (proposed): builds without errors, no console errors, keyboard and zoom checks, an automated accessibility audit, and a manual content-claim check against section 13. This specification claims no performance or accessibility score. Any target is measured during implementation.
- Working model: the Human supplies real systems and evidence, Claude implements when authorized, ChatGPT reviews, and the Human approves. Claude has no GitHub write access, so changes are prepared as files for the Human to commit.

## 13. Content/claim rules

13.1 Never fabricate: clients, client names, statistics, revenue, savings, performance improvements, user counts, testimonials, logos, awards, certifications, or years of experience.

13.2 Every factual claim on the site maps to a real artifact (a workflow, an export, a run record, a repository file), or it is removed.

13.3 An honest gap is better than an invented fact. "No production deployment yet." is acceptable copy.

13.4 Status labels, shown on cards and case studies:

- `prototype`: built and runnable, tested only with test or synthetic data, not used for real work.
- `working-demo`: runs end to end reliably for demonstration with realistic or sanitized data, not used by a real client or process.
- `production`: in real use by someone for a real process. Requires Human confirmation and a description of who uses it. Never used for anything else.

When unsure, use `prototype`.

13.5 Readiness rule for featuring a system: it has at least one recorded, dated, successful end-to-end run. Unrun or broken scenarios are not featured. Known bugs of a featured system are disclosed under "Known limitations".

13.6 Describe workflows as they actually are, including limits, failures, and what is still manual. Discarded approaches are worth documenting when they are informative.

13.7 Metrics only when measured from real runs, with date, method, and sample size. Otherwise they are not shown. No "up to", "typically", or estimated savings presented as results.

13.8 AI: name the actual model and its role. Do not imply autonomy, reasoning ability, or accuracy beyond what is demonstrated. Show how its output is checked.

13.9 Third-party names are text only. No logos. Do not imply partnership or endorsement.

13.10 Sanitization (DEC-008): no secrets, webhook URLs, tokens, connection identifiers, personal data, or client data in any text, screenshot, export, or repository file. Use placeholders or synthetic data.

13.11 Personal information: the Human decides every personal detail that is published. Minimal by default.

13.12 Copy written or edited with AI assistance is reviewed by the Human before publishing. The Human is responsible for its accuracy.

13.13 Case studies show a last-updated date. Stale content is updated or removed.

13.14 Candidate systems. A system that does not yet meet 13.5 stays a candidate and is not shown on the site. It is featured only when all of these are true and documented: (a) at least one successful end-to-end run with a recorded date; (b) the workflow actually exists; (c) the evidence can be sanitized; (d) the status label reflects reality; (e) every technology named is evidenced for that system. This repository currently contains no run evidence for any system, so no candidate is confirmed (decision #5).

## 14. Implementation boundary

TASK-005 (this task): architecture and specification only. Deliverables are this document and the task records (`TASKS.md`, `LOG.md`, `AGENT_ACTIVITY.md`). It ends at REVIEW. Only the Human may mark it DONE.

Not part of TASK-005: React components, `npm install`, a Vite project, a local prototype, writing content for real systems, assets, hosting, a domain, CI/CD, analytics, Make.com scenarios, Grok integration, or any production code.

Future task (not created here): Claude implements the approved website specification. Prerequisites:

1. The Human approves this specification, and records the approval as a DECISION if desired.
2. The Human resolves the items in section 16.2 that are marked as blocking.
3. The Human or ChatGPT creates the task with its own acceptance criteria.
4. The Human explicitly authorizes Claude.
5. When implementation actually starts, the Human decides whether `PROJECT.md` needs a new phase and non-goals, and whether that requires CTX-003 (decision #10). `PROJECT.md` currently says the phase is "Shared project infrastructure" and lists building the website as a non-goal of this phase. TASK-005 does not change `PROJECT.md` and does not create CTX-003.

The two tasks must not be mixed. No implementation is hidden inside TASK-005, and no re-specification happens inside the implementation task without a Human-approved change to this document.

## 15. Acceptance criteria

### 15.1 This specification (TASK-005)

- [ ] All 16 required sections are present in the required order.
- [ ] Positioning is defined: core positioning, 10-second message, audience, value proposition, tone.
- [ ] Homepage structure, project card, case study, workflow visualization, navigation and CTA, visual system, responsive behavior, accessibility, technical architecture, and content rules are defined.
- [ ] Technologies are tied to evidence or marked "Human to confirm". No metrics, clients, or results are invented.
- [ ] The implementation boundary is explicit.
- [ ] Open decisions are listed for the Human.
- [ ] The Human's decisions #2 to #11 are reflected. None is recorded as a DECISION by this task.
- [ ] No code was written, no `npm install` was run, nothing was built.

### 15.2 Proposed for the future implementation task (to be adopted or changed by the Human and ChatGPT)

- [ ] The homepage has the seven sections in order, with the anchors from section 3.
- [ ] Project cards and case-study pages are rendered from data and match sections 5 and 6.
- [ ] The workflow diagram component matches section 7 in compact and full variants.
- [ ] The visual system matches section 9 and none of the rejected patterns appears.
- [ ] Responsive behavior is verified at 320, 375, 768, 1024, and 1440px, with no horizontal page scroll.
- [ ] The accessibility baseline in section 11 is met, and the audit results are reported honestly.
- [ ] Every piece of displayed content traces to real evidence supplied by the Human. Nothing placeholder is published as real.
- [ ] No secrets in the repository or the build, and `.gitignore` covers the build output.
- [ ] The task ends at REVIEW. Only the Human marks it DONE.

## 16. Open decisions requiring Human approval

### 16.1 Decisions specified by the Human for this revision (2026-10-05)

These are the Human's inputs to this specification. They are not recorded in `DECISIONS.md`. Whether to record them there is the Human's call.

| # | Decision | Applied in |
|---|---|---|
| 2 | Headline and first-person voice | 2.2, 2.5 |
| 3 | Personal builder identity, short About, no extra personal details | 2.1, 4 (About) |
| 4 | Evidence-first technologies, per system | 2.6, 4 (Stack) |
| 5 | Feature only qualifying systems, no placeholders, readiness rule unchanged | 4 (Selected Systems), 13.5, 13.14 |
| 6 | Primary and secondary CTA. GitHub, and email only if a public email is accepted. No extra CTAs. | 4 (Contact), 8 |
| 7 | English only in version 1 | 3, 11 |
| 8 | Static hosting. React Router if a single-page-app fallback is available, otherwise hash routing. No backend. No paid domain. | 12 |
| 9 | Code location `website/` | 12 |
| 10 | No CTX-003 now. No `PROJECT.md` change for TASK-005. | 14 |
| 11 | Accent `#6FCFB4` and the current tokens | 9 |

### 16.2 Still open (Human)

| Item | Open question | Blocks implementation? |
|---|---|---|
| A | Approve this specification, or request changes (decision #1). Final approval is the Human's. This document does not claim it. | Yes |
| B | Publish a public email address, or use GitHub only. Needed for the Contact section. | Yes (Contact content) |
| C | The personal name to show, supplied when real content is prepared. It is not recorded in this specification. | Yes (content) |
| D | Which systems qualify under 13.5 and 13.14, with dated run evidence. This is the main constraint. One qualifying system is enough. | Yes |
| E | Technology confirmation per featured system (2.6). Only for systems that qualify. | Yes (content) |
| F | The specific static host. An implementation choice to settle before deployment, not part of TASK-005. | Before deployment only |
| G | When implementation starts: whether `PROJECT.md` needs a new phase and non-goals, and whether CTX-003 is needed (decision #10 defers this to the Human). | Yes, before the implementation task starts |
| H | Whether decisions #2 to #11 should also be recorded as formal decisions in `DECISIONS.md`. Not done by this task. | No |
| I | Optional case study about this repository's collaboration protocol. Not addressed in the Human's decisions. Left out of version 1 unless the Human asks. | No |
