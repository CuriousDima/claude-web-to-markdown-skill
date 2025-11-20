# Web to Markdown Skill

A Claude skill that converts web pages to Markdown format using Jina AI's reader service.

## 📖 Description

This skill enables Claude to convert any web page into clean, readable Markdown format. Simply provide a URL, and Claude will fetch the converted content and save it as a downloadable `.md` file.

## ✨ Features

- Convert any web page to Markdown format
- Uses Jina AI's reader service (`https://r.jina.ai/`)
- Automatic filename generation from URLs
- Supports custom filenames
- Handles multiple phrasings and synonyms

## 🚀 Installation

### Option 1: Direct Installation (Recommended)

1. Download the pre-packaged skill file: [`web-to-markdown.skill`](./web-to-markdown.skill)
2. In Claude, go to your Skills settings
3. Click "Add Skill" or "Import Skill"
4. Upload the `web-to-markdown.skill` file

### Option 2: From Source

1. Clone this repository
2. Navigate to the `web-to-markdown` directory
3. Package the skill using Claude's skill packaging tools
4. Install the generated `.skill` file in Claude

## 💬 Usage

Once installed, you can ask Claude to convert web pages using natural language:

### Examples

```
Convert https://example.com/article into markdown
```

```
Generate markdown from this website: https://blog.example.com/post
```

```
Create an MD file from https://docs.example.com
```

```
Turn this page into markdown: https://news.example.com/story
```

### Supported Phrasings

The skill recognizes various ways to request conversion:
- "Convert this page to markdown"
- "Generate markdown from this URL"
- "Create an MD file from this website"
- "Download this webpage as markdown"
- "Turn this page into a markdown file"

You can use synonyms like:
- **Convert**: generate, create, transform, download
- **Page**: webpage, web page, website, URL
- **Markdown**: MD, md

## 🔧 How It Works

1. **URL Extraction**: Claude extracts the URL from your request
2. **Jina AI Service**: Prepends `https://r.jina.ai/` to your URL
3. **Fetch Content**: Uses `curl` to retrieve the converted Markdown
4. **Save File**: Writes the content to a `.md` file
5. **Download Link**: Provides a link to download your file

### Technical Details

The skill uses this command pattern:
```bash
curl -s "https://r.jina.ai/{YOUR_URL}" > /mnt/user-data/outputs/{filename}.md
```

## 📁 Repository Structure

```
.
├── web-to-markdown/          # Skill source directory
│   └── SKILL.md              # Skill instructions and metadata
├── web-to-markdown.skill     # Pre-packaged skill file (ready to install)
├── README.md                 # This file
└── LICENSE                   # License information
```

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Make your changes to the `web-to-markdown/SKILL.md` file
4. Test the skill with Claude
5. Commit your changes (`git commit -am 'Add improvement'`)
6. Push to the branch (`git push origin feature/improvement`)
7. Open a Pull Request

### Ideas for Contributions

- Add error handling improvements
- Support additional output formats
- Add configuration options
- Improve filename sanitization
- Add examples and documentation

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Jina AI](https://jina.ai/) for providing the web-to-markdown reader service
- [Anthropic](https://www.anthropic.com/) for Claude and the Skills system

## 📮 Support

If you encounter any issues or have questions:

1. Check the [Issues](../../issues) page
2. Open a new issue with details about your problem
3. Include the URL you're trying to convert and any error messages

## 🔗 Links

- [Jina AI Reader Documentation](https://jina.ai/reader/)
- [Claude Skills Documentation](https://docs.anthropic.com/)

---

**Made with ❤️ for the Claude community**
