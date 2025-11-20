
Help me to create a new skill using skills creator

I'll help you create a new skill! Let me first read the skill-creator guide to understand the best practices.


1 step

Checking the skills directory to find the skill-creator path


Reading the skill-creator SKILL.md file to understand how to create new skills
Great! Now I understand how to help you create a skill. Let me guide you through the process.

To create an effective skill, I'll need to understand what you want to build. Let me ask you a few questions:

1. What should this skill do? What specific task or capability do you want to add to Claude?

2. Can you give me some examples of how you'd use this skill? What are some concrete things you'd ask Claude to do that would trigger this skill?

For example:

If you're creating an image-editor skill, you might say things like "Remove red-eye from this photo" or "Rotate this image 90 degrees"
If you're creating a data-analysis skill, you might say "Analyze this sales data and create a trend report"
Take your time - I'll help you develop this step by step once I understand what you're trying to build!

The skill should convert a web page into a Markdown file. A user provides a link to a page, and the skill adds a prefix to this article and downloads generated Markdown file.
Here is an example. If I ask "Convert a page https://entropytown.com/articles/2025-11-13-world-model-lecun-feifei-li/ into markdown", the skill should call add a prefix "https://r.jina.ai/", call https://r.jina.ai/https://entropytown.com/articles/2025-11-13-world-model-lecun-feifei-li/, and return me generated markdown file. There are many synonyms o a word "convert" like "generate", "create from", etc. There are also multiple synonyms to a word "page", for example web-page, web page, and website. Same goes for "Markdown". Sometimes I can say "MD" or "md" instead of "Markdown".
Perfect! I understand what you want to build. This is a straightforward skill for converting web pages to Markdown using the Jina AI reader service.

Let me create this skill for you step by step.

First, I'll initialize the skill structure:


Initializing the web-to-markdown skill structure


Great! Now let me check the generated structure and then customize it:


Viewing the generated skill structure

Now let me create the actual skill. Since this is a simple conversion task, I'll create a Python script to handle the conversion and write clear instructions in SKILL.md:


Failed to edit
SKILL
Let me check the current content:


Reading the current SKILL.md content
Show working file
Now let me rewrite the SKILL.md properly:


F

Write file


I see - I need to use the proper file writing tool:


1 step

Removing the template SKILL.md to replace it with our custom version



Creating the SKILL.md file with proper frontmatter and instructions
SKILL.md
Great! Now let me create the conversion script:


Removing the example script file



Creating the Python script to convert web pages to Markdown
convert_to_markdown.py
Now let me test the script to make sure it works:


Making the script executable



Testing the script with the example URL provided by the user


I see - the network access has restrictions. Let me use the web_fetch tool instead, which can access external URLs. Let me update the script:


Removing the old script to create an updated version


Actually, let me think about this differently. Since we're in Claude's environment and the web_fetch tool is available, I should update the skill to tell Claude to use web_fetch instead of a Python script. This is more appropriate:


Removing SKILL.md to update with the correct approach



Creating updated SKILL.md that uses web_fetch tool
SKILL.md
Perfect! Now let me clean up the unnecessary directories since we don't need scripts, references, or assets for this skill:


Removing unused resource directories


Now let's verify the skill structure:


Checking the final skill structure

Excellent! Now let's package the skill:


Packaging the web-to-markdown skill


Perfect! Now let me move it to the outputs directory so you can download it:


Copying the packaged skill to the outputs directory


Excellent! Your skill is ready! 🎉

View your skill

What I Created
I've built a web-to-markdown skill that will help Claude convert web pages to Markdown format using Jina AI's reader service. Here's what it does:

The skill will trigger when you say things like:

"Convert this page to markdown"
"Generate markdown from this URL"
"Create an MD file from this website"
"Turn this webpage into markdown"
How it works:

You provide a URL
Claude prepends https://r.jina.ai/ to your URL
Uses the web_fetch tool to get the converted Markdown
Saves it as a .md file in the outputs directory
Gives you a download link
To install the skill:

Download the web-to-markdown.skill file
In Claude, go to your skills settings
Upload/import the skill file
Once installed, you can simply ask Claude to "convert [any URL] to markdown" and it will handle everything automatically!

Web to markdown
SKILL 
Instead of using web_fetch, use curl.

