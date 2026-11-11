# SurveysAI Qualitative Analysis

Lets Claude Code analyse interview and focus group transcripts with SurveysAI Qualitative Analysis: thematic analysis, rapid analysis or deductive coding with a codebook, followed by written reports. The plugin connects the hosted MCP server and adds the `analyze-interviews` skill, which agrees the brief with you, offers pseudonymisation, shows the price before any paid analysis and reads the reports.

**Sign-in.** OAuth: in Claude Code run `/mcp`, select the server and authenticate; your browser opens to sign in and approve access. No API key is needed.

**Data.** The skill asks before sending your content to the service. SurveysAI is operated by i-dotazník s.r.o.; privacy policy: https://www.surveysai.com/legal/privacy/. Not affiliated with Google, OpenAI or Anthropic.

Service: https://qualitative-analysis.surveysai.com/

Install from the SurveysAI marketplace:

```
/plugin marketplace add pacerny/surveysai-plugins
/plugin install surveysai-qualitative-analysis@surveysai
```

License: MIT (see the repository LICENSE).
