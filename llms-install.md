# Installing the Flashloop MCP server

Flashloop is a hosted (remote) MCP server. Do not clone, build or run anything from this repository: it holds
documentation only.

1. Add this entry to the MCP settings file:

   ```json
   {
     "mcpServers": {
       "flashloop": {
         "type": "streamableHttp",
         "url": "https://mcp.flashloop.ai/mcp"
       }
     }
   }
   ```

2. No API key or environment variable is needed. On the first connection the server answers HTTP 401 with an
   OAuth challenge; the client opens a browser window where the user signs in to their Flashloop account.
3. After sign-in, call `flashloop_whoami` to confirm the connection and `flashloop_get_credits` to see the balance.

The user needs a Flashloop account (https://www.flashloop.ai). Generations spend the user's Flashloop credits, so
estimate a job with `flashloop_estimate_cost` before starting it when the user asks about cost.
