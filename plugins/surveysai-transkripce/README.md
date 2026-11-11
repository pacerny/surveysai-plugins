# Transkripce

Lets Claude Code work with Transkripce, a service for transcribing Czech audio and video recordings. The plugin connects the hosted Transkripce MCP server and adds the `transcribe-audio` skill, which shows the price before any paid transcription, leaves uploading recordings to you in the web app and reads the finished transcripts.

**Sign-in.** API key: create one in your Transkripce profile and export it as `TRANSKRIPCE_API_KEY` before starting Claude Code.

**Data.** The skill never uploads recordings; you upload them in the web app and decide what is sent. Transkripce is operated by i-dotazník s.r.o.; privacy policy: https://transkripce.i-dotaznik.cz/napoveda/privacy/. Not affiliated with Google, OpenAI or Anthropic.

Service: https://transkripce.i-dotaznik.cz/

Install from the SurveysAI marketplace:

```
/plugin marketplace add pacerny/surveysai-plugins
/plugin install surveysai-transkripce@surveysai
```

License: MIT (see the repository LICENSE).