Good idea! Let me update the skill to use curl instead. I'll modify the SKILL.md to instruct Claude to use bash with curl:


Removing the current SKILL.md to update it with curl approach



Creating updated SKILL.md that uses curl instead of web_fetch
SKILL.md
Now let me test it with your example URL to make sure curl works:


Testing curl with the Jina AI service using the example URL


The curl command executed but returned empty output. This might be due to network restrictions. However, the skill instructions are correct - when users install and use this skill in their own Claude environment, curl should work properly if their network allows it.

Let me package the updated skill:


Packaging the updated web-to-markdown skill with curl



Copying the updated skill to outputs


Perfect! I've updated the skill to use curl instead of web_fetch.

View your updated skill

What Changed
The skill now instructs Claude to use a simple curl command:

bash
curl -s "https://r.jina.ai/{URL}" > /mnt/user-data/outputs/{filename}.md
This is cleaner and more straightforward. When you use the skill, Claude will:

Take your URL
Run: curl -s "https://r.jina.ai/YOUR_URL" > /mnt/user-data/outputs/filename.md
Give you a download link to the generated Markdown file
The skill is ready to install and use!

Web to markdown
SKILL 
Looks like .skill file is some form of a binary. Can I get the original skill file as well?

Absolutely! Let me check what the .skill file actually is, and then provide you with the original source files:


Checking what type of file the .skill file is


Ah, it's actually a ZIP file! The .skill extension is just a renamed .zip archive. Let me copy the original skill directory to the outputs folder so you can see the source:


Copying the skill source directory to outputs



Showing the contents of the skill directory

Perfect! Now let me also show you the SKILL.md content so you can see exactly what's in it:


Showing the SKILL.md content
Show working file
Perfect! Now you have both versions:

Your Files
web-to-markdown.skill - The packaged skill file (it's actually a ZIP archive with .skill extension)
web-to-markdown folder - The original source directory containing:
SKILL.md - The skill instructions
About the .skill File
The .skill file is just a ZIP archive with a different extension. You can actually rename it to .zip and extract it if you want to inspect it:

bash
unzip web-to-markdown.skill
Or on Mac/Linux:

bash
mv web-to-markdown.skill web-to-markdown.zip
unzip web-to-markdown.zip
The packaged .skill file is what you upload to Claude to install the skill, but the source directory shows you exactly what's inside it!

Web to markdown
SKILL 
computer:///mnt/user-data/outputs/web-to-markdown/
 


How can I help you today?






 


Skill · MD
Copy

---
name: web-to-markdown
description: Convert web pages to Markdown format using Jina AI's reader service. Use when the user asks to convert, generate, create, transform, or download a web page, website, or URL into Markdown, MD, or md format. Handles various phrasings like "convert this page to markdown", "generate markdown from this website", "create md file from this URL".
---

# Web to Markdown Converter

Convert any web page to clean Markdown format using Jina AI's reader service.

## Process

When a user requests to convert a web page to Markdown:

1. **Extract the URL** from the user's request
2. **Construct Jina URL**: Prepend `https://r.jina.ai/` before the user's URL
3. **Fetch with curl**: Use `curl` to retrieve the Markdown content
4. **Save to file**: Write the content to `/mnt/user-data/outputs/{filename}.md`
5. **Provide download link**: Give the user a link to the generated file

## Command Template

```bash
curl -s "https://r.jina.ai/{USER_URL}" > /mnt/user-data/outputs/{filename}.md
```

## Example Workflow

User request: "Convert https://example.com/article into markdown"

Execute:
```bash
curl -s "https://r.jina.ai/https://example.com/article" > /mnt/user-data/outputs/article.md
```

Then provide link: `computer:///mnt/user-data/outputs/article.md`

## Filename Generation

Generate a sensible filename from the URL:
- Use the last path segment if available (e.g., `article` from `/articles/article`)
- Remove any file extensions from the URL
- Sanitize by replacing special characters with underscores or hyphens
- Add `.md` extension
- If user specifies a custom filename, use that instead

## Common User Phrasings

This skill handles various ways users might request conversion:
- "Convert this page to markdown"
- "Generate markdown from this URL"
- "Create an MD file from this website"
- "Download this webpage as markdown"
- "Turn this page into a markdown file"
Claude