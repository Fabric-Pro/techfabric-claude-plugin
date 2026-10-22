# TechFabric for Claude Code

For TechFabric engineers who write for techfabric.com. The plugin adds the techfabric MCP server (https://www.techfabric.com/mcp), its commands and the techfabric-blog skill. Sign in once: run /mcp, pick the techfabric server, choose Authenticate and use your @techfabric.com Microsoft account.

Commands: /techfabric:write-post, /techfabric:write-case-study, /techfabric:check, /techfabric:preview, /techfabric:publish, /techfabric:revise, /techfabric:status, /techfabric:blog-post-template, /techfabric:case-study-template, /techfabric:linkedin-post, /techfabric:reddit-post, /techfabric:performance. Each one tells Claude the exact tool sequence and reads the house rules from the server's editorial_rules resource. Nothing is published until you say yes, and a hook asks you again before every publish_draft.

Install it from a shell: claude plugin marketplace add Fabric-Pro/techfabric-claude-plugin && claude plugin install techfabric@techfabric

If git isn't installed, from techfabric.com instead: claude plugin marketplace add https://www.techfabric.com/mcp-servers/harness/claude-code/marketplace.json && claude plugin install techfabric@techfabric

More: https://www.techfabric.com/mcp-servers#commands. Privacy: https://www.techfabric.com/mcp-servers#privacy
