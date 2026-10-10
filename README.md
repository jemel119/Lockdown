# Lab 13: The Lockdown

An HTML and CSS escape room set in an abandoned laboratory. Investigate three puzzle stations, examine recovered evidence, and combine the answers to unlock the exit.

## Developer

- **Project leader and sole developer:** Jeremy Henry-Atohengbe
- **Course:** CSC 6370
- **Level:** Graduate
- **Responsibilities:** Planning, wireframes, HTML, CSS, puzzle interactions, accessibility, testing, documentation, deployment, and presentation.

## Project Selection

- **Track:** Track F — Escape Room Challenge
- **Pack:** Investigation Pack
- **Setting:** An abandoned laboratory
- **Graduate feature 1:** AI Assistant Panel simulation
- **Graduate feature 2:** Recommendation Engine UI simulation

## Links

- GitHub: https://github.com/jemel119/Lockdown
- Live Codd website: 
- Presentation recording: 
- Trello board: https://trello.com/b/hynnKHDu/lab-13-the-lockdown

## Run Locally

1. Download or clone the repository.
2. Keep the HTML, CSS, font, and image files together in the project folder.
3. Open `index.html` in a current browser.

No installation, build process, JavaScript, backend, or database is required.

## Project Files

| File | Purpose |
|---|---|
| `index.html` | Story introduction, instructions, and station links |
| `rooms.html` | Three puzzles, answer feedback, assistant hints, and recommendations |
| `clues.html` | Filterable evidence board with expandable records |
| `unlock.html` | Final answer selections and animated exit |
| `team.html` | Developer introduction and project details |
| `styles.css` | Shared layout, theme, interactions, animations, and responsive rules |
| `SuperMario256.ttf` | Display font for headings and navigation |


## Story and User Flow

The laboratory is abandoned, but its security system remains active. The investigator must identify a containment symbol, restore emergency power, and recover an archive code.

1. Read the introduction and instructions.
2. Investigate the Symbol, Relay, and Archive stations.
3. Examine evidence or request prepared hints when needed.
4. Write down the three answers.
5. Select those answers on the Final Unlock page.

Selections do not transfer between pages. Users keep their own notes and reselect their answers at the exit terminal.

## Puzzle Answers

| Station | Answer | Evidence |
|---|---|---|
| Symbol | Triangle | The legend assigns Triangle to the isolation chamber |
| Relay | Cooling → Power → Security | Cooling precedes power, and security follows power |
| Archive | 274 | Isolation, storage, and observation have 2, 7, and 4 samples |

The exit opens only when all three correct answers are selected together. Incomplete selections keep it locked. A completed incorrect combination displays retry feedback. Reset clears the selections.

## HTML and CSS Implementation

Semantic HTML provides the page structure, navigation, headings, fieldsets, labels, and expandable details.

CSS provides:

- Variables for shared colors and spacing.
- Flexbox for navigation, the page layout, and the footer.
- Grid for station cards and evidence records.
- `:checked` and sibling selectors for answer feedback and clue filtering.
- `:has()` for station recommendations and the final answer combination.
- Transitions for navigation and buttons.
- Transforms for the skip link, hover movement, evidence reveal, and exit door.
- Responsive rules at 768px and 480px.


## Graduate Feature 1: AI Assistant Panel

### Behavior

Each station contains a prepared gentle hint and a full explanation. Users choose the level of help by opening the corresponding panel.

### Concept Mapping

The selected panel represents the user's intent: requesting a hint or requesting an explanation. The station's evidence provides the context, and the authored text represents the assistant response.

This is a UI simulation. It does not generate responses, process free-text prompts, or contact an AI service.

### Original Design Choice

Each station offers two levels of assistance so users can request a smaller clue before revealing the full reasoning.

### Integration

Assistant panels appear directly beneath the puzzle choices. Recommendation panels link users back to the relevant assistant when an answer is incorrect.

### Verified Checks

- Gentle hints and full explanations expand and collapse.
- Panels can be operated with the keyboard.
- Hint and explanation content matches the station evidence.

## Graduate Feature 2: Recommendation Engine UI

### Behavior

