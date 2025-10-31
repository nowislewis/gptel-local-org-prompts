# gptel-local-org-prompts.el

A local org file-driven system prompt selector for [gptel](https://github.com/karthink/gptel).

## Overview

This extension allows you to use the content of any `.org` file from a configured local directory (recursively) as a selectable prompt for your gptel LLM sessions. Each org file becomes a candidate; after selection, its content is used as the system prompt. You can further edit it as needed.

- 100% local, privacy-friendly
- Organize prompts via directory structure (category-like)
- Preview with the first 50 characters (configurable)
- Immediate editing after selection

---

## Features

- Recursively loads all `.org` files under your configured directory. Each file's content is a prompt candidate.
- The selection menu displays each candidate as `relative/path/to/file.org: prompt preview` for easy filtering by directory/category.
- After selection, the full file content is set as the system prompt and opened for further editing.
- Highly customizable: prompt root directory, preview length, etc.

---

## Installation & Usage

1. Place `gptel-local-org-prompts.el` somewhere in your `load-path`.
2. Add to your Emacs config:
   ```elisp
   (require 'gptel-local-org-prompts)
   ```
3. Set your main prompt directory (where your org prompt files are stored):
   ```elisp
   (setq gptel-local-org-prompts-directory "~/gptel-prompts/")
   ```
4. (Optional) Adjust the prompt preview length:
   ```elisp
   (setq gptel-local-org-prompts-preview-length 50)
   ```
5. Use interactively:
   ```elisp
   M-x gptel-choose-org-prompt
   ```
   Select a prompt, edit if needed, and it will be set as your gptel system prompt.

---

## Configuration Table

| Variable                                | Type     | Default                          | Description                             |
|-----------------------------------------|----------|-----------------------------------|-----------------------------------------|
| `gptel-local-org-prompts-directory`     | string   | `~/gptel-local-prompts/`          | Root directory to search org prompts     |
| `gptel-local-org-prompts-preview-length`| integer  | `50`                              | Preview length (characters) in menu      |

---

## Author & Feedback

Developed by ECA + Lewisliu collaboration.

Issues, PR and feedback welcome!
