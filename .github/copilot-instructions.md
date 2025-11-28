# Copilot instructions — Clarinha (TelaCaminhao)

Purpose: give AI coding agents the minimal, specific context needed to be productive in this repository.

- Repository shape: single Java source file at the repository root: `TelaCaminhao.java`.
- Language & UI: the project uses Java Swing (UI class `TelaCaminhao` extends `JFrame`). Identifiers and comments are in Portuguese.

Quick facts (from code):
- Class: `TelaCaminhao` (no package declared — default package).
- UI fields use the `txt` prefix convention: `txtComprimnto`, `txtLargura`, `txtAltura`, `txtOrcamento` (note: `txtComprimnto` looks like a possible typo of `txtComprimento`).
- File contains only field declarations and a top-line comment `// primeiro commit`.

What agents should know before editing:
- Preserve the repository's naming language (Portuguese) unless the human asks for a rename across the codebase.
- Keep UI fields using the `txt` prefix pattern for consistency with existing code.
- The project currently has no build files (no `pom.xml`, no `build.gradle`, no `README.md`). Ask the user for the preferred build tool and target JDK before adding one.
- The code lives in the default package. If you add a package declaration, update compile/run instructions and inform the user.

Build / run (minimal commands discovered — confirm JDK version with user):
```powershell
# compile
javac -encoding UTF-8 TelaCaminhao.java

# run (after successful compile)
java TelaCaminhao
```

When changing identifiers or structure:
- Ask the user before renaming fields or classes (e.g., fixing `txtComprimnto` → `txtComprimento`) because external code or resources might rely on those exact names.
- If you introduce packages, update the classpath/compile commands and mention the change in the commit message.

Commit & PR guidance:
- Keep changes small and focused. Use Portuguese commit messages when the project uses Portuguese (e.g., `Corrige nome do campo txtComprimnto`).
- When adding a build tool (Maven/Gradle), include a short README snippet explaining how to build and run.

Questions to ask the human before larger changes:
- What JDK version should be targeted (e.g., 8, 11, 17)?
- Do you want a build tool (Maven/Gradle) added, or do you prefer manual `javac` commands?
- Is the project expected to remain a single-file Swing demo, or will it grow into a multi-class application?

Examples of good prompts for the repo:
- "Add an input validator to `TelaCaminhao` that ensures `txtComprimnto` and `txtLargura` are numeric. Keep identifiers in Portuguese." 
- "Create a Maven `pom.xml` for JDK 17 and update `TelaCaminhao` package to `br.com.meuprojeto.ui` — confirm package migration with me first."

If anything here is incomplete or incorrect, tell me what you expect (build tool, JDK, or code style) and I'll update this file.
