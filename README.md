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

Create or edit `mcp.json` in your Cursor settings directory:

**Windows**: `%APPDATA%\Cursor\User\mcp.json`
**macOS**: `~/Library/Application Support/Cursor/User/mcp.json`
**Linux**: `~/.config/Cursor/User/mcp.json`

#### Step 2: Basic MCP Server Configuration

```json
{
  "mcpServers": {
    "postgres": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-postgres",
        "postgresql://localhost/mydb"
      ],
      "env": {
        "DB_USER": "your_username"
      }
    },
    "filesystem": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "/path/to/allowed/directory"
      ]
    }
  }
}
```

#### Step 3: Popular MCP Servers

##### Development Tools

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
    "stripe": {
      "command": "npx",
      "args": ["-y", "@stripe/mcp", "--tools=all"],
      "env": {
        "STRIPE_SECRET_KEY": "your_stripe_key"
      }
    }
  }
}
```

##### Remote Services

```json
{
  "mcpServers": {
    "linear": {
      "url": "https://mcp.linear.app/sse"
    },
    "figma": {
      "url": "http://127.0.0.1:3845/sse"
    },
    "notion": {
      "url": "https://mcp.notion.com/mcp"
    }
  }
}
```

#### Step 4: One-Click Installation Links

For quick MCP server installation, you can use these deep links:

- **PostgreSQL**: [Add to Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=postgres&config=eyJjb21tYW5kIjoibnB4IiwiYXJncyI6WyIteSIsIkBtb2RlbGNvbnRleHRwcm90b2NvbC9zZXJ2ZXItcG9zdGdyZXMiLCJwb3N0Z3JlY3FsOi8vbG9jYWxob3N0L215ZGIiXX0=)
- **GitHub Integration**: [Add to Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=github&config=eyJjb21tYW5kIjoiZG9ja2VyIiwgImFyZ3MiOlsicnVuIiwgIi1pIiwgIi0tcm0iLCAiLWUiLCAiR0lUSFVCX1BFUlNPTkFMX0FDQ0VTU19UT0tFTiJdfQ==)

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
