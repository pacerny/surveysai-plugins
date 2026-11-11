# SurveysAI for Google Forms

Lets Claude Code turn a plain-text survey draft into a real Google Form in your own Google account. The plugin connects the hosted SurveysAI MCP server and adds the `create-google-form` skill, which drafts the questions with you, validates them and creates the form only after you confirm the title and the list of questions.

**Sign-in.** OAuth: in Claude Code run `/mcp`, select the server and authenticate; your browser opens to sign in with Google and approve access. No API key is needed.

**Data.** The skill asks before sending your content to the service. SurveysAI is operated by i-dotazník s.r.o.; privacy policy: https://www.surveysai.com/legal/privacy/. Not affiliated with Google, OpenAI or Anthropic.

Service: https://for-google-forms.surveysai.com/

Install from the SurveysAI marketplace:

```
/plugin marketplace add pacerny/surveysai-plugins
/plugin install surveysai-google-forms@surveysai
```

License: MIT (see the repository LICENSE).
