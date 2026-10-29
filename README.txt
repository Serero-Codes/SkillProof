SkillProof

Show the work behind your skills.

SkillProof is a lightweight prototype that helps developers explore how
technical skills may be represented in a public GitHub repository. A
user provides a public repository URL, selects technical skills, and
receives a report showing potential evidence found in the files
inspected.

SkillProof is designed to make evidence easier to review---not to make
hiring decisions or certify someone's abilities.

Why SkillProof?

A CV can list technologies, but it may not show where those technologies
appear in a developer's work. SkillProof connects selected skills to
inspectable repository evidence, with file links, snippets, and
explanations that a reviewer can follow up on.

Features

Analyze a public GitHub repository using its URL.

Select technical skills to investigate.

Inspect eligible repository files within configured limits.

Detect potential evidence using transparent, deterministic
pattern-matching rules.

Present evidence with source-file links, snippets, and explanations.

Report inspection status and limitations rather than treating
missing evidence as proof that a skill is absent.

Run in the browser without requiring a GitHub personal access token
for basic public-repository access.

Skills currently represented

The current rule set includes:

Python

JavaScript

TypeScript

Java

C/C++

React

SQL

Git

Docker

HTML/CSS

Node.js

REST APIs

Data Analysis

Machine Learning

Testing

CI/CD

Cloud (AWS/GCP/Azure)

Linux/Shell

MongoDB/NoSQL

Algorithms

Detection is rule-based. A detected pattern is an indication that
relevant material may exist; it is not a complete evaluation of the
developer's skill.

How it works

Enter a repository URL. Provide a link to a public GitHub
repository.

Choose skills. Select up to the limit supported by the
interface.

Inspect files. SkillProof requests repository metadata and
eligible file contents through the GitHub API.

Match evidence. Deterministic rules look for relevant file
types, names, and content patterns.

Review the report. Examine evidence snippets, open the original
files, and read the inspection status and limitations.

Evidence statuses

SkillProof uses these statuses to communicate what the inspection found:

Status                              Meaning

evidence_found                    One or more patterns relevant to
the selected skill were found in
the inspected files.

not_found_in_inspected_files      The inspection did not find a
matching pattern in the files it
inspected. This does not mean
the person lacks the skill.

needs_further_assessment          The available evidence is not
sufficient for a meaningful
conclusion and should be reviewed
further.

Technology

React

TypeScript

Vite

Tailwind CSS

GitHub REST API

Deterministic regular-expression/pattern matching

Getting started

Prerequisites

Install a recent version of Node.js that includes
npm.

1. Clone the repository

Replace YOUR_GITHUB_USERNAME with the GitHub account or organization
that hosts this project.

git clone https://github.com/YOUR_GITHUB_USERNAME/SkillProof.git
cd SkillProof

If your repository has a different name, use that name in the cd
command.

2. Install dependencies

npm install

3. Run the development server

npm run dev

Open the local URL printed in the terminal by Vite (commonly
http://localhost:5173).

4. Check the project

Run the TypeScript check:

npm run typecheck

Create a production build:

npm run build

The current project scripts do not define a dedicated test command.

Inspection boundaries

Repository inspection is deliberately bounded. The current
implementation configures limits on the number of files, directory
depth, file size, API requests, and request timeouts. Files identified
as binary, generated, lock, or potentially sensitive are intended to be
skipped.

GitHub unauthenticated API limits may apply. Private repositories are
not supported by the public-repository workflow.

Repository contents are inspected as text; they should not be executed,
installed, or treated as trusted instructions. Do not submit secrets or
private information in repository content.

Important limitations

SkillProof is an evidence-support prototype, not a skill
certification or hiring system.

Pattern matching can produce false positives and false negatives.

A technology may be used in ways that the current rules do not
recognize.

Evidence may exist in files that are not inspected because of
configured limits, API restrictions, unsupported file types, or
retrieval failures.

A repository can contain code written by multiple contributors;
repository evidence alone does not establish authorship.

Finding a pattern does not prove that the code is correct, secure,
production-ready, or independently written by a particular person.

Not finding evidence in the inspected files does not mean a person
lacks the skill.

Results should be reviewed in context by a human.

Privacy

The application is designed to analyze a repository URL and retrieve
public repository data for the inspection. The prototype does not
require a GitHub personal access token for basic public access. Review
the implementation before deploying it if you need to make specific
privacy, logging, or data-retention commitments.

Project status

SkillProof is a prototype under development. Behaviour and supported
evidence rules may change as the implementation is tested and improved.

Contributing

Contributions and feedback are welcome. Useful contributions include:

Adding or improving transparent skill-detection rules.

Improving error handling and reporting for incomplete inspections.

Adding mocked tests for GitHub API responses and edge cases.

Improving accessibility and usability.

Documenting false-positive and false-negative cases.

When proposing a rule, explain what it detects, why the signal is
relevant, and where the rule may be misleading.

License

No license has been specified yet. Unless a license is added to this
repository, reuse and redistribution are not automatically granted.

SkillProof --- Show the work behind your skills.
