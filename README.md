# SurveysAI plugins for Claude Code and Codex

Remote MCP servers and skills for SurveysAI products:

| Plugin | What it does | Sign-in |
|---|---|---|
| `surveysai-google-forms` | Creates Google Forms in your own Google account from a plain-text survey | OAuth (browser sign-in on first use) |
| `surveysai-transkripce` | Transcribes Czech audio and video | API key from your Transkripce profile → `TRANSKRIPCE_API_KEY` |
| `surveysai-open-end` | Codes open-ended survey responses into a category hierarchy | API key from your Open-End profile → `OPEN_END_API_KEY` |
| `surveysai-qualitative-analysis` | Analyses interview and focus group transcripts | API key from your Account page → `QUALITATIVE_ANALYSIS_API_KEY` |

The skills ask before sending survey drafts or responses to a service, leave
uploading recordings to you, and show the price before any paid action
(transcription, analysis). SurveysAI is operated by i-dotazník s.r.o. and is
not affiliated with Google, OpenAI or Anthropic.

## Claude Code

```
/plugin marketplace add pacerny/surveysai-plugins
/plugin install surveysai-google-forms@surveysai
```

Set the API key environment variables before starting `claude` for the
plugins that need them. Skills are available as `/surveysai-google-forms:create-google-form`,
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
bearer_token_env_var = "OPEN_END_API_KEY"

[mcp_servers.surveysai-qualitative-analysis]
url = "https://qualitative-analysis.surveysai.com/mcp"
bearer_token_env_var = "QUALITATIVE_ANALYSIS_API_KEY"
```

The skills in `plugins/*/skills/` can be copied to `~/.agents/skills/`.

## Other clients

The Google Forms, Transkripce and Open-End servers are listed in the official MCP Registry:
- https://registry.modelcontextprotocol.io/v0/servers?search=com.surveysai/for-google-forms
- https://registry.modelcontextprotocol.io/v0/servers?search=com.surveysai/transkripce
- https://registry.modelcontextprotocol.io/v0/servers?search=com.surveysai/open-end
More: https://www.surveysai.com/for-ai-agents/

## Privacy and security

- Privacy: https://www.surveysai.com/legal/privacy/ (Google Forms, Open-End,
  Qualitative Analysis),
  https://transkripce.i-dotaznik.cz/napoveda/privacy/ (Transkripce).
- API keys belong in environment variables, never in files of this repository.
- Security issues: see [SECURITY.md](SECURITY.md).
