Doc-It
Doc-It is a powerful, modular command-line tool that leverages local Large Language Models (LLMs) via Ollama to automatically generate professional documentation for your code changes. Track your work, explain complex changes in natural language, and export your documentation to multiple formats without ever leaving your terminal.

Features
AI-Powered Explanations: Automatically generates clear, human-readable explanations for code modifications.

Fully Local: Uses your local Ollama instance, ensuring your code stays private and secure.

** snapshot-Based Tracking:** Intelligently detects changes by comparing snapshots of your codebase, no Git dependency required.

Multiple Export Formats: Generate your final documentation in Markdown (.md), Microsoft Word (.docx), or LaTeX (.tex).

Modular & Configurable: Easily configure the tool through a simple .json file to specify the Ollama model, files to watch, and more.

Simple CLI Interface: A clean and intuitive command set makes documenting your project a breeze.

Prerequisites
Before you begin, you must have the following installed and running on your machine:

Python 3.10 or higher.

Ollama: The tool requires a running Ollama instance. You can download it from https://ollama.com/.

An Ollama Model: You need to have at least one model pulled. We recommend Llama 3:

ollama pull llama3

Installation
You can install Doc-It directly from PyPI using pip:

pip install doc-it-installer

Usage
Using Doc-It involves a simple three-step workflow. Navigate to your project's root directory in your terminal and run the following commands.

1. Initialize Your Project
This command sets up the necessary .docit directory, initializes a database, scans your entire codebase, and asks the AI to create a high-level summary. Run this only once per project.

doc-it init

2. Analyze and "Commit" Your Changes
After you've made some changes to your code, run the commit command. This will take a new snapshot, compare it to the previous one, and send every detected change to the AI to generate an explanation.

You must provide a message with the -m flag to describe your work.

doc-it commit -m "Refactored the user authentication module"

3. Generate the Documentation
When you're ready to create the final documentation file, run the generate command.

doc-it generate

By default, it creates a documentation.md file. You can specify other formats using the --format or -f flag:

Generate a Word document:

doc-it generate --format docx

Generate a LaTeX document:

doc-it generate --format tex

Authors
Kartik Sharma

Harshvardhan Singh

License
This project is licensed under the MIT License. See the LICENSE file for details.