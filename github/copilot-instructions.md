# Global AI Coding Rules for Windsurf
https://code.visualstudio.com/docs/copilot/reference/copilot-vscode-features

These rules establish universal standards and preferences that apply across all projects developed with Windsurf AI assistance.

## Core Principles

* **Simplicity First (SF):** Always choose the simplest viable solution. Complex patterns or architectures require explicit justification.
* **Readability Priority (RP):** Code must be immediately understandable by both humans and AI during future modifications.
* **Dependency Minimalism (DM):** No new libraries or frameworks without explicit request or compelling justification.
* **Industry Standards Adherence (ISA):** Follow established conventions for the relevant language and tech stack.
* **Strategic Documentation (SD):** Comment only complex logic or critical functions. Avoid documenting the obvious.
Write new docs in english. If you find docs in other languages, rewrite them into english.
* **Test-Driven Thinking (TDT):** Design all code to be easily testable from inception.

## Workflow Standards

* **Atomic Changes (AC):** Make small, self-contained modifications to improve traceability and rollback capability.
* **Commit Discipline (CD):** Recommend regular commits with semantic messages using conventional commit format:
  ```
  type(scope): concise description
  
  [optional body with details]
  
  [optional footer with breaking changes/issue references]
  ```
  Types: feat, fix, docs, style, refactor, perf, test, chore
* **Transparent Reasoning (TR):** When generating code, explicitly reference which global rules influenced decisions.
* **Context Window Management (CWM):** Be mindful of AI context limitations. Suggest new sessions when necessary.
* **Preserve Existing Code (PEC):** Windsurf must not overwrite or break functional code unless explicitly instructed otherwise. Propose changes conservatively to maintain codebase integrity [AC, CA]

## Code Quality Guarantees

* **DRY Principle (DRY):** No duplicate code. Reuse or extend existing functionality.
* **Clean Architecture (CA):** Generate cleanly formatted, logically structured code with consistent patterns.
* **Robust Error Handling (REH):** Integrate appropriate error handling for all edge cases and external interactions.
* **Code Smell Detection (CSD):** Proactively identify and suggest refactoring for:
  * Functions exceeding 30 lines
  * Files exceeding 300 lines
  * Nested conditionals beyond 2 levels
  * Classes with more than 5 public methods

## Security & Performance Considerations

* **Input Validation (IV):** All external data must be validated before processing.
* **Resource Management (RM):** Close connections and free resources appropriately.
* **Constants Over Magic Values (CMV):** No magic strings or numbers. Use named constants.
* **Security-First Thinking (SFT):** Implement proper authentication, authorization, and data protection.
* **Performance Awareness (PA):** Consider computational complexity and resource usage.

## AI Communication Guidelines

* **Rule Application Tracking (RAT):** When applying rules, tag with the abbreviation in brackets (e.g., [SF], [DRY]).
* **Explanation Depth Control (EDC):** Scale explanation detail based on complexity, from brief to comprehensive.
* **Alternative Suggestions (AS):** When relevant, offer alternative approaches with pros/cons.
* **Knowledge Boundary Transparency (KBT):** Clearly communicate when a request exceeds AI capabilities or project context.

## Continous documentation during development process (CDiP)

* **Keep all  *.md files up-to-date, which where used to keep track of progress, todos and help ing infos** (e.g. TASK_LIST.md, README.md, LEARNING_FROM_JAVA.md, VAU_IMPLEMENTATION_PLAN.md, etc.)
- generate memories for each new created or new requested md file, which shall help the AI or the developer to keep track of the project context and progress.
- update the md files, when new tasks are added, completed or when new todos are added or completed.
- but do not touch *.md files in doc folder!  

## Feature-Based Development Workflow

1. **Create Feature Branch:**
   - For each new feature or task, create a dedicated feature branch from master.
   - Use descriptive branch names with conventional format: `feature/feature-name` or `task/task-name` [CD].

2. **Development Process:**
   - Complete all development work in the feature branch [AC].
   - Ensure all tests pass successfully before considering the task complete [CTC].
   - Follow clean architecture principles and coding standards [CA].

3. **Task Completion in Feature Branch:**
   - Mark tasks as completed in `TASK_LIST.md` within the feature branch [CDiP].
   - Commit these changes to the feature branch [CD].
   - This should be done before creating the pull request.

4. **Pull Request Process:**
   - Create a pull request to the master branch when feature is complete [AC].
   - Include the updated `TASK_LIST.md` in the pull request [CDiP].
   - Wait for reviewer acknowledgment before proceeding.

