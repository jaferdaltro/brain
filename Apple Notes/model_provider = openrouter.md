---
apple-notes-id: 194B6A9A-76AE-4BEA-94B9-8FBFE8FFE7C3
---
```
model_reasoning_effort = "high"
model="~openai/gpt-sol-latest"

[model_providers.openrouter]
name = "openrouter"
base_url="https://openrouter.ai/api/v1"

[model_providers.openrouter.auth]
command = "sh"
args = ["-c", "echo $OPENROUTER_API_KEY"]


# model_reasoning_effort = "low"
# notify = [ "/Users/jafer/.codex/computer-use/Codex Computer Use.app/Contents/SharedSupport/SkyComputerUseClient.app/Contents/MacOS/SkyComputerUseClient", "turn-ended" ]
# model = "gemini/gemini-2.5-flash"
# model_provider = "9router"

# [model_providers.openrouter]
# name = "openrouter"
# base_url = "https://openrouter.ai/api/v1"

# [model_providers.openrouter.auth]
# command = "sh"
# args = [ "-c", "echo $OPENROUTER_API_KEY" ]

# [model_providers.9router]
# name = "9Router"
# base_url = "http://127.0.0.1:20128/v1"
# wire_api = "responses"

# [model_providers.9router.http_headers]
# Authorization = "Bearer sk-9ff845025e1ace23-mqm951-9921d093"

# [agents]
# default_subagent_model = "gemini/gemini-3-flash-preview"

# [projects."/Users/jafer/dev/collegium"]
# trust_level = "trusted"

# [projects."/Users/jafer"]
# trust_level = "trusted"

# [projects."/Users/jafer/dev/musclebuddy-fit"]
# trust_level = "trusted"

# [projects."/Users/jafer/dev/transitando"]
# trust_level = "trusted"

# [tui.model_availability_nux]
# "gpt-5.6-sol" = 4

# [mcp_servers.rubymine]
# url = "http://127.0.0.1:64502/stream"

# [mcp_servers.node_repl]
# args = []
# command = "/Applications/Codex.app/Contents/Resources/cua_node/bin/node_repl"
# startup_timeout_sec = 120

[mcp_servers.node_repl.env]
NODE_REPL_NATIVE_PIPE_CONNECT_TIMEOUT_MS = "1000"
NODE_REPL_NODE_MODULE_DIRS = "/Applications/Codex.app/Contents/Resources/cua_node/lib/node_modules"
NODE_REPL_NODE_PATH = "/Applications/Codex.app/Contents/Resources/cua_node/bin/node"
NODE_REPL_TRUSTED_CODE_PATHS = "/Users/jafer/.codex:/Applications/Codex.app/Contents/Resources/cua_node/lib/node_modules"
CODEX_HOME = "/Users/jafer/.codex"
BROWSER_USE_AVAILABLE_BACKENDS = "chrome,iab"
BROWSER_USE_TINYSKY_ENABLED = "1"
NODE_REPL_INSTRUCTIONS_USE_CASE_BROWSER = ""
NODE_REPL_INSTRUCTIONS_USE_CASE_CHROME = ""
NODE_REPL_INSTRUCTIONS_USE_CASE_COMPUTER_USE = ""
BROWSER_USE_CODEX_APP_BUILD_FLAVOR = "prod"
BROWSER_USE_CODEX_APP_VERSION = "26.901.51231"
NODE_REPL_TRUSTED_SERVICES = "{\"browser\":\"/Users/jafer/.codex/plugins/cache/openai-bundled/browser/26.901.51231/scripts/browser-service.mjs\",\"sky\":\"@oai/sky/service\"}"
SKY_CUA_SERVICE_PATH = "/Users/jafer/.codex/computer-use/Codex Computer Use.app"
CODEX_CLI_PATH = "/Applications/Codex.app/Contents/Resources/codex"

[mcp_servers.computer-use]
command = "./Codex Computer Use.app/Contents/SharedSupport/SkyComputerUseClient.app/Contents/MacOS/SkyComputerUseClient"
args = [ "mcp" ]
cwd = "."
enabled = false

[desktop]
followUpQueueMode = "steer"

[marketplaces.openai-bundled]
source_type = "local"
source = "/Users/jafer/.codex/.tmp/bundled-marketplaces/openai-bundled"

[marketplaces.openai-primary-runtime]
source_type = "local"
source = "/Users/jafer/.cache/codex-runtimes/codex-primary-runtime/plugins/openai-primary-runtime"

[plugins."codex-app-tools@openai-bundled"]
enabled = true

[plugins."browser@openai-bundled"]
enabled = true

[plugins."unified-computer-use@openai-bundled"]
enabled = true

[plugins."visualize@openai-bundled"]
enabled = true

[plugins."computer-use@openai-bundled"]
enabled = true

[plugins."documents@openai-primary-runtime"]
enabled = true

[plugins."pdf@openai-primary-runtime"]
enabled = true

[plugins."spreadsheets@openai-primary-runtime"]
enabled = true

[plugins."presentations@openai-primary-runtime"]
enabled = true

[plugins."template-creator@openai-primary-runtime"]
enabled = true











```