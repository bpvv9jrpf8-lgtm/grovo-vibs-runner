# Grovo Vibs Runner

Public GitHub Actions runner for Grovo Vibs.

Production architecture:

1. Generate one complete song/video/package once from the private source repository.
2. Save the publish-ready files as an immutable Actions artifact.
3. Publish to YouTube in a separate publish-only workflow.
4. If publishing fails, retry only the publish workflow so OpenAI, ElevenLabs, stock-video work, and rendering are not regenerated.
