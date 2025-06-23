# Cursor Rules Collection

A curated collection of powerful `.mdc` rule files and configuration guides for Cursor AI editor to enhance your development workflow.

## 📚 What's Included

This repository contains specialized Cursor rules for:

- **TypeScript & React Development** - Best practices, patterns, and conventions
- **Next.js Applications** - App Router, performance, and SSR guidelines
- **UI/UX Development** - Tailwind CSS, component design, and styling patterns
- **Testing Strategies** - Unit, integration, and E2E testing approaches
- **Security Practices** - Secure development principles and vulnerability prevention
- **Code Quality** - Clean code guidelines, refactoring protocols, and standards
- **MCP Integration** - Model Context Protocol server configurations

## 🚀 Quick Setup

### Adding Rules to Cursor

1. **Download Rule Files**: Clone this repository or download individual `.mdc` files
2. **Place in Project Root**: Copy the relevant `.mdc` files to your project's root directory
3. **Cursor Auto-Detection**: Cursor will automatically detect and apply the rules when you open the project

#### Alternative: Global Rules Setup

For system-wide rules, place `.mdc` files in:

- **Windows**: `%APPDATA%\Cursor\User\globalStorage`
- **macOS**: `~/Library/Application Support/Cursor/User/globalStorage`
- **Linux**: `~/.config/Cursor/User/globalStorage`

### Configuring MCP Servers

Model Context Protocol (MCP) servers extend Cursor's capabilities with external tools and services.

#### Step 1: Create MCP Configuration File

**Option A: Use Repository Configuration** (Recommended)
Copy the included `mcp.json` file from this repository to your Cursor settings directory:

**Windows**: `%APPDATA%\Cursor\User\mcp.json`
**macOS**: `~/Library/Application Support/Cursor/User/mcp.json`
**Linux**: `~/.config/Cursor/User/mcp.json`

**Option B: Create Your Own**
Create a new `mcp.json` file in the same location with your custom server configurations.

#### Step 2: Repository MCP Configuration

This repository includes a pre-configured `mcp.json` file with powerful MCP servers:

```json
{
  "mcpServers": {
    "context7": {
      "command": "npx",
      "args": ["-y", "@upstash/context7-mcp"]
    },
    "sequential-thinking": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-sequential-thinking"]
    },
    "memory": {
      "command": "npx",
      "args": ["-y", "mcp-knowledge-graph", "--memory-path", "./memory.jsonl"],
      "autoapprove": [
        "create_entities",
        "create_relations",
        "add_observations",
        "delete_entities",
        "delete_observations",
        "delete_relations",
        "read_graph",
        "search_nodes",
        "open_nodes"
      ]
    },
    "puppeteer": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-puppeteer"]
    },
    "brave-search": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-brave-search"],
      "env": {
        "BRAVE_API_KEY": "KEY_HERE"
      }
    }
  }
}
```

#### Step 3: Server Descriptions

##### 🧠 **Context7** - Documentation and Library Access

Access up-to-date documentation for popular libraries and frameworks directly in Cursor.

##### 🤔 **Sequential Thinking** - Advanced Problem Solving

Enables step-by-step reasoning and complex problem-solving workflows within Cursor.

##### 💾 **Memory (Knowledge Graph)** - Persistent Context

Maintains a knowledge graph of your project, remembering entities, relationships, and observations across sessions.

##### 🌐 **Puppeteer** - Web Automation

Automate web interactions, testing, and scraping directly from Cursor.

##### 🔍 **Brave Search** - Real-time Web Search

Perform web searches and get real-time information without leaving your editor.

