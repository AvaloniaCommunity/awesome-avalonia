# Awesome Avalonia Curation Repository

Awesome Avalonia is a curated list of Avalonia UI libraries, tools, samples, and resources maintained in a single README.md file. This is a documentation-only repository with no build processes or code compilation.

Always reference these instructions first and fallback to search or bash commands only when you encounter unexpected information that does not match the info here.

## Working Effectively

### Repository Structure
- `README.md` - The main awesome list containing all Avalonia resources organized by categories
- `CONTRIBUTING.md` - Guidelines for contributors submitting new entries
- `.github/workflows/link-check.yml` - Weekly automated link validation
- `.gitignore` and `.gitattributes` - Standard Git configuration files

### Essential Commands
- Install the markdown link checker: `cargo install mlc`
- Check all links: `/home/runner/.cargo/bin/mlc . --throttle 100` 
- Check specific file: `/home/runner/.cargo/bin/mlc README.md --throttle 100`
- View link checker help: `/home/runner/.cargo/bin/mlc --help`

### Link Validation - NEVER CANCEL
- **CRITICAL**: Link checking takes 22-25 seconds. NEVER CANCEL. Set timeout to 60+ minutes.
- The tool checks 299+ links across the repository
- Expect 40-50 broken links due to site changes, redirects, or temporary outages
- Exit code 1 is NORMAL when broken links are found - this is not a failure
- Use `--throttle 100` to avoid being rate-limited by external sites
- Both commands (`mlc .` and `mlc README.md`) produce identical results since only README.md contains links

### Timing Expectations
- **Link checking**: 22-25 seconds for full repository check. NEVER CANCEL.
- **Manual validation**: 2-3 minutes to verify new entries follow format guidelines
- **Content editing**: Immediate - no build or compilation steps required

## Validation

### Pre-commit Validation Steps
ALWAYS run these commands before committing changes:
1. `cd /home/runner/work/awesome-avalonia/awesome-avalonia`
2. `/home/runner/.cargo/bin/mlc README.md --throttle 100` (22-25 seconds - NEVER CANCEL)
3. Manually verify any new entries follow the format: `- [Name](link) - Description.` (note period)
4. Check that entries are properly categorized and alphabetically sorted within sections
5. Verify descriptions are concise (under 100 characters) and end with a period

### Manual Content Validation
When adding or editing entries:
- Verify links are accessible and lead to the correct resource
- Ensure descriptions are concise and accurate (under 100 characters)
- Check that the resource is actually related to Avalonia UI
- Confirm entries follow the established format exactly
- Validate entries are placed in the correct category section

### GitHub Actions Workflow
- The `.github/workflows/link-check.yml` runs weekly on Mondays at 9 AM UTC
- Uses `becheran/mlc@v0.16.2` to check all markdown links
- Can be triggered manually via GitHub UI using workflow_dispatch
- Failures are expected due to external site changes - review and update as needed

## Common Tasks

### Adding a New Entry
1. Identify the correct category section in README.md
2. Use the exact format: `- [Name](link) - Description.` (note the period at the end)
3. Insert alphabetically within the category
4. Validate the link works and description is accurate (under 100 characters)
5. Run link checker: `/home/runner/.cargo/bin/mlc README.md --throttle 100` (22-25 seconds)
6. Ensure description follows CONTRIBUTING.md guidelines: short, simple, and descriptive

### Fixing Broken Links
1. Run full link check: `/home/runner/.cargo/bin/mlc . --throttle 100` (22-25 seconds - NEVER CANCEL)
2. Review the "broken links" list in the output (expect 40-50 broken links normally)
3. Research each broken link to find:
   - Updated URL if the resource moved
   - Alternative resource if the original is permanently gone
   - Remove entry if resource is no longer relevant
4. Update README.md with corrections
5. Re-run link checker to verify fixes: `/home/runner/.cargo/bin/mlc README.md --throttle 100`

### Updating Categories
1. Edit README.md table of contents if adding new sections
2. Ensure internal anchor links match section headers exactly (case-sensitive)
3. Verify all TOC links work: `/home/runner/.cargo/bin/mlc README.md --throttle 100` (22-25 seconds)
4. Follow the existing hierarchy: major sections, subsections, and sub-subsections

## Repository Reference

### Exact Entry Format Examples
**Correct format:**
```
- [Avalonia](https://github.com/AvaloniaUI/Avalonia) - Avalonia source code.
- [AvaloniaVS](https://github.com/AvaloniaUI/AvaloniaVS) - Visual Studio Extension for Avalonia.
```

**Common mistakes to avoid:**
- Missing period at end: `- [Name](link) - Description`
- Wrong bullet format: `* [Name](link) - Description.`
- Missing space after bullet: `-[Name](link) - Description.`
- Inconsistent capitalization in descriptions

### Current Structure Output
```
ls -la /home/runner/work/awesome-avalonia/awesome-avalonia
total 68
drwxr-xr-x 4 runner docker  4096 Sep  9 15:07 .
drwxr-xr-x 3 runner docker  4096 Sep  9 15:06 ..
drwxr-xr-x 7 runner docker  4096 Sep  9 15:07 .git
-rw-r--r-- 1 runner docker   378 Sep  9 15:07 .gitattributes
drwxr-xr-x 3 runner docker  4096 Sep  9 15:07 .github
-rw-r--r-- 1 runner docker   649 Sep  9 15:07 .gitignore
-rw-r--r-- 1 runner docker   397 Sep  9 15:07 CONTRIBUTING.md
-rw-r--r-- 1 runner docker 36899 Sep  9 15:07 README.md
```

### Current Link Statistics
- **Total links**: 299
- **Working links**: ~246 (82%)
- **Warnings**: ~9 (redirects)
- **Broken links**: ~44 (15%)
- **Check frequency**: Weekly via GitHub Actions

### Key Categories in README.md
- General
- Samples and Projects (Audio, Communication, Documents, Gaming, Graphics, Productivity, Software Development)
- Tutorials
- Libraries & Extensions (Generic, Localization, Themes, MVVM, Charts, Controls, Games, Web)
- Videos
- Articles
- Community
- Tooling

## Important Notes

- **NO BUILD PROCESS**: This repository has no compilation, testing, or build steps
- **NO DEPENDENCIES**: No package.json, requirements.txt, or similar dependency files
- **CONTENT FOCUS**: Primary work involves curating and organizing Avalonia-related resources
- **LINK MAINTENANCE**: Regular validation and updating of external links is the main maintenance task
- **COLLABORATIVE**: Follow CONTRIBUTING.md guidelines when adding community suggestions

## Troubleshooting

### Link Checker Issues
- If mlc is not installed: `cargo install mlc`
- If Rust/Cargo is not available: Install Rust toolchain first
- If links fail due to rate limiting: Increase `--throttle` value (e.g., `--throttle 200`)
- If checker hangs: Wait at least 60 seconds before considering alternatives

### Content Issues
- Verify entry format matches existing entries exactly
- Check that links use HTTPS when available
- Ensure descriptions end with a period
- Confirm alphabetical ordering within categories
- Validate that new categories have corresponding TOC entries