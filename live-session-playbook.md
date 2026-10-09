# Live session playbook — Incheon resilience workshop

For Shreyasi/Anurag to run during tomorrow's 20-minute presentation window, and to
test on today's 3pm call before relying on it live.

---

## Role split (confirm on the 3pm call)

- **Presenter**: gives the 20-minute talk. Not touching Mentimeter/AI during this window.
- **Virtual host** (Shreyasi or Anurag, pick one): owns Mentimeter results, runs the
  clustering step, pastes the output into the two placeholder slides. Not doing
  anything else during the 20 minutes.
- **Second pair of hands** (the other of the two): backup on the clustering step,
  watches the clock, flags if timing is slipping so the host can switch to the
  fallback path early rather than late.

---

## The one path: copy responses → AI prompt → Mermaid render

No Miro, no new tools — just an AI chat, a copy-paste, and mermaid.live. Since
nobody on the team has used Miro before, adding it the day before a live,
no-do-over session was a new variable that didn't earn its place. This path only
uses things you already know how to do.

### Step 1 — copy the raw responses
From the Mentimeter results view, copy every submitted answer for the question as a
plain list (one per line).

### Step 2 — paste into one of these two prompts (use with Claude/ChatGPT)

**Prompt for Q1 — "What are the three biggest drivers of disaster risk in your country?"**

```
You are helping synthesize live audience responses from a workshop with national
disaster-risk delegations.

QUESTION ASKED: "What are the three biggest drivers of disaster risk in your country?"

RAW RESPONSES (one per line, from ~40 delegates, may repeat, may be terse, may need
light translation):
{PASTE RESPONSES HERE}

TASK:
1. Merge near-duplicates. Translate any non-English text to English, preserving
   original meaning.
2. Cluster every response under exactly these five categories (Climate and Disaster
   Resilience Index dimensions) — do not invent new top-level categories:
   - Physical (built environment)
   - Natural (natural environment)
   - Social
   - Economic and livelihoods
   - Institutional capacities
   A response may fit more than one category — pick the single best fit.
3. Within each category, group similar responses into 2-4 short theme labels
   (3-6 words), and note how many delegates raised each theme, e.g. "Weak land-use
   enforcement (6)".
4. Output ONLY a Mermaid mindmap in this exact format, nothing else — no preamble,
   no explanation:

mindmap
  root((Drivers of disaster risk))
    Physical
      Theme A (n)
      Theme B (n)
    Natural
      Theme C (n)
    Social
      Theme D (n)
    Economic and livelihoods
      Theme E (n)
    Institutional capacities
      Theme F (n)

Keep every leaf label under 6 words. Omit a category entirely if it got zero
responses — do not invent content to fill it.
```

**Prompt for Q2 — "Which population is most likely to be left behind during disasters?"**

```
You are helping synthesize live audience responses from a workshop with national
disaster-risk delegations.

QUESTION ASKED: "Which population is most likely to be left behind during disasters?"

RAW RESPONSES (one per line, from ~40 delegates, may repeat, may be terse, may need
light translation):
{PASTE RESPONSES HERE}

TASK:
1. Merge near-duplicates. Translate any non-English text to English, preserving
   original meaning.
2. Cluster responses under these Sendai Framework vulnerable-population categories.
   Reuse this list; only add a new branch if a response clearly doesn't fit any of
   them:
   - Older persons
   - Persons with disabilities
   - Women and girls
   - Children
   - Poor / economically marginalized households
   - Informal settlement residents
   - Migrants and displaced people
   - Indigenous / ethnic minority groups
   - Remote / hard-to-reach rural populations
3. Within each populated category, note the specific reason delegates gave (short
   phrase) and how many raised it, e.g. "No independent means of evacuation (5)".
4. Output ONLY a Mermaid mindmap in this exact format, nothing else — no preamble,
   no explanation:

mindmap
  root((Leaving no one behind))
    Older persons
      reason (n)
    Persons with disabilities
      reason (n)

Keep every leaf label under 6 words. Omit a category entirely if it got zero
responses — do not invent content to fill it.
```

### Step 3 — render and export
1. Copy the mermaid code the AI returns.
2. Go to mermaid.live, paste into the left pane.
3. Click Export → PNG (top right).
4. Paste the PNG into the matching placeholder slide (slide 1 for Q1, slide 2 for Q2).

---

## Timing rehearsal (do this on the 3pm call)

1. Submit ~15-20 dummy answers to each Mentimeter question — mix in duplicates, a
   couple of terse one-word answers, and a couple of non-English phrases so the test
   isn't cleaner than reality will be.
2. Run the full path end to end, for both questions, twice — copy responses, run
   the prompt, render on mermaid.live, export PNG, paste into the placeholder slide.
   The second run should be visibly faster than the first; if it isn't, something
   in the steps is unclear and needs fixing before tomorrow, not during it.
3. It needs to comfortably fit inside the 20-minute presentation window — target
   under 6 minutes per question, so there's margin if the room's answers are
   messier or slower to arrive than the test.
4. Decide now, not tomorrow morning: who is the virtual host running this (one
   person, start to finish, not split across two people mid-task), and where
   exactly the mermaid.live tab and the AI chat tab live (bookmarked, already
   logged in, no sign-in prompts eating time tomorrow).

---

## Slide checklist (deck order, per the mail)

1. Drivers of disaster risk — live synthesis (Q1 mindmap)
2. Leaving no one behind — live synthesis (Q2 mindmap)
3. Physical (built environment) — schematic map
4. Natural (natural environment) — schematic map
5. Social — schematic map
6. Economic and livelihoods — schematic map
7. Institutional capacities — schematic map
8. Discussion prompt: "How useful is this, and how would you use it in your work?"

Slides 3-7 are already built: `D:\ANSHUTALK\slides\slide-*.png`.
