# Exercise 7 - GitHub Copilot Spaces

#### Duration: 30 minutes

## 🎯 Learning Objectives

By the end of this exercise, you will:
- Understand what GitHub Copilot Spaces are and their benefits
- Create and configure multiple Copilot Spaces for different purposes
- Set up Spaces with specific goals, instructions, and context
- Complete development tasks using focused AI assistance in Spaces

## 🍳 Scenario: Collaborative Development at FlavorHub

Your team at FlavorHub is working on multiple simultaneous initiatives for the application:
- A security audit to ensure the recipe upload and pantry management systems are hardened against vulnerabilities
- New documentation for the API and component architecture
- Performance optimization for recipe search and filtering
- Accessibility improvements across the application

These are complex, multi-faceted projects that benefit from focused, dedicated AI assistance with specific context and goals. Your manager has asked you to explore GitHub Copilot Spaces as a way to organize these initiatives and collaborate more effectively with AI assistance.

## 🌟 Introduction to GitHub Copilot Spaces

**GitHub Copilot Spaces** are dedicated, persistent AI workspaces where you can:
- Define specific goals and instructions for a project or initiative
- Add relevant context files, issues, and documentation
- Have focused conversations with Copilot about a particular topic
- Collaborate with team members in a shared AI context

### Spaces vs. Regular Copilot Chat:

| Feature | Regular Chat | Copilot Spaces |
|---------|--------------|----------------|
| Context | Current workspace only | Custom files, repos, issues, docs |
| Instructions | General + repo instructions | Custom instructions per Space |
| Collaboration | Individual conversations | Shared team Spaces |

---

## 🎯 Step 1: Create Your First Space - Security Analysis

In this lab, you'll create TWO different Copilot Spaces to experience how they can be tailored for different purposes. Let's start with a Security Analysis Space.

### Instructions:

