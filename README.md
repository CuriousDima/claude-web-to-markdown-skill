# Web to Markdown Skill

A Claude skill that converts web pages to Markdown format using Jina AI's reader service.

## Installation

1. Download [`web-to-markdown.skill`](https://github.com/CuriousDima/claude-web-to-markdown-skill/releases/download/0.2/web-to-markdown.skill)
2. In Claude, go to Skills settings and upload the file
3. **Important**: Allow Claude Desktop to call jina.ai:
   - Open "Settings"
   - Go to "Capabilities"
   - Add `*.jina.ai` to "Additional Allowed Domains"

## Usage

Once installed, you can ask Claude to convert web pages using natural language:

```
Convert https://example.com/article into markdown
```

```
Generate markdown from this website: https://blog.example.com/post
```

```
Turn this page into markdown: https://news.example.com/story
```

The skill recognizes various ways to request conversion:
- "Convert this page to markdown"
- "Generate markdown from this URL"
- "Create an MD file from this website"
- "Download this webpage as markdown"
- "Turn this page into a markdown file"

## How It Works

1. Claude extracts the URL from your request
2. The skill prepends `https://r.jina.ai/` to your URL
3. Uses `curl` to retrieve the converted Markdown
4. Saves the content to a `.md` file
5. Provides a link to download your file