> **Note**: Requires a Brave Search API key. See the [API Key Setup](#brave-search-api-key-setup) section below for instructions.

#### Step 4: Additional Popular Servers

For additional functionality, you can extend the configuration:

```json
{
  "mcpServers": {
    "github": {
      "command": "docker",
      "args": ["run", "-i", "--rm", "-e", "GITHUB_PERSONAL_ACCESS_TOKEN"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "your_token_here"
      }
    },
    "linear": {
      "url": "https://mcp.linear.app/sse"
    },
    "postgres": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-postgres",
        "postgresql://localhost/mydb"
      ]
    }
  }
}
```

#### Step 5: Quick Setup

To use the repository's MCP configuration:

1. **Copy the `mcp.json` file** from this repository to your Cursor settings directory
2. **Configure API Keys**: Update the `BRAVE_API_KEY` in the brave-search server configuration
3. **Restart Cursor** to load the new MCP servers

**One-Click Installation Links** (for individual servers):

- **Context7**: [Add to Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=context7&config=eyJjb21tYW5kIjoibnB4IiwiYXJncyI6WyIteSIsIkB1cHN0YXNoL2NvbnRleHQ3LW1jcCJdfQ==)
- **Sequential Thinking**: [Add to Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=sequential-thinking&config=eyJjb21tYW5kIjoibnB4IiwiYXJncyI6WyIteSIsIkBtb2RlbGNvbnRleHRwcm90b2NvbC9zZXJ2ZXItc2VxdWVudGlhbC10aGlua2luZyJdfQ==)
- **Memory**: [Add to Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=memory&config=eyJjb21tYW5kIjoibnB4IiwiYXJncyI6WyIteSIsIm1jcC1rbm93bGVkZ2UtZ3JhcGgiLCItLW1lbW9yeS1wYXRoIiwiLi9tZW1vcnkuanNvbmwiXSwiYXV0b2FwcHJvdmUiOlsiY3JlYXRlX2VudGl0aWVzIiwiY3JlYXRlX3JlbGF0aW9ucyIsImFkZF9vYnNlcnZhdGlvbnMiLCJkZWxldGVfZW50aXRpZXMiLCJkZWxldGVfb2JzZXJ2YXRpb25zIiwiZGVsZXRlX3JlbGF0aW9ucyIsInJlYWRfZ3JhcGgiLCJzZWFyY2hfbm9kZXMiLCJvcGVuX25vZGVzIl19)
- **Puppeteer**: [Add to Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=puppeteer&config=eyJjb21tYW5kIjoibnB4IiwiYXJncyI6WyIteSIsIkBtb2RlbGNvbnRleHRwcm90b2NvbC9zZXJ2ZXItcHVwcGV0ZWVyIl19)
- **Brave Search**: [Add to Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=brave-search&config=eyJjb21tYW5kIjoibnB4IiwiYXJncyI6WyIteSIsIkBtb2RlbGNvbnRleHRwcm90b2NvbC9zZXJ2ZXItYnJhdmUtc2VhcmNoIl0sImVudiI6eyJCUkFWRV9BUElfS0VZIjoiS0VZX0hFUkUifX0=)

### Advanced Configuration

#### Privacy Settings

Enable Privacy Mode to prevent code storage:

```
Cursor Settings > General > Privacy Mode
```

#### Corporate Proxy Support

For corporate environments, disable HTTP/2:

```json
{
  "cursor.general.disableHttp2": true
}
```

#### Custom Ignore Patterns

Create a `.cursorignore` file in your project root:

```
# Ignore build directories
dist/
build/
node_modules/

# Ignore log files
*.log

# Ignore sensitive files
.env
config.json
```

### Brave Search API Key Setup

The Brave Search MCP server requires an API key to function. Here's how to get yours:

#### Step 1: Create Account

1. Visit [api-dashboard.search.brave.com/register](https://api-dashboard.search.brave.com/register)
2. Sign up for a new account or login if you already have one
3. Complete the registration process

#### Step 2: Choose a Plan

Brave Search API offers several pricing tiers:

- **Free Tier**: 2,000 queries per month (perfect for personal projects)
- **Paid Plans**: Starting from $3 per 1,000 queries for higher usage
- **Data for AI Plans**: Specialized plans for AI training and development

#### Step 3: Subscribe to Data for AI Plan

For MCP server usage, you need a "Data for AI" plan:

1. In the dashboard, navigate to the **Subscriptions** tab in the left menu
2. Select one of the **"Data for AI"** plans
3. Complete the subscription process

> **💡 Tip**: The free tier (2,000 queries/month) is often sufficient for development and personal use.

#### Step 4: Generate API Key

1. In the dashboard, go to **API Keys** in the left menu
2. Click **"Add API Key"** to generate a new key
3. Copy the generated API key
4. Add it to your `mcp.json` configuration:

```json
{
  "mcpServers": {
    "brave-search": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-brave-search"],
      "env": {
        "BRAVE_API_KEY": "your_actual_api_key_here"
      }
    }
  }
}
```

#### Security Best Practices

- Never commit API keys to version control
- Store keys in environment variables when possible
- Regenerate keys if they may have been compromised
- Monitor your usage in the Brave dashboard

For more information, visit the [official Brave Search API documentation](https://brave.com/search/api/).

## 📋 Rule Categories

### Core Development Rules

- **`typescript-react-patterns.mdc`** - TypeScript + React best practices
- **`next-js.mdc`** - Next.js App Router and performance guidelines
- **`styling-patterns.mdc`** - Tailwind CSS and component styling
- **`software-standards.mdc`** - Clean code principles and conventions

### Quality & Testing

- **`testing-patterns.mdc`** - Comprehensive testing strategies
- **`testing.mdc`** - Unit and integration testing guidelines
- **`code-refactoring-protocol.mdc`** - Systematic refactoring approaches

### Security & Architecture

- **`secure-development-principles.mdc`** - Security-first development
- **`secure-nodejs-development.mdc`** - Node.js security practices
- **`secure-mcp-usage.mdc`** - Safe MCP server configuration

### Advanced Features

- **`streaming-components.mdc`** - Real-time component patterns
- **`expert-designer.mdc`** - UI/UX design principles
- **`development-reasoning.mdc`** - Problem-solving methodologies

## 🔧 Troubleshooting

### Rule Files Not Loading

1. Ensure `.mdc` files are in the project root
2. Restart Cursor after adding new rules
3. Check file permissions and encoding (UTF-8)

### MCP Server Issues

1. Verify `mcp.json` syntax with a JSON validator
2. Check server logs:
   - **Windows**: `C:\Users\<username>\AppData\Roaming\Cursor\logs`
   - **macOS/Linux**: Check Cursor > Help > Show Logs
3. Ensure required environment variables are set
4. Test server connectivity manually

### Common Fixes

- **Tab/Cmd+K not working**: Enable `"cursor.general.disableHttp2": true`
- **Server not starting**: Check command paths and permissions
- **Authentication errors**: Verify API keys and tokens

## 🤝 Contributing

We welcome contributions! To add new rules or improve existing ones:

1. Fork this repository
2. Create a feature branch
3. Add your `.mdc` rule file with clear documentation
4. Submit a pull request with examples and use cases

### Rule File Guidelines

- Use descriptive filenames (e.g., `python-fastapi-patterns.mdc`)
- Include comprehensive comments and examples
- Follow the established format and structure
- Test rules with real projects before submitting

## 📖 Resources

- [Cursor Documentation](https://docs.cursor.com)
- [MCP Specification](https://spec.modelcontextprotocol.io)
- [Available MCP Servers](https://github.com/modelcontextprotocol/servers)
- [Cursor Community Discord](https://discord.gg/cursor)

## 📄 License

This collection is open source and available under the MIT License. Feel free to use, modify, and distribute these rules in your projects.

---

_Happy coding with Cursor! 🎯_