1. **Navigate to Copilot Spaces:**
   - Go to [https://github.com/copilot/spaces](https://github.com/copilot/spaces)

2. **Create a new Space:**
   - Click **"Create Space"** button

3. **Configure the Security Analysis Space:**

**Purpose**: Analyze and improve the security posture of the FlavorHub application.

**Basic Settings:**

1. **Space name**: `FlavorHub - Security Assessment`
2. **Owner**: Select your username
3. **Description**: `Implement security best practices for the FlavorHub application`

**Add Instructions:**

4. Click **"Instructions"**
5. Add the following instructions:

```markdown
You are a security expert helping to analyze and improve the security posture of a Spring Boot recipe management application. Focus on:

- Recipe upload and pantry management security vulnerabilities and mitigations
- Input validation and sanitization for REST APIs
- Authentication and authorization patterns
- XSS prevention in user-generated content and HTML templates
- Secure data handling and storage
- OWASP Top 10 web application security risks
- Spring Boot specific security best practices
- Thymeleaf template security

Provide specific code examples and security recommendations that follow industry standards and OWASP guidelines. Consider both server-side and client-side security measures.
```

7. Click **"Save"**

**Add Source Files:**

8. Click **"Add sources"** → **"Add files from repositories"**
9. Add the following files from your version of this repository:
   ```
   flavorhub/src/main/java/com/coveros/training/flavorhub/controller/RecipeController.java
   flavorhub/src/main/java/com/coveros/training/flavorhub/controller/UserPantryController.java
   flavorhub/src/main/resources/templates/index.html
   flavorhub/src/main/resources/application.properties
   ```

**Add Security Documentation:**

10. Click **"Add sources"** → **"Add text content"**
11. Add the following security reference:

Name: `Relevant OWASP Security Vulns`

```markdown
## OWASP Top 10 2025 - Key Security Risks for Web Applications

1. **A01 Broken Access Control** - Users can act outside of their intended permissions
2. **A02 Security Misconfiguration** - Missing appropriate security hardening
3. **A03 Software Supply Chain Failures** - Vulnerabilities or malicious changes in third-party code, tools, or dependencies
4. **A04 Cryptographic Failures** - Failures related to cryptography leading to sensitive data exposure
5. **A05 Injection** - User-supplied data is not validated, filtered, or sanitized
6. **A06 Insecure Design** - Risks related to design and architectural flaws
7. **A07 Authentication Failures** - Authentication and session management issues
8. **A08 Software or Data Integrity Failures** - Code and infrastructure integrity violations
9. **A09 Security Logging and Alerting Failures** - Insufficient logging, monitoring, and alerting
10. **A10 Mishandling of Exceptional Conditions** - Improper error handling, failing open, and logic errors

## Spring Boot Security Headers
- Content Security Policy (CSP)
- X-Frame-Options
- X-Content-Type-Options
- Referrer-Policy
- Permissions-Policy

## Data Input Security Considerations
- Request body validation using Bean Validation
- Path variable sanitization
- Query parameter validation
- File size limits for recipe images
- SQL injection prevention with JPA
- XSS prevention in Thymeleaf templates
```

12. Click **"Save"**

✅ **Checkpoint**: You've created your first Copilot Space! You should see it in your Spaces dashboard.

---

## 🎯 Step 1b: Create Your Second Space - Documentation Hub

Now let's create a second Space focused on documentation and API design. This demonstrates how you can organize different concerns into separate, focused workspaces.

### Instructions:

1. **Return to Copilot Spaces dashboard:**
   - Go to [https://github.com/copilot/spaces](https://github.com/copilot/spaces)

2. **Create another new Space:**
   - Click **"Create Space"** button

3. **Configure the Documentation Space:**

**Purpose**: Create comprehensive documentation and API design for the FlavorHub application.

**Basic Settings:**

1. **Space name**: `FlavorHub - Documentation Hub`
2. **Owner**: Select your username
3. **Description**: `Create comprehensive documentation and API design documentation for the FlavorHub application`

**Add Instructions:**

4. Click **"Instructions"**
5. Add the following instructions:

```markdown
You are a technical documentation expert and API designer helping to create comprehensive documentation for a Spring Boot recipe management application. Focus on:

- Clear, beginner-friendly component and service documentation
- API design and endpoint specifications
- Architecture decision records (ADRs)
- Code examples and usage patterns
- JavaDoc comments for classes and methods
- README and getting started guides
- HTML template documentation for the frontend
- Performance considerations

Provide well-structured, maintainable documentation that follows industry best practices. Use clear examples and diagrams where appropriate.
```

7. Click **"Save"**

**Add Source Files:**

8. Click **"Add sources"** → **"Add files from repositories"**
9. Add the following files from your version of this repository:
   ```
   flavorhub/src/main/java/com/coveros/training/flavorhub/controller/RecipeController.java
   flavorhub/src/main/java/com/coveros/training/flavorhub/service/RecipeService.java
   flavorhub/src/main/resources/templates/index.html
   README.md
   ```

**Add Documentation Templates:**

10. Click **"Add sources"** → **"Add text content"**
11. Add the following documentation template:

```markdown
## Component Documentation Template

### ComponentName

**Purpose**: [One sentence describing what this component does]

**Location**: `flavorhub/src/main/java/com/coveros/training/flavorhub/[path]/ComponentName.java`

#### Methods

| Method | Parameters | Returns | Description |
|--------|-----------|---------|-------------|
| methodName | type param | type | Description |

#### Usage Example

\`\`\`java
// Example usage
ComponentName component = new ComponentName();
component.methodName(param);
\`\`\`

#### Dependencies

- [Service 1]
- [Repository 1]

#### Related Components

- [Component 1]
- [Component 2]
```

12. Click **"Save"**

✅ **Checkpoint**: Excellent! You now have TWO specialized Copilot Spaces:
- **Security Assessment Space** - for security analysis and hardening
- **Documentation Hub Space** - for creating comprehensive documentation

You should see both spaces in your Copilot Spaces dashboard. Each Space has its own focused instructions and relevant context files.

---

## 💬 Step 2: Work Within Your Copilot Spaces

Now that your Spaces are configured, let's use them to accomplish specific goals. You'll work with each Space to see how the specialized context and instructions affect Copilot's responses.

### Instructions:

1. **Open your Security Assessment Space** from the Copilot Spaces dashboard

2. **Try these security-focused prompts:**

Create prompts to analyze the application for security vulnerabilities. Consider asking about:
- Recipe and pantry input validation
- REST API security risks
- HTML template XSS prevention
- Security headers configuration
- Security checklists based on OWASP Top 10

<details>
<summary>💡 Example Prompt</summary>

```
Analyze the RecipeController for potential security vulnerabilities. What risks should we address?
```

```
How can we implement input validation for recipe creation and pantry item additions?
```

```
Review the index.html template - are there any XSS vulnerabilities we should prevent?
```

```
What security headers should we configure in Spring Boot for this application?
```

```
Create a security checklist for the pantry management feature based on OWASP Top 10.
```
</details>

3. **Review the responses** - Notice how Copilot uses the security context and OWASP guidelines from your Space

4. **Have a multi-turn conversation** - Ask follow-up questions, request code examples, iterate on solutions

5. **Switch to your Documentation Hub Space:**
   - Return to your Spaces dashboard
   - Open the "FlavorHub - Documentation Hub" Space

6. **Try these documentation-focused prompts:**

Create prompts to generate documentation for the application. Consider asking for:
- JavaDoc comments for services and controllers
- API specifications
- Component usage guides
- Architecture decision records
- Getting started guides for developers

<details>
<summary>💡 Example Prompt</summary>

```
Generate comprehensive JavaDoc comments for the RecipeService class.
```

```
Create an API specification document for the recipe endpoints used in this application.
```

```
Write a usage guide for developers working with the RecipeController.
```

```
Generate an architecture decision record (ADR) for using Spring Boot and Thymeleaf in this project.
```

```
Create a getting started guide for new developers joining the FlavorHub project.
```
</details>

7. **Compare the experiences:**
   - Notice how each Space has different expertise based on its instructions
   - The Security Space focuses on vulnerabilities and OWASP standards
   - The Documentation Space provides clear, well-structured documentation
   - Each Space uses only the relevant files you added to its context

## 📝 Step 3: Manage and Organize Your Spaces

As you create more Spaces, organization becomes important.

### Best Practices:

1. **Use clear, descriptive names:**
   - ✅ "Recipe Upload - Security Hardening"
   - ❌ "Project A"

2. **Add comprehensive descriptions:**
   - Explain the Space's purpose
   - Include goals or success criteria
   - Note any specific constraints

3. **Keep instructions focused:**
   - Each Space should have a clear, specific purpose
   - Don't try to cover everything in one Space
   - Instructions should guide Copilot toward your specific needs

4. **Curate sources carefully:**
   - Add only relevant files and documentation
   - Too much context can dilute focus
   - Update sources as the project evolves


## 🏆 Exercise Wrap-up

Excellent work! You've mastered GitHub Copilot Spaces:
- ✅ Created TWO specialized Copilot Spaces with custom instructions
- ✅ Configured a Security Assessment Space with OWASP context
- ✅ Set up a Documentation Hub Space with documentation templates
- ✅ Added relevant context files and documentation to each Space
- ✅ Worked within Spaces for focused, goal-oriented AI assistance
- ✅ Understood collaboration features and best practices
- ✅ Learned to organize and manage multiple Spaces

### Reflection Questions:
1. **How do Spaces differ from regular Copilot Chat in your workflow?**
2. **What types of projects or tasks would benefit most from dedicated Spaces?**
3. **What was different about the responses from your Security Space vs. Documentation Space?**
4. **How might your team use Spaces for collaboration?**
5. **What instructions and context were most effective in your Spaces?**
6. **How would you organize Spaces for your current projects?**

### Key Takeaways:
- Spaces provide persistent, focused AI assistance for complex projects
- Each Space can have specialized instructions and curated context
- Custom instructions and relevant source files dramatically improve AI responses
- Different Spaces serve different purposes (security, docs, features, performance, etc.)
- Spaces enable better team collaboration and knowledge sharing
- Spaces are particularly valuable for long-running, complex initiatives

## Coming up next...

In the final lab, you'll learn about the GitHub Copilot Cloud Agent:
- Assign entire issues to Copilot for autonomous development
- Experience parallel development by working on multiple tasks simultaneously
- Monitor progress through session logs and review pull requests
- Scale your productivity with multiple concurrent agent tasks