5. **Merge Process:**
   - After approval, merge the feature branch into master.
   - Delete the feature branch after successful merge [AC].

6. **Task Tracking:**
   - The updated `TASK_LIST.md` is already part of the merged changes [CDiP].
   - No additional updates to `TASK_LIST.md` should be needed after the PR is approved.

**This workflow ensures that:**
   - Each feature can be rolled back independently if needed [AC].
   - Code quality is maintained through the review process [CA].
   - The master branch always contains a working version of the application [PEC].
   - Progress is clearly tracked and documented [CDiP].
   - Task completion is part of the feature work and included in the review process [CD].
# COPILOT EDITS OPERATIONAL GUIDELINES
                
## PRIME DIRECTIVE
	Avoid working on more than one file at a time.
	Multiple simultaneous edits to a file will cause corruption.
	Be chatting and teach about what you are doing while coding.

## LARGE FILE & COMPLEX CHANGE PROTOCOL

### MANDATORY PLANNING PHASE
	When working with large files (>300 lines) or complex changes:
		1. ALWAYS start by creating a detailed plan BEFORE making any edits
            2. Your plan MUST include:
                   - All functions/sections that need modification
                   - The order in which changes should be applied
                   - Dependencies between changes
                   - Estimated number of separate edits required
                
            3. Format your plan as:
## PROPOSED EDIT PLAN
	Working with: [filename]
	Total planned edits: [number]

### MAKING EDITS
	- Focus on one conceptual change at a time
	- Show clear "before" and "after" snippets when proposing changes
	- Include concise explanations of what changed and why
	- Always check if the edit maintains the project's coding style

### Edit sequence:
	1. [First specific change] - Purpose: [why]
	2. [Second specific change] - Purpose: [why]
	3. Do you approve this plan? I'll proceed with Edit [number] after your confirmation.
	4. WAIT for explicit user confirmation before making ANY edits when user ok edit [number]
            
### EXECUTION PHASE
	- After each individual edit, clearly indicate progress:
		"✅ Completed edit [#] of [total]. Ready for next edit?"
	- If you discover additional needed changes during editing:
	- STOP and update the plan
	- Get approval before continuing
                
### REFACTORING GUIDANCE
	When refactoring large files:
	- Break work into logical, independently functional chunks
	- Ensure each intermediate state maintains functionality
	- Consider temporary duplication as a valid interim step
	- Always indicate the refactoring pattern being applied
                
### RATE LIMIT AVOIDANCE
	- For very large files, suggest splitting changes across multiple sessions
	- Prioritize changes that are logically complete units
	- Always provide clear stopping points
            
## General Requirements
	Use modern technologies as described below for all code suggestions. Prioritize clean, maintainable code with appropriate comments.
            
### Accessibility
	- Ensure compliance with **WCAG 2.1** AA level minimum, AAA whenever feasible.
	- Always suggest:
	- Labels for form fields.
	- Proper **ARIA** roles and attributes.
	- Adequate color contrast.
	- Alternative texts (`alt`, `aria-label`) for media elements.
	- Semantic HTML for clear structure.
	- Tools like **Lighthouse** for audits.
        
## Browser Compatibility
	- Prioritize feature detection (`if ('fetch' in window)` etc.).
        - Support latest two stable releases of major browsers:
	- Firefox, Chrome, Edge, Safari (macOS/iOS)
        - Emphasize progressive enhancement with polyfills or bundlers (e.g., **Babel**, **Vite**) as needed.
            
## PHP Requirements
	- **Target Version**: PHP 8.1 or higher
	- **Features to Use**:
	- Named arguments
	- Constructor property promotion
	- Union types and nullable types
	- Match expressions
	- Nullsafe operator (`?->`)
	- Attributes instead of annotations
	- Typed properties with appropriate type declarations
	- Return type declarations
	- Enumerations (`enum`)
	- Readonly properties
	- Emphasize strict property typing in all generated code.
	- **Coding Standards**:
	- Follow PSR-12 coding standards
	- Use strict typing with `declare(strict_types=1);`
	- Prefer composition over inheritance
	- Use dependency injection
	- **Static Analysis:**
	- Include PHPDoc blocks compatible with PHPStan or Psalm for static analysis
	- **Error Handling:**
	- Use exceptions consistently for error handling and avoid suppressing errors.
	- Provide meaningful, clear exception messages and proper exception types.
            
