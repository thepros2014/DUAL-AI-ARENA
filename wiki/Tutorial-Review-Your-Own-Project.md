# Tutorial: review your own project

**Goal:** run a focused Arena review and bring useful changes back into your development workflow.

## 1. Choose a small review target

Pick one function, module, or related group of files. A well-defined question is easier to evaluate than “find every bug in this project.”

For example:

> Review the input validation in this module. Preserve its public interface. Identify concrete failing cases, propose minimal fixes, and explain how to test them.

Include the relevant requirements and supporting code. If an important dependency is missing, add it or explain its behavior rather than asking the model to guess.

## 2. Prepare your working copy

Save or commit your current work and use a separate branch or practice copy for proposed changes. Exclude credentials, private configuration, generated files, and unrelated data from the review input.

Select providers appropriate for the code you are sharing. Cloud inference sends the selected input to the chosen provider; use a local configuration when that matches your needs.

## 3. Import the selected code

Follow [[How-To-Import-Local-Codebases]]. Check that the intended files appear in the challenge before starting. If a file is missing or filtered, reduce the input or use a supported source format.

## 4. Run a focused battle

Start with manual handoff when learning a new codebase. Read each finding for a clear location, explanation, and concrete example. Ask for clarification when a finding depends on an unstated assumption.

Use [[How-To-Run-Autonomous-Battles]] when you are comfortable monitoring consecutive turns. More rounds do not by themselves establish correctness.

## 5. Review and integrate

Inspect the proposed changes using [[Viewing-and-Exporting-Results]]. Bring accepted changes into your review branch, then run your project's tests and relevant checks. Check compatibility with callers and adjacent code, not only the reported failure.

If a proposal is too broad, request a smaller change tied to one finding. Keep changes you can explain and verify.

## 6. Share useful feedback

In community posts, describe the review goal, model configuration, and result. Use a small synthetic reproduction for a problem, and remove private details before posting.

**You have completed this tutorial when:** a proposed change has been reviewed, tested in your project, and either accepted with evidence or rejected with a clear reason.

[[Arena-Tutorials]] · [[Customer-FAQ-and-Troubleshooting]]