Each station displays one of three prepared recommendations:

| Selection state | Recommendation |
|---|---|
| No answer selected | Examine the relevant evidence |
| Incorrect answer selected | Review the relevant rule or hint |
| Correct answer selected | Record the answer and continue |

### Concept Mapping

The selected answer acts as the input signal. CSS applies a predefined rule to select a recommendation. Each result includes an explanation and a qualitative confidence label.

Confidence labels describe the strength of the authored rule. They are not calculated probabilities or machine-learning predictions.

### Original Design Choice

Recommendations explain why a next step is suggested. Archive completion recommends visiting the exit only if the user has recorded all three answers.

### Integration

Recommendations update alongside puzzle feedback. Each station uses its own selection state and links to evidence, hints, or the next destination.

### Verified Checks

- No selection displays the starting recommendation.
- Incorrect selections display the review recommendation.
- Correct selections display the next-step recommendation.
- Changing an answer updates the recommendation.
- Stations operate independently, and recommendation links work.

## Animations

| Animation | Trigger | Purpose |
|---|---|---|
| `status-pulse` | Final Unlock page loads | Briefly draws attention to the exit sign |
| `clue-reveal` | Evidence record opens | Reveals the record contents |
| `door-open` | All final answers are correct | Shows the exit opening |

The `prefers-reduced-motion` rule disables animations and transitions. Evidence remains visible, and the exit opens immediately when the correct combination is selected.

## Design Decisions and Tradeoffs

- Dark panels, teal accents, and amber feedback support the laboratory theme.
- Background pictures establish the setting while dark overlays preserve text readability.
- The Super Mario font is limited to headings and navigation. Instructions use a system font for readability.
- Native radio controls and expandable details support keyboard interaction.
- Shared CSS keeps the five pages visually consistent.
- Keeping state within each page allows the project to remain HTML and CSS only, but requires users to keep notes.
- Answers are present in the source. The puzzles are an interactive demonstration, not a secure access-control system.

## Accessibility and Responsive Design

Implemented features include:

- Skip-to-content links.
- Visible keyboard focus indicators.
- Navigation labels and current-page indicators.
- Associated radio labels and fieldset legends.
- Feedback expressed through text as well as color.
- Responsive layouts and wrapping text.
- Reduced-motion support.
- System-font fallback if the supplied font cannot load.
- A solid background-color fallback if an image cannot load.

## Testing

Manual checks were completed in the local browser.

| Check | Result |
|---|---|
| Navigation and station links | Passed |
| Correct and incorrect puzzle feedback | Passed |
| Assistant panel interactions | Passed |
| Recommendation updates and links | Passed |
| Evidence filtering and expansion | Passed |
| Final unlock, incorrect combinations, and reset | Passed |
| Keyboard navigation and controls | Passed |
| Layouts at 375, 480, 768, and 1280px | Passed |
| Layout and controls at 200% zoom | Passed |
| Reduced-motion behavior | Passed |
| HTML validation for all five pages | No errors reported |
| CSS validation | No errors reported |
| Contrast verification | Pending |
| Live Codd verification | Pending |

## Development Process

Work was completed in stages with commits for individual files or related changes.

Trello tracks tasks using:

- Backlog
- To Do
- In Progress
- Review
- Done

Daily card comments record the date, actual time spent, completed work, pending checks, and relevant commit. Time is categorized as Proposal, Layout, Motion, or Polish.

The proposal was submitted on October 4, 2026. Development evidence and showcase materials accompany the final submission.

## Asset Credits

| Asset | 
| `SuperMario256.ttf` | 
| `lab.avif` | 
| `puzzle.jpg` | 
| `clue.jpg` |
| `exit.avif` | 
| `team.webp` | 

The interface decorations and exit-door illustration are created with CSS.

## AI Assistance Disclosure

OpenAI ChatGPT/Codex provided assistance with proposal drafting, worklow planning, implementation guidance, testing checklists, and documentation drafts.

I selected the project direction and assets, applied the code locally, implemented the code, managed commits, and performed the reported browser checks.

The assistant and recommendation panels within the website use prepared content and do not connect to a live AI service.