## HTML/CSS Requirements
	- **HTML**:
	- Use HTML5 semantic elements (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`, `<search>`, etc.)
	- Include appropriate ARIA attributes for accessibility
	- Ensure valid markup that passes W3C validation
	- Use responsive design practices
	- Optimize images using modern formats (`WebP`, `AVIF`)
	- Include `loading="lazy"` on images where applicable
	- Generate `srcset` and `sizes` attributes for responsive images when relevant
	- Prioritize SEO-friendly elements (`<title>`, `<meta description>`, Open Graph tags)
            
	- **CSS**:
	- Use modern CSS features including:
	- CSS Grid and Flexbox for layouts
	- CSS Custom Properties (variables)
	- CSS animations and transitions
	- Media queries for responsive design
	- Logical properties (`margin-inline`, `padding-block`, etc.)
	- Modern selectors (`:is()`, `:where()`, `:has()`)
	- Follow BEM or similar methodology for class naming
	- Use CSS nesting where appropriate
	- Include dark mode support with `prefers-color-scheme`
	- Prioritize modern, performant fonts and variable fonts for smaller file sizes
	- Use modern units (`rem`, `vh`, `vw`) instead of traditional pixels (`px`) for better responsiveness
            
## JavaScript Requirements
		    
	- **Minimum Compatibility**: ECMAScript 2020 (ES11) or higher
	- **Features to Use**:
	- Arrow functions
	- Template literals
	- Destructuring assignment
	- Spread/rest operators
	- Async/await for asynchronous code
	- Classes with proper inheritance when OOP is needed
	- Object shorthand notation
	- Optional chaining (`?.`)
	- Nullish coalescing (`??`)
	- Dynamic imports
	- BigInt for large integers
	- `Promise.allSettled()`
	- `String.prototype.matchAll()`
	- `globalThis` object
	- Private class fields and methods
	- Export * as namespace syntax
	- Array methods (`map`, `filter`, `reduce`, `flatMap`, etc.)
	- **Avoid**:
	- `var` keyword (use `const` and `let`)
	- jQuery or any external libraries
	- Callback-based asynchronous patterns when promises can be used
	- Internet Explorer compatibility
	- Legacy module formats (use ES modules)
	- Limit use of `eval()` due to security risks
	- **Performance Considerations:**
	- Recommend code splitting and dynamic imports for lazy loading
	**Error Handling**:
	- Use `try-catch` blocks **consistently** for asynchronous and API calls, and handle promise rejections explicitly.
	- Differentiate among:
	- **Network errors** (e.g., timeouts, server errors, rate-limiting)
	- **Functional/business logic errors** (logical missteps, invalid user input, validation failures)
	- **Runtime exceptions** (unexpected errors such as null references)
	- Provide **user-friendly** error messages (e.g., “Something went wrong. Please try again shortly.”) and log more technical details to dev/ops (e.g., via a logging service).
	- Consider a central error handler function or global event (e.g., `window.addEventListener('unhandledrejection')`) to consolidate reporting.
	- Carefully handle and validate JSON responses, incorrect HTTP status codes, etc.
            
## Folder Structure
	Follow this structured directory layout:

		project-root/
		├── api/                  # API handlers and routes
		├── config/               # Configuration files and environment variables
		├── data/                 # Databases, JSON files, and other storage
		├── public/               # Publicly accessible files (served by web server)
		│   ├── assets/
		│   │   ├── css/
		│   │   ├── js/
		│   │   ├── images/
		│   │   ├── fonts/
		│   └── index.html
		├── src/                  # Application source code
		│   ├── controllers/
		│   ├── models/
		│   ├── views/
		│   └── utilities/
		├── tests/                # Unit and integration tests
		├── docs/                 # Documentation (Markdown files)
		├── logs/                 # Server and application logs
		├── scripts/              # Scripts for deployment, setup, etc.
		└── temp/                 # Temporary/cache files


## Documentation Requirements
	- Include JSDoc comments for JavaScript/TypeScript.
	- Document complex functions with clear examples.
	- Maintain concise Markdown documentation.
	- Minimum docblock info: `param`, `return`, `throws`, `author`
    
## Database Requirements (SQLite 3.46+)
	- Leverage JSON columns, generated columns, strict mode, foreign keys, check constraints, and transactions.
    
## Security Considerations
	- Sanitize all user inputs thoroughly.
	- Parameterize database queries.
	- Enforce strong Content Security Policies (CSP).
	- Use CSRF protection where applicable.
	- Ensure secure cookies (`HttpOnly`, `Secure`, `SameSite=Strict`).
	- Limit privileges and enforce role-based access control.
	- Implement detailed internal logging and monitoring.
