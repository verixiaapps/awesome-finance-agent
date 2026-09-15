# Awesome Finance Agent

A curated list of finance agent SDKs, MCP tools, wallet infrastructure, safeguards, simulation systems, security standards, and integration layers for building safer financial agents.

It covers the core building blocks behind finance agents, including execution SDKs, wallet and signing stacks, policy and safeguard layers, transaction simulation and preview systems, security eval tooling, observability platforms, and the protocols that connect them.

## Contents

- [Awesome Finance Agent](#awesome-finance-agent)
  - [Contents](#contents)
  - [Top Picks](#top-picks)
  - [Execution](#execution)
    - [Agent Wallet SDKs and Chain Kits](#agent-wallet-sdks-and-chain-kits)
    - [MCP Servers and Tool Surfaces](#mcp-servers-and-tool-surfaces)
    - [Exchanges, Brokerages, and Payments](#exchanges-brokerages-and-payments)
  - [Wallets and Signing](#wallets-and-signing)
  - [Safety and Guardrails](#safety-and-guardrails)
  - [Simulation and Validation](#simulation-and-validation)
  - [Security Testing and Evals](#security-testing-and-evals)
  - [Observability and Audit](#observability-and-audit)
  - [Standards and Protocols](#standards-and-protocols)
  - [Frameworks and Integration Layers](#frameworks-and-integration-layers)
  - [Adjacent Infrastructure](#adjacent-infrastructure)
  - [Design Patterns](#design-patterns)
  - [Contributing](#contributing)

## Top Picks

Quick starting points if you want a short list of the most useful projects in the space.

| Project | Category | Scope | Why it stands out |
| --- | --- | --- | --- |
| [Coinbase AgentKit](https://github.com/coinbase/agentkit) | Execution | Crypto | One of the clearest agent-to-wallet reference implementations. |
| [CCXT](https://github.com/ccxt/ccxt) | Execution | Crypto / fintech | The most practical exchange adapter layer for trading agents. |
| [Safe](https://safe.global/) | Wallet / safety | Crypto | Strong base for spend limits, approvals, and controlled execution. |
| [Tenderly](https://docs.tenderly.co/simulations/quickstart) | Simulation | Crypto | Pre-sign simulation and preview are core finance-agent safety primitives. |
| [Open Policy Agent](https://www.openpolicyagent.org/) | Safety | General | Strong fit for a policy gateway between reasoning and signing. |
| [Promptfoo](https://github.com/promptfoo/promptfoo) | Eval | General | Practical way to regression-test finance-agent tool behavior. |
| [Phoenix](https://github.com/Arize-ai/phoenix) | Observability | General | Open-source tracing and evaluation for production agent systems. |

## Execution

Execution tools are the action layer. They let agents trade, transfer, swap, pay, or interact with onchain and exchange systems.

### Agent Wallet SDKs and Chain Kits

| Project | Primary role | Scope | What it enables | Why it matters |
| --- | --- | --- | --- | --- |
| [Coinbase AgentKit](https://github.com/coinbase/agentkit) | Agent wallet SDK | Crypto | Gives AI agents wallets and onchain actions. | Reference implementation for wallet-enabled agents. |
| [Solana Agent Kit](https://github.com/sendaifun/solana-agent-kit) | Chain action kit | Crypto | Solana swaps, transfers, token ops, and related actions. | High-signal example of chain-specific action packaging. |
| [Sui Agent Kit](https://github.com/getnimbus/sui-agent-kit) | Chain action kit | Crypto | Sui DeFi and token workflows for agents. | Shows the same abstraction pattern beyond EVM and Solana. |
| [Starknet Agent Kit](https://github.com/kasarlabs/snak) | Chain action kit | Crypto | Agent development on Starknet. | Relevant for non-EVM account models and Cairo ecosystems. |
| [Polkadot AI Agent Kit](https://github.com/elasticlabs-org/polkadot-agent-kit) | Chain action kit | Crypto | Agent tooling for Polkadot-SDK chains. | Useful for tracking multi-chain patterns outside EVM norms. |

### MCP Servers and Tool Surfaces

| Project | Primary role | Scope | What it enables | Why it matters |
| --- | --- | --- | --- | --- |
| [MCP Crypto Wallet EVM](https://github.com/dcSpark/mcp-cryptowallet-evm) | Wallet MCP server | Crypto | Wallet creation, balances, sends, and contract calls via MCP. | Canonical example of a wallet exposed as a tool surface. |
| [Solana MCP Server](https://github.com/sendaifun/solana-mcp) | Chain MCP server | Crypto | Standardized Solana actions for MCP-native agents. | Clear path from chain kit to MCP interface. |
| [Jupiter MCP Server](https://github.com/dcSpark/mcp-server-jupiter) | DEX MCP server | Crypto | Quotes, swap transaction building, and swap execution. | Good archetype for finance-specific tool packaging. |
| [Blockscout MCP Server](https://github.com/blockscout/mcp-server) | Explorer MCP server | Crypto | Explorer-backed data and contract inspection tools. | Helps agents inspect state and audit transactions. |
- [HostDeFi](https://hostdefi.com/api/v1/mcp) - Hosted Streamable HTTP MCP server: free `scan_token` tool returns A+–F token-safety grades across Solana and 7 EVM chains; paid tools settle per call in USDC via x402.

### Exchanges, Brokerages, and Payments

| Project | Primary role | Scope | What it enables | Why it matters |
| --- | --- | --- | --- | --- |
| [CCXT](https://github.com/ccxt/ccxt) | Exchange adapter | Crypto / fintech | Unified trading and market-data access across many venues. | The most realistic substrate for LLM trading agents. |
| [Alpaca-py](https://github.com/alpacahq/alpaca-py) | Brokerage SDK | Fintech / crypto | Brokerage and market-data flows, including paper trading. | Useful on-ramp to equities-oriented agent workflows. |
| [Binance Connector Python](https://github.com/binance/binance-connector-python) | Exchange SDK | Crypto | Official Binance API access. | Reliable official SDK option for exchange execution. |
| [WalletConnect Agent SDK](https://github.com/WalletConnect/agent-sdk) | Payments tooling | Crypto | Agent-oriented WalletConnect Pay flows. | Tracks agent payment primitives in the wallet ecosystem. |

## Wallets and Signing

Wallet and signing infrastructure controls how an agent gets account access, signs transactions, and enforces boundaries around custody and permissions.

| Project | Primary role | Scope | What it enables | Why it matters |
| --- | --- | --- | --- | --- |
| [Privy](https://www.privy.io/) | Embedded wallets | Crypto | Programmable wallets for product and agent experiences. | Important embedded-wallet option for AI-native apps. |
| [langchain-privy](https://github.com/privy-io/langchain-privy) | Wallet integration | Crypto | Wallet management and signing inside LangChain flows. | Shows what wallet tooling looks like in agent code. |
| [Turnkey](https://github.com/tkhq/sdk) | Key management | Crypto | Programmatic signer and key-management APIs. | Common pattern for controlled signing infrastructure. |
| [Fireblocks SDK JS](https://github.com/fireblocks/fireblocks-sdk-js) | Institutional custody | Crypto | Custody and signing workflows for institutional systems. | Important when finance agents touch policy-heavy operations. |
| [Safe Core](https://github.com/safe-global/safe-core-sdk) | Smart accounts | Crypto | Safe smart-account integration and controlled execution. | Strong base for approvals and spend controls. |
| [ZeroDev](https://github.com/zerodevapp/sdk) | Smart accounts | Crypto | ERC-4337 smart accounts and agent-friendly permissions. | Frequently referenced for session keys and modular auth. |
| [Alchemy Account Kit](https://github.com/alchemyplatform/aa-sdk) | Smart accounts | Crypto | Smart-account execution, user ops, and account plumbing. | Major production AA stack. |
| [permissionless.js](https://github.com/pimlicolabs) | ERC-4337 utilities | Crypto | User operation and bundler utilities for custom flows. | Useful when teams need lower-level control. |
| [Web3Signer](https://docs.web3signer.consensys.io/) | Remote signer | Crypto | Isolates signing from the application or agent runtime. | Helpful for reducing direct signer exposure. |
| [viem](https://github.com/wevm/viem) | Client library | Crypto | Type-safe EVM interactions and transaction handling. | Common base layer under modern wallet stacks. |

## Safety and Guardrails

Safety and guardrail tools sit between agent reasoning and financial execution. This is where policy checks, spend limits, approval hygiene, and transaction risk controls live.

| Project | Primary role | Scope | What it enables | Why it matters |
| --- | --- | --- | --- | --- |
| [Safe Allowance Module](https://docs.safe.global/home/ai-agent-quickstarts/agent-with-spending-limit) | Spend controls | Crypto | Caps what an agent can spend over time. | One of the clearest practical spend-limit patterns. |
| [Open Policy Agent](https://github.com/open-policy-agent/OPA) | Policy engine | General | Policy-as-code for tools, destinations, assets, and quotas. | Good fit for a signing or execution gateway. |
| [Cedar](https://github.com/cedar-policy) | Policy engine | General | Fine-grained authorization rules for actions and actors. | Strong option for permission schemas around tools. |
| [OpenZeppelin Defender](https://docs.openzeppelin.com/defender/module/transaction-proposals) | Approvals workflow | Crypto | Transaction proposals, reviews, approvals, and relayers. | Useful when human approval must sit above execution. |
| [Blockaid](https://www.blockaid.io/blog/privy-integrates-blockaid-to-bring-transaction-security-into-global-wallets) | Transaction scanning | Crypto | Pre-sign risk analysis and validation. | Represents the wallet-firewall category well. |
| [Revoke.cash](https://revoke.cash/) | Approval hygiene | Crypto | Detects and removes risky token approvals. | Approval abuse is a major finance-agent risk surface. |
| [Approval Exploit List](https://github.com/RevokeCash/approval-exploit-list) | Exploit dataset | Crypto | Catalog of approval-abuse incidents. | Good source material for eval scenarios and education. |
| [Wallet Guard](https://github.com/wallet-guard/wallet-guard-extension) | Wallet firewall UX | Crypto | Transaction warnings and phishing protection. | Useful open-source reference for transaction safety UX. |
| [ScamSniffer Scam Database](https://github.com/scamsniffer/scam-database) | Threat intel | Crypto | Lists of malicious domains and addresses. | Supports deny-lists and screening pipelines. |
| [Ethereum Transactions Firewall](https://github.com/web3-pi/ethereum-transaction-firewall) | Gateway firewall | Crypto | Accepts or rejects transactions before RPC submission. | Illustrates the gateway model for policy enforcement. |

## Simulation and Validation

Simulation and validation tools help verify what a transaction or action will actually do before it is signed or sent.

| Project | Primary role | Scope | What it enables | Why it matters |
| --- | --- | --- | --- | --- |
| [Tenderly Simulation](https://docs.tenderly.co/simulations/quickstart) | Transaction simulation | Crypto | Dry-runs transactions against current chain state. | Core simulate-before-sign primitive. |
| [Tenderly Transaction Preview](https://docs.tenderly.co/simulations/transaction-preview) | Preview layer | Crypto | User-facing previews of expected transaction outcome. | Strong wallet-safety pattern for agent-generated actions. |
| [Tenderly Rabby Preview Example](https://github.com/Tenderly/tenderly-rabby-transaction-preview) | Integration example | Crypto | Example wallet integration for transaction preview. | Useful end-to-end implementation reference. |
| [Blocknative Transaction Preview](https://www.blocknative.com/blog/ethereum-transaction-preview-api) | Preview layer | Crypto | Alternative preview infrastructure. | Helpful for comparing provider approaches. |
| [Hardhat](https://hardhat.org/) | Local simulation | Crypto | Local and forked EVM testing environments. | Essential for deterministic action testing. |
| [Foundry](https://getfoundry.sh/forge/tests/fork-testing/) | Fork testing | Crypto | Fast fork-mode protocol and transaction testing. | Excellent fit for agent action harnesses. |
| [Ledger ERC-7730 Registry](https://github.com/LedgerHQ/clear-signing-erc7730-registry) | Clear-signing registry | Crypto | Metadata for readable transaction display. | Supports safer review before signing. |
| [Ledger ERC-7730 Analyzer](https://github.com/LedgerHQ/erc7730-analyzer) | Descriptor analysis | Crypto | Checks clear-signing descriptors for issues. | Treats metadata itself as part of the attack surface. |

## Security Testing and Evals

Security testing and eval tools are used to probe failure modes, red-team agent behavior, and turn finance-specific risks into repeatable test cases.

| Project | Primary role | Scope | What it enables | Why it matters |
| --- | --- | --- | --- | --- |
| [AgentShield](https://github.com/affaan-m/agentshield) | Agent scanner | General | Scans agent configs, tools, and MCP surfaces. | High-signal for finance-agent tool exposure review. |
| [garak](https://github.com/NVIDIA/garak) | LLM vuln scanner | General | Broad probing for model and prompt failures. | Useful baseline scanner in any eval stack. |
| [PyRIT](https://github.com/Azure/PyRIT) | Red-team framework | General | Automated and human-guided AI red teaming. | Good harness for finance-specific attack cases. |
| [Promptfoo](https://github.com/promptfoo/promptfoo) | Eval harness | General | CI-friendly evals and adversarial tests. | Practical choice for regression suites around tool use. |
| [OpenAI Evals](https://github.com/openai/evals) | Eval framework | General | Custom evaluation pipelines for model behavior. | Good substrate for domain benchmarks. |
| [PurpleLlama CyberSecEval](https://github.com/meta-llama/PurpleLlama) | Security benchmark | General | Benchmark suite for security behavior and vulnerabilities. | Useful seed material for finance-agent benchmarks. |
| [Damn Vulnerable DeFi](https://github.com/OpenZeppelin/damn-vulnerable-defi) | Scenario bank | Crypto | Public DeFi exploit scenarios and exercises. | Helpful source of wallet-drain and approval-abuse patterns. |

## Observability and Audit

Observability and audit tooling helps teams trace agent decisions, monitor financial side effects, and review what happened after execution.

| Project | Primary role | Scope | What it enables | Why it matters |
| --- | --- | --- | --- | --- |
| [OpenAI Agents SDK](https://github.com/openai/openai-agents-python) | Agent tracing | General | Traces, execution graphs, and structured agent flows. | Sets expectations for auditable agent execution. |
| [LangSmith](https://docs.langchain.com/langsmith/home) | Agent observability | General | Monitoring, tracing, and evaluation for production agents. | Common choice for multi-step tool pipelines. |
| [Phoenix](https://github.com/Arize-ai/phoenix) | Open-source observability | General | Open-source tracing, experiments, and evaluations. | Strong OSS choice for agent monitoring. |
| [OpenZeppelin Defender Monitor](https://docs.openzeppelin.com/defender/module/monitor) | Onchain monitoring | Crypto | Alerts and monitoring for smart-contract activity. | Important for automated systems that control funds. |
| [Blockscout](https://github.com/blockscout/blockscout) | Explorer / audit data | Crypto | Explorer and API layer for transaction inspection. | Makes auditability and post-trade review easier. |
| [Helius](https://github.com/helius-labs/helius-sdk) | Solana data layer | Crypto | Solana RPC, webhooks, and enriched chain data. | Useful for observability in Solana-heavy stacks. |

## Standards and Protocols

Standards and protocols define the shared interfaces behind finance agents, from tool calling and identifiers to signing and intent execution.

| Standard / project | Area | Scope | What it standardizes or enables | Why it matters |
| --- | --- | --- | --- | --- |
| [Model Context Protocol](https://github.com/modelcontextprotocol/modelcontextprotocol) | Tool interface | General | Common protocol for exposing tools and data to agents. | Increasingly the default way to package finance actions. |
| [CAIPs](https://github.com/chainagnostic/caips) | Identifiers | Crypto | Chain, account, and asset identifiers across ecosystems. | Helps normalize multi-chain agent systems. |
| [EIP-712](https://eips.ethereum.org/EIPS/eip-712) | Signing | Crypto | Typed structured signing. | Improves clarity and policy boundaries at signing time. |
| [ERC-4337](https://eips.ethereum.org/EIPS/eip-4337) | Account abstraction | Crypto | Smart-account execution via user operations. | Enables better permission models than raw EOAs. |
| [ERC-7683](https://eips.ethereum.org/EIPS/eip-7683) | Intents | Crypto | Cross-chain intents and solver-based execution. | Important for chain-abstracted agent execution. |
| [Open Intents Framework](https://github.com/openintentsframework) | Intents infra | Crypto | Tooling and infra for solver-based intent execution. | Bridges intent expression to actual execution. |
| [CoW Protocol](https://docs.cow.fi/cow-protocol/concepts/introduction/intents) | Intent trading | Crypto | Trade intents executed by solvers. | Concrete real-world intent execution model. |
| [ERC-7730](https://eips.ethereum.org/EIPS/eip-7730) | Clear signing | Crypto | Metadata format for readable transaction display. | Central to what-you-see-is-what-you-sign safety. |
| [ERC-8001](https://eips.ethereum.org/EIPS/eip-8001) | Agent coordination | Crypto | Agent coordination and attestation concepts. | Relevant when multiple actors or agents coordinate finance actions. |
| [x402](https://github.com/coinbase/x402) | Payments | Crypto / fintech | HTTP-native payment flows for machine-to-machine commerce. | Important for agent monetization and payments. |

## Frameworks and Integration Layers

Frameworks and integration layers are not finance-specific on their own, but they are often the glue used to orchestrate finance-agent workflows.

| Project | Primary role | Scope | What it enables | Why it matters |
| --- | --- | --- | --- | --- |
| [LangGraph](https://github.com/langchain-ai/langgraph) | Orchestration | General | Stateful agents with checkpoints and human review. | Useful for approval-heavy finance workflows. |
| [AutoGen](https://github.com/microsoft/autogen) | Multi-agent framework | General | Cooperative agent workflows and task decomposition. | Useful when different agents handle research, policy, and execution. |
| [Semantic Kernel](https://github.com/microsoft/semantic-kernel) | Agent SDK | General | Enterprise-friendly orchestration across tools and models. | Relevant for regulated or internal finance systems. |
| [CrewAI](https://github.com/crewAIInc/crewAI) | Multi-agent framework | General | Lightweight Python agent coordination. | Include for completeness, though not finance-specific. |
| [LlamaIndex](https://github.com/run-llama/llama_index) | Data / RAG | General | Retrieval and knowledge workflows for agent systems. | Useful when finance agents need research context plus tools. |
| [ElizaOS](https://github.com/elizaOS/eliza) | Agent runtime | General / crypto-adjacent | Extensible runtime with plugin ecosystem. | Common in crypto agent ecosystems. |
| [Composio](https://github.com/ComposioHQ/composio) | Tool router | General | Tool routing and connection management. | Relevant when finance actions are one tool family among many. |

## Adjacent Infrastructure

Adjacent infrastructure includes the data, indexing, routing, and protocol SDK layers that many finance agents depend on behind the scenes.

| Project | Primary role | Scope | What it provides | Why it matters |
| --- | --- | --- | --- | --- |
| [The Graph](https://github.com/graphprotocol/contracts) | Indexing | Crypto | Structured blockchain data access via subgraphs. | Agents need reliable historical and structured data. |
| [Graph Node](https://github.com/graphprotocol/graph-node) | Indexing runtime | Crypto | Core runtime for custom subgraph indexing. | Useful for self-hosted data pipelines. |
| [Subsquid](https://github.com/subsquid-labs) | Indexing / datasets | Crypto | Data extraction and dataset tooling. | Helpful for analytics, monitoring, and training signals. |
| [Jupiter Swap API](https://github.com/jup-ag/jupiter-swap-api-client) | Protocol SDK | Crypto | Solana swap integration primitives. | Common base under agent wrappers and MCP servers. |
| [Uniswap SDK](https://github.com/Uniswap/sdks) | Protocol SDK | Crypto | EVM swap primitives and pool logic. | Useful for custom execution tooling. |
| [1inch SDK](https://github.com/1inch/1inch-sdk-go) | Aggregation SDK | Crypto | Routing and intent-swap infrastructure. | Practical for route building and execution logic. |
| [LI.FI SDK](https://github.com/lifinance/sdk) | Bridge / swap SDK | Crypto | Cross-chain swaps and bridging. | Common routing layer for multi-chain agents. |
| [Awesome ERC-4337](https://github.com/4337Mafia/awesome-account-abstraction) | Upstream curation | Crypto | Curated AA ecosystem resources. | Good upstream list to track instead of duplicating everything. |

## Design Patterns

- Simulate before signing. A finance agent should preview or fork-test a transaction before it reaches a signer.
- Put policy between reasoning and signing. LLM output should not directly control a hot signer.
- Prefer smart accounts over raw EOAs when possible. Session keys, allowlists, quotas, and approval workflows matter.
- Treat approvals as a first-class risk surface. Allowance abuse is one of the easiest ways to turn a capable agent into a dangerous one.
- Trace both the agent decision and the financial side effect. Tool-call logs without transaction context are incomplete, and onchain logs without agent traces are hard to audit.
- Build evals around finance-specific failures. Prompt injection is generic; wallet drain, approval abuse, route tampering, and malicious tool responses are the domain-specific cases.

## Contributing

Pull requests are welcome for new entries, removals, and stale-link fixes.

Please keep additions aligned with the curation bar:

- The project should materially help with financial actions, wallet control, transaction safety, simulation, monitoring, or finance-specific evaluation.
- Prefer official docs, official SDKs, or widely used open-source projects over thin wrappers and abandoned experiments.
- Keep descriptions short and factual.
- Avoid marketing copy, duplicate entries, and generic agent tooling that has no finance-specific relevance.
