# Technical Specification: FDA 510(k) Review Studio v6.0
## Regulatory Command Center: Nordic WOW — Pantone Edition

### 1. Executive Summary
The FDA 510(k) Review Studio v6.0 is a production-grade "Regulatory Command Center" designed to streamline the complex process of medical device regulatory reviews. Built on a Nordic-inspired aesthetic with deep Pantone integration, the platform serves as a high-performance workspace for agency reviewers, consultants, and regulatory affairs professionals. The system implements a four-step agentic pipeline powered by Gemini models, utilizing a "Master Source of Truth" derived from user-provided device descriptions. This version introduces three critical "WOW" visualization features: a real-time Pulse Metric array, a Temporal Heatmap for event auditing, and a Unified Command Center dashboard that aggregates compliance density and optimization flux data.

### 2. Design Philosophy: The Nordic WOW Aesthetic
The design of v6.0 transcends standard enterprise software through a deliberate application of the "Nordic WOW" philosophy. This approach prioritizes functional minimalism, high contrast, and tactile responsiveness.

#### 2.1 Pantone Color Integration
The system utilizes a dynamic theme engine based on the `PANTONE_PALETTES` constant. Instead of hardcoded HEX values, the UI relies on CSS variables (`--accent`, `--bg`, `--card`, `--text`) that are swapped at the root level.
- **Classic Blue (19-4052):** Used for stability, confidence, and connection in regulatory environments.
- **Illuminating (13-0647):** Utilized for warnings and highlights to ensure critical alerts are not overlooked.
- **Viva Magenta (18-1750):** Applied for high-intensity actions and revolutionary feature discovery.

#### 2.2 Typography & Spacing
- **Primary Face:** Inter (Sans-serif) for legibility in dense reports.
- **Technical Face:** JetBrains Mono for the "Black Box Recorder" and source buffers, establishing a clear distinction between human-readable reports and machine-generated data.
- **Spacing:** A strict 4px grid system ensures alignment, while variable padding is used to create a rhythmic hierarchy that prevents cognitive fatigue during long review sessions.

### 3. Technical Architecture
The platform is built as a full-stack application using a modern TypeScript stack, ensuring type safety and performance from the LLM logic down to the rendering layer.

#### 3.1 Frontend Stack
- **Framework:** React 19 (Functional Components with Hooks).
- **Styling:** Tailwind CSS 4.0 with `@theme` variable injection.
- **Animations:** `motion/react` (formerly Framer Motion) for physics-based layout transitions and stagger effects.
- **Visualizations:** Recharts 3.8 for SVG-based reactive charts.
- **Markdown:** `react-markdown` 10.1 for structural rendering of LLM outputs.

#### 3.2 AI & Intelligence Layer
- **SDK:** `@google/genai` (Google GenAI JavaScript SDK).
- **Model Orchestration:** Support for `gemini-3-flash-preview` and `gemini-1.5-pro-preview` with specialized prompt templates.
- **State Inference:** The platform uses a "State Lineage" (DAG) approach, where each step inherits the context of previous artifacts to ensure zero-loss information transfer.

### 4. Component Deep Dive
This section details the implementation of the three primary "WOW" features introduced in v6.0.

#### 4.1 Pulse Metrics (Interactive performance Indicator)
The `PulseMetrics` component is a high-visibility array that represents the "Vital Signs" of the regulatory synthesis.
- **Implementation:** USes a grid layout with `motion.div` for entry staggered animations.
- **Visual Feedback:** Each metric features a "Pulsing Glow" (CSS animation) whose color status (optimal, warning, critical) reflects the calculated delta of the current generation.
- **Real-time Response:** As the Gemini model streams or batch-finishes a synthesis, the metrics (Consistency, Compliance, Risk Score, Processing Time) update with smooth spring transitions via `framer-motion`.

#### 4.2 Temporal Log Stream (Active Heatmap & Black Box)
The `LogViewer` has been upgraded from a simple scrollable list to a sophisticated "Event Chronology" system.
- **Heatmap Logic:** The `TemporalHeatmap` sub-component calculates log density over HH:mm slices. It visualizes event frequency using variable-height bars with reactive hover states, allowing users to identify "bursts" of system activity or processing delays.
- **Auditability:** Every log entry is stamped with a unique ID and a color-coded type (system, success, warning, error), rendered in a high-contrast monospaced environment to simulate a hardware-level debugger.

