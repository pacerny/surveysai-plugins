# Open-End Response Analyser

Lets Claude Code code open-ended survey responses with Open-End Response Analyser: an AI code frame with up to three levels, categorisation of every answer, and the results. The plugin connects the hosted Open-End MCP server and adds the `analyze-open-ended-responses` skill, which asks before sending responses and shows the price in credits before any paid analysis.

**Sign-in.** OAuth: in Claude Code run `/mcp`, select the server and authenticate; your browser opens to sign in to Open-End and approve access. No API key is needed.

**Data.** The skill asks before sending your content to the service. SurveysAI is operated by i-dotazník s.r.o.; privacy policy: https://www.surveysai.com/legal/privacy/. Not affiliated with Google, OpenAI or Anthropic.

Service: https://open-end.surveysai.com/

Install from the SurveysAI marketplace:

```
/plugin marketplace add pacerny/surveysai-plugins
/plugin install surveysai-open-end@surveysai
```

License: MIT (see the repository LICENSE).
