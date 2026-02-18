# Contributing to Brand Consistency AI Skill

Thanks for your interest in contributing! This project is actively maintained and PRs are welcome.

## What We're Looking For

### High-value contributions
- **Platform specs**: New or updated dimensions for emerging platforms (Threads, Bluesky, Pinterest, etc.)
- **Brand config examples**: Real-world examples from public brands (using only publicly available brand information)
- **Tone-of-voice templates**: Copy templates for additional deliverable types (press releases, product descriptions, etc.)
- **Script improvements**: Bug fixes, new `--check` modes for `validate_brand.py`, better error messages
- **Industry-specific guidance**: Adapted references for specific sectors (SaaS, fashion, healthcare, NGO…)

### Ideas (discuss first via Issues)
- Web UI for brand config generation
- Integration with Figma Tokens / Style Dictionary / Theo
- GitHub Action for automated brand compliance checks on PRs
- Support for additional AI providers beyond Claude

## How to Contribute

1. **Fork** this repository
2. **Create a branch**: `git checkout -b feature/your-feature-name`
3. **Make your changes** — keep PRs focused and small
4. **Test scripts** if you've changed Python files: `python3 scripts/validate_brand.py --help`
5. **Open a Pull Request** with a clear description of what you changed and why

## Style Guidelines

### Markdown files
- Use present tense ("Add support for…" not "Added support for…")
- Keep tables aligned (they're used a lot in this project)
- Test any new copy templates by actually running them through Claude

### Python scripts
- Follow the existing code style (no external dependencies unless unavoidable)
- Add usage examples in the docstring
- Keep CLI flags consistent with existing scripts (`--config`, `--output`, `--format`)

### Brand config examples
- Only use brands with publicly available brand guidelines
- Include a source URL in the PR description
- Don't include anything proprietary or copyrighted

## Reporting Issues

Found a bug or missing spec? [Open an issue](../../issues/new) with:
- What you expected
- What actually happened
- The brand config or command you used (anonymize sensitive brand data)

## Code of Conduct

Be kind and constructive. This is a small project — we keep things simple and welcoming.