#### 4.3 Command Center (Comprehensive Dashboard)
The Unified Command Center aggregates multidimensional data into a single screen.
- **Compliance Density (Radar Chart):** Maps device risks across Clinical, Technical, Regulatory, Safety, and Labeling axes. It provides a visual snapshot of "Incompleteness" in the submission.
- **Optimization Flux (Area Chart):** Measures token usage and processing efficiency across the pipeline steps, ensuring that the synthesis remains within cost and complexity boundaries.
- **Action Lineage:** A vertical timeline that tracks the "User-Model Interaction" history, allowing for point-in-time rollbacks (Time Travel feature).

### 5. Data Flow & Pipeline Logic
The core of the application is the `generateArtifact` function, which manages the sequential four-step pipeline.

#### 5.1 Step 1: Intelligence Gathering
- **Trigger:** User provides a "User Context / Device Description".
- **Goal:** Contextualize the device within the FDA's regulatory landscape.
- **Artifact:** A 2000-word FDA Intelligence Summary.

#### 5.2 Step 2: Instruction Generation
- **Dependency:** Requires Step 1 output.
- **Goal:** Create a "Guidance-Driven Review Instruction" set, including checkboxes and tables.
- **Prompt Logic:** Injects the "Intelligence" to derive specific review mandates.

#### 5.3 Step 3: Data Mapping
- **Goal:** Reorganize raw submission clinical/bench data into the tables generated in Step 2.
- **Complexity:** Handles table formatting and structural integrity checks.

#### 5.4 Step 4: Report Synthesis
- **Goal:** Compile a final 3000-word Comprehensive 510(k) Review Report.
- **Unique Constraint:** Must end with 20 comprehensive follow-up questions to the submitter, as per agency best practices.

### 6. Internationalization (I18n)
v6.0 features a robust localization engine (`TRANSLATIONS`) supporting English (EN) and Traditional Chinese (ZH). Unlike simple key-value pairs, the translations are integrated into the "technical vibe" of the app, using clinical and precise terminology (e.g., "Command Center" vs "任務控制中心").

### 7. Future Capability Roadmap
- **OCR Engine Integration:** Direct PDF/Image extraction for submission documents.
- **Multi-Agent Collaboration:** Simultaneous review by "Clinical" and "Technical" agent personas.
- **Blockchain Verification:** Immutable logging of review artifacts for legal traceability.

---

### 8. 20 Comprehensive Follow-Up Questions
1. How does the Pantone theme engine impact accessibility scores (WCAG 2.1) for color-blind users?
2. What is the maximum character limit for the `userInput` buffer before token truncation occurs in the Gemini model?
3. How does the `TemporalHeatmap` handle data persistence across browser sessions if the user does not trigger a "Save Artifact"?
4. Can the "Compliance Density" Radar Chart be exported as a standalone high-resolution SVG for external reporting?
5. What specific algorithms are used to calculate the "Compliance" and "Consistency" metrics in the Pulse Metrics component?
6. Logic for "Time Travel": Does rolling back to an earlier history entry also revert the LLM Settings (model, temperature) to their state at that time?
7. In Step 4 synthesis, how does the system ensure the "20 comprehensive follow-up questions" are distinct and not repetitive?
8. Are the CSS variables for the Pantone palettes accessible to the `react-markdown` custom components for inline styling?
9. How is the "AbortController" signal handled within the `@google/genai` request to prevent orphaned server-side processing?
10. Can the user define custom Pantone palettes beyond the pre-configured options?
11. What is the performance impact of rendering the Recharts components inside a `motion.div` with layout animations?
12. How does the system handle "Hallucination Detection" within the "Regulatory Risk Radar"?
13. Is there a plan to implement a "Diff" view between the current artifact and the previous state in the history?
14. How does the "Word Count" ticker handle Markdown formatting characters (e.g., #, *, [])?
15. What is the "System Directives" (Prompt) character limit for the fine-tuning of the "LLM Matrix"?
16. Does the "Optimization Flux" chart track latency per token or overall round-trip time (RTT)?
17. Can the "Temporal Log Stream" be filtered by "Event Type" to isolate critical errors?
18. How are the "Pulse Metrics" initial values determined before the first generation cycle begins?
19. Does the "Nordic WOW" aesthetic support a "High Contrast" mode for users with low visual acuity?
20. What security measures are in place to ensure that the `GEMINI_API_KEY` is not leaked through client-side error logging?
