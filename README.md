# SurveysAI plugins for Claude Code and Codex

Remote MCP servers and skills for SurveysAI products:

| Plugin | What it does | Sign-in |
|---|---|---|
| `surveysai-google-forms` | Creates Google Forms in your own Google account from a plain-text survey | OAuth (browser sign-in via `/mcp`) |
| `surveysai-transkripce` | Transcribes Czech audio and video | API key from your Transkripce profile → `TRANSKRIPCE_API_KEY` |
| `surveysai-open-end` | Codes open-ended survey responses into a category hierarchy | OAuth (browser sign-in via `/mcp`) |
| `surveysai-qualitative-analysis` | Analyses interview and focus group transcripts | OAuth (browser sign-in via `/mcp`) |

The skills ask before sending survey drafts or responses to a service, leave
uploading recordings to you, and show the price before any paid action
(transcription, analysis). SurveysAI is operated by i-dotazník s.r.o. and is
not affiliated with Google, OpenAI or Anthropic.

## Claude Code

```
/plugin marketplace add pacerny/surveysai-plugins
/plugin install surveysai-google-forms@surveysai
```

Set `TRANSKRIPCE_API_KEY` before starting `claude` if you use the Transkripce
plugin; for the other plugins open `/mcp` in Claude Code, select the server
and authenticate (browser sign-in). Skills are available as `/surveysai-google-forms:create-google-form`,
`/surveysai-transkripce:transcribe-audio`,
`/surveysai-open-end:analyze-open-ended-responses` and
`/surveysai-qualitative-analysis:analyze-interviews`.

## Codex CLI

Add the servers to `~/.codex/config.toml`:

```toml
[mcp_servers.surveysai-google-forms]
url = "https://mcp.for-google-forms.surveysai.com/mcp"
# then: codex mcp login surveysai-google-forms

[mcp_servers.surveysai-transkripce]
url = "https://transkripce.i-dotaznik.cz/api/v1/transcription/mcp/"
bearer_token_env_var = "TRANSKRIPCE_API_KEY"

[mcp_servers.surveysai-open-end]
url = "https://mcp.open-end.surveysai.com/mcp"
# then: codex mcp login surveysai-open-end

[mcp_servers.surveysai-qualitative-analysis]
url = "https://qualitative-analysis.surveysai.com/mcp"
# then: codex mcp login surveysai-qualitative-analysis
```

Open-End and Qualitative Analysis also accept an API key instead of OAuth:
`bearer_token_env_var = "OPEN_END_API_KEY"` or `"QUALITATIVE_ANALYSIS_API_KEY"`.

The skills in `plugins/*/skills/` can be copied to `~/.agents/skills/`.

## Other clients

All four servers are listed in the official MCP Registry:
- https://registry.modelcontextprotocol.io/v0/servers?search=com.surveysai/for-google-forms
- https://registry.modelcontextprotocol.io/v0/servers?search=com.surveysai/transkripce
- https://registry.modelcontextprotocol.io/v0/servers?search=com.surveysai/open-end
- https://registry.modelcontextprotocol.io/v0/servers?search=com.surveysai/qualitative-analysis-workflow
More: https://www.surveysai.com/for-ai-agents/

## Privacy and security

- Privacy: https://www.surveysai.com/legal/privacy/ (Google Forms, Open-End,
  Qualitative Analysis),
  https://transkripce.i-dotaznik.cz/napoveda/privacy/ (Transkripce).
- API keys belong in environment variables, never in files of this repository.
- Security issues: see [SECURITY.md](SECURITY.md).

## License

MIT, see [LICENSE](LICENSE). It covers all content of this repository
(manifests, skill instructions, documentation and icons), not the services
the plugins connect to.
