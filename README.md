# Flask Web App Template Repository

This is a **Template Repository** designed to help you quickly start new web application projects using GitHub Copilot. It provides a structured starting point with a comprehensive Product Requirements Document (PRD) template and best practices for Flask-based web applications.

**Why This Tech Stack?** This template uses Flask, Bootstrap, jQuery, SQLite, and Fly.io specifically chosen for **simplicity and speed of development**. These technologies work exceptionally well with GitHub Copilot, providing reliable code generation and suggestions that help you build faster. Flask's lightweight nature, Bootstrap's proven UI components, jQuery's straightforward DOM manipulation, SQLite's zero-configuration database, and Fly.io's simple deployment make this stack ideal for rapid prototyping and getting your ideas to production quickly.

*Note: This is the default stack, but you can work with Copilot in Step 4 to adjust any of these choices based on your specific project needs.*

## 🚀 Getting Started

### Step 1: Create Your Repository

1. **Above the file list, click "Use this template"**
2. **Select "Create a new repository"**
3. Give your new repository a name and description
4. Choose public or private visibility
5. Click "Create repository from template"

### Step 2: Clone Your New Repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
cd YOUR_REPO_NAME
```

## 🤖 Using GitHub Copilot to Build Your App

### Step 3: Customize Copilot Instructions (Optional)

Adjust the development guidelines in `.github/copilot-instructions.md` to match your specific project needs, coding style preferences, or additional requirements.

### Step 4: Update Your PRD with Copilot

Open `PRD.md` and ask GitHub Copilot to help you customize it for your specific application. Use this prompt structure:

```
I want to create a [TYPE OF APP] that [DESCRIPTION OF WHAT IT DOES]. 

Key details about my app:
- [Add any specific features, user types, or requirements]
- [Mention any specific integrations or external APIs needed]
- [Note any particular design or UX requirements]

Please help me update this PRD template for my project. Specifically:

1. Fill in all the bracketed placeholders with details specific to my app. You may add sections if needed, or remove ones we have decided to eliminate (verify this with me first).
2. Validate and adjust the tech stack selection: Flask, Bootstrap, jQuery, SQLite, fly.io - let me know if any of these should be changed for my use case
3. Brainstorm with me on any key decisions or adjustments I should consider before finalizing the PRD
4. Make sure the scope and features are appropriate for a first version

Let's discuss any recommendations before you make the actual changes to the file.

If the tech stack changes, also suggest changes to copilot-instructions.md
```

### Step 5: Review and Finalize

1. **Review the updated PRD** carefully
2. **Make any manual adjustments** you feel are necessary
3. **Ensure the scope is realistic** for your timeline and resources

### Step 6: Implement Your Application

Once your PRD is finalized, tell GitHub Copilot:

```
Please implement the application described in my PRD.md file. Create all necessary files, folder structure, and code to build a working application that meets the requirements.

Also:
- Copy .env.example to .env and adjust the environment variables for my specific project, reminding me to update .env with my secrets etc
- Create any additional configuration files needed for the tech stack
```

## 📋 What's Included

- **PRD.md**: Comprehensive Product Requirements Document template
- **.github/copilot-instructions.md**: Development guidelines and best practices for Copilot
- **.env.example**: Template for environment variables (copy to `.env` and adjust for your project)
- **Template structure** ready for Flask + Bootstrap + jQuery applications

## 🛠 Default Tech Stack

This template is optimized for:
- **Backend**: Flask (Python)
- **Frontend**: Bootstrap 5 + jQuery
- **Database**: SQLite (optional, stateless preferred)
- **Deployment**: Fly.io
- **Environment**: .env configuration

## 💡 Tips for Success

1. **Be specific** about your app's purpose and target users
2. **Consider starting simple** - you can always add features later
3. **Think about whether you actually need a database** - stateless apps are often simpler
4. **Review the generated code** and ask Copilot to explain anything unclear
5. **Test locally** before deploying to production

## 🤝 Contributing

This template is designed to evolve based on common patterns and best practices. Feel free to submit issues or pull requests to improve the template for everyone.

---

**Ready to build something amazing?** Start by creating your repository from this template and customizing your PRD! 🚀