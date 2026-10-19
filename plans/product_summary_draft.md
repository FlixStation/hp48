# hp48-flix — Product Executive Summary (v1.0)

> Working name. Rename before any public launch.

## Vision
A free, open-source RPN calculator that feels like the HP 48GX, runs on a modern desktop, and stays maintainable by a small community for years.

## Why
- Existing HP 48 emulators are full hardware emulators that require a copyrighted HP ROM, rather than clean, native modern desktop applications.
- Many are old and may stop being maintained.
- It is also a hands-on way for its author, a petroleum engineer, to learn how software is built and shipped.

## Who it's for
1. **Felix**: daily-use calculator, and a learning vehicle.
2. **Engineers and students** who like RPN and the HP 48 workflow.
3. **Open-source contributors** who want a small, friendly project.

## What it is
- A **functional** RPN calculator: a stack, HP-style number handling, and a growing set of commands.
- Written in Python, with **no HP ROM and no hardware emulation**.
- Target behavior: **HP 48GX**, checked by hand against iHP48.
- **Data scope**: Start strictly with real numbers and basic scientific operations; units, complex numbers, and matrices will be introduced in later phases.
- **Form factor progression**: Engine-first design. Validated first via an M1 terminal prototype, evolving into a dedicated desktop GUI window with an HP-style display and full keyboard support.

## What it is not (for now)
- Not a Saturn CPU or ROM emulator.
- No graphical window in M1 (terminal-only prototype).
- Not a full RPL programming environment.
- No HP logos or artwork. Not affiliated with HP Inc.

## Principles
1. **Small steps.** Each step is useful and understandable on its own.
2. **Learn as we go.** Propose working code with concise explanations of the core software concept behind each step.
3. **Clean-room.** We write our own code from documented and observed behavior. We copy nothing from the ROM or from GPL projects (e.g., x48, droid48).
4. **Open from day one.** Apache-2.0 licence.
5. **Decide late.** We only specify the next step in detail.

## Roadmap (only M0 and M1 are committed)

| Step | What | You'll see | Concept you learn |
|---|---|---|---|
| **M0** | **This summary, approved** | A one-page document capturing scope and decisions | Product vision and scope definition |
| **M1** | **Throwaway prototype**: single-file terminal RPN calculator (~80 lines), strict HP single-entry input, 4-level display, HP error handling | Type `3 ENTER 4 +` and see stack levels update | What a stack and RPN are in code, plus running Python |
| M2 | Review checkpoint | A short note: what worked, what to do next | Retrospective & design review |
| M3+ | *Candidates, not committed:* modular architecture, unit tests & CI, scientific commands, desktop GUI window | Chosen together after M2 | One concept per step |

## Success criteria
- **M0:** You read this document and confirm: "Yes, that's the product."
- **M1:** You run the terminal prototype yourself and can explain, in your own words, what happens to the stack when you press `+`.

## Agreed Decisions (from Alignment Interview)
- **Primary Interface Vision:** Dedicated desktop GUI window with an HP-style 4-level display and full keyboard support (post-M1).
- **M1 Prototype Organization:** A single clean Python file (~80 lines) read top-to-bottom.
- **M1 Input Handling:** Strict HP simulation (one number or command per line, pressing Return).
- **M1 Operations Scope:** `+`, `-`, `*`, `/`, `ENTER`, `DROP`, `SWAP`, `CLEAR`, and `QUIT`.
- **M1 Error Behavior:** HP 48 style (display messages like `Too Few Arguments` / `Zero Divide`, preserving stack).
- **M1 Display Format:** Classic 4-level vertical stack (`4:`, `3:`, `2:`, `1:` above the prompt).
- **Math Scope:** Real numbers and basic arithmetic first; units and matrices deferred.
- **Clean-room Reference:** Behavior verified against `iHP48` and HP 48GX manuals; no GPL code / no ROM.
- **Licence & Target:** Apache-2.0, macOS first, working name `hp48-flix`.
