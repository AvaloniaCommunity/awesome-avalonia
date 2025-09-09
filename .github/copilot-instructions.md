# Awesome Avalonia

**ALWAYS reference these instructions first and fallback to search or bash commands only when you encounter unexpected information that does not match the info here.**

Awesome Avalonia is a curated list repository that catalogs Avalonia UI libraries, tools, tutorials, and resources. This is a documentation repository, NOT a buildable/runnable codebase.

## Working Effectively

### Repository Structure
- **Main content**: README.md - The curated list of Avalonia resources organized by categories
- **Contribution guidelines**: CONTRIBUTING.md - Format and submission requirements
- **CI/CD**: `.github/workflows/link-check.yml` - Automated weekly link validation
- **Git configuration**: `.gitignore` and `.gitattributes` for repository management

### Bootstrap and Validation Setup
- **Download link checker**: `curl -L https://github.com/becheran/mlc/releases/latest/download/mlc-x86_64-linux -o /tmp/mlc && chmod +x /tmp/mlc`
- **Verify installation**: `/tmp/mlc --version`

### Link Validation Commands
- **Check all links (FULL VALIDATION)**: `/tmp/mlc README.md` -- takes 20-60 minutes for 298+ links. NEVER CANCEL. Set timeout to 90+ minutes.
- **Check specific file**: `/tmp/mlc [filename.md]`
- **Check offline only (local links)**: `/tmp/mlc --offline README.md` -- takes under 1 minute
- **Check with throttling (recommended)**: `/tmp/mlc --throttle 1000 README.md` -- reduces server load, takes 30-90 minutes. NEVER CANCEL.
- **Check and ignore specific links**: `/tmp/mlc --ignore-links "https://broken-link.com" README.md`

### Contribution Workflow  
- **Read contribution guidelines**: Always review CONTRIBUTING.md before making changes
- **Format requirements**: Use exact format: `[Lib Name](link) - Description.`
- **Keep descriptions short and simple**: Concise, informative descriptions only
- **Maintain alphabetical sorting**: Entries should be sorted within their categories
- **Validate ALL links**: Run full link validation before submitting changes

## Validation
- **ALWAYS validate links** after making ANY changes to README.md: `/tmp/mlc README.md`
- **TIMING CRITICAL**: Full link validation takes 20-60 minutes with 298+ links. NEVER CANCEL. Set timeout to 90+ minutes minimum.
- **Use throttling for server-friendly validation**: `/tmp/mlc --throttle 1000 README.md`
- **Test locally first**: Use `/tmp/mlc --offline README.md` to check formatting and local links
- **Handle network failures**: Some links may temporarily fail due to network issues or rate limiting. Re-run validation if needed.
- **Manual verification**: Manually visit newly added links to ensure they work and point to the correct resource
- **SCENARIO VALIDATION**: After adding new entries, manually verify:
  1. Link opens correctly in browser
  2. Link points to the intended Avalonia-related resource
  3. Description accurately represents the linked resource
  4. Entry follows the exact format: `[Name](URL) - Description.`
  5. Entry is placed in the correct category and maintains alphabetical order
- **Common link issues to watch for**:
  - Redirects that change domain (may be flagged as warnings)
  - Rate limiting from GitHub or other sites during bulk validation
  - Temporary server outages causing false negatives
  - Links that require specific user agents or headers

## Common Tasks

### Adding New Library/Resource
1. **Research**: Verify the resource is Avalonia-related and actively maintained
2. **Quality check**: Ensure the project has reasonable documentation and appears stable
3. **Uniqueness**: Verify it's not already listed or a duplicate
4. **Format**: Use exact format: `[Library Name](https://github.com/user/repo) - Brief description of what it does.`
5. **Categorize**: Place in appropriate section (Libraries & Extensions, Samples, Tools, etc.)
6. **Sort**: Maintain alphabetical order within the category
7. **Validate**: Run `/tmp/mlc README.md` to check all links (20-60 minutes, NEVER CANCEL)

### Entry Acceptance Criteria
- **Avalonia-specific**: Must be specifically designed for or extensively use Avalonia UI
- **Active maintenance**: Recent commits or releases (within 1-2 years preferred)
- **Functional**: Working project with clear purpose and documentation
- **Open source preferred**: Commercial products accepted if clearly beneficial to community
- **Language**: Primarily English descriptions and documentation

### Fixing Broken Links  
1. **Identify broken links**: Check CI workflow output or run `/tmp/mlc README.md`
2. **Research replacement**: Find updated URL or remove if resource no longer exists
3. **Update entry**: Modify the link or remove the entire entry if obsolete
4. **Validate**: Run full link check to ensure fix worked

### Repository Structure Output
```
ls -la /home/runner/work/awesome-avalonia/awesome-avalonia
total 64
drwxr-xr-x 4 runner runner  4096 .
drwxr-xr-x 3 runner runner  4096 ..
drwxrwxr-x 7 runner runner  4096 .git
-rw-rw-r-- 1 runner runner   378 .gitattributes
drwxrwxr-x 3 runner runner  4096 .github
-rw-rw-r-- 1 runner runner   649 .gitignore
-rw-rw-r-- 1 runner runner   397 CONTRIBUTING.md
-rw-rw-r-- 1 runner runner 36760 README.md
```

### Key Categories in README.md
- **General**: Core Avalonia resources and templates
- **Samples and Projects**: Real-world applications built with Avalonia
- **Tutorials**: Learning resources and guides
- **Libraries & Extensions**: Reusable components and add-ons
- **Videos**: Educational video content
- **Articles**: Written guides and technical articles
- **Tooling**: Development tools and utilities
- **Community**: Discussion forums and support channels

## Critical Timing and Cancellation Warnings
- **NEVER CANCEL link validation commands** - Full validation takes 20-60 minutes for 298+ links
- **ALWAYS set timeouts to 90+ minutes** for full link checks
- **Use `--throttle 1000` flag** to be respectful to servers (increases time to 30-90 minutes)
- **Build concept does NOT apply** - This is a documentation repository with no build process
- **No code compilation** - Only markdown editing and link validation required
- **CI runs weekly** - Link checker workflow runs every Monday at 9 AM UTC

## Working with CI/CD
- **Workflow file**: `.github/workflows/link-check.yml`
- **Schedule**: Runs weekly on Mondays at 9 AM UTC
- **Manual trigger**: Can be triggered manually from GitHub Actions tab
- **Purpose**: Validates all links in the repository for broken/moved URLs
- **Tool used**: `becheran/mlc@v0.16.2` (markdown link checker)

## Quality Standards
- **Link quality**: All links must be functional and point to Avalonia-related content
- **Description quality**: Descriptions should be concise but informative
- **Categorization**: Resources must be placed in the most appropriate category
- **Maintenance**: Remove entries for abandoned or obsolete projects
- **Formatting consistency**: Strict adherence to the established format pattern

This repository serves the Avalonia community by maintaining a high-quality, well-organized collection of resources. Always prioritize link validity and accurate categorization.