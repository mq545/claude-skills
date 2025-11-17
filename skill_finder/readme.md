# Skill Finder

**Discover which skills you should create based on your actual Claude usage patterns.**

Skill Finder analyzes your conversation history to identify repeatable tasks that would benefit from being formalized into dedicated skills. Instead of guessing what skills might be useful, let your actual usage patterns guide you.

## What It Does

Skill Finder searches your conversations and identifies:
- Tasks you perform repeatedly (3+ times)
- Clear patterns in how you use Claude
- Opportunities to save time through automation
- Which skills would provide the most value

**It doesn't build skills** - it recommends which ones you should build based on what you actually do.

## Installation

### Option 1: Upload to Claude (Easiest)
1. Download this folder
2. Open Claude in your browser (claude.ai)
3. Navigate to the project where you want to use Skill Finder
4. Drag and drop the entire `skill-finder` folder into the chat
5. Claude will automatically detect and install the skill

### Option 2: Manual Installation
1. Clone this repository
2. Copy the `skill-finder` folder to your Claude skills directory
3. The skill will be available in that project

## How to Use

Once installed, simply ask Claude:
```
"What skills should I create based on my conversations?"
```

Or be more specific:
```
"Do I ask about code reviews enough that it should be a skill?"
"Analyze my last 3 months of conversations for patterns"
"Show me what I do repeatedly with Claude"
```

### Configuration Options

When Skill Finder starts, it will ask you:

1. **Scope**: How far back to analyze
   - Recent conversations
   - Last 3 months (recommended)
   - All time

2. **Topic filter**: What to focus on
   - Everything (recommended for first run)
   - Specific topics (code, data, writing, etc.)

3. **Minimum frequency**: How often a pattern should appear
   - 3+ times (default, recommended)
   - 5+ times (if you have lots of conversations)

## What You'll Get

Skill Finder produces a detailed report with:

### High Priority Recommendations
Patterns appearing frequently that would save significant time:
- **Pattern name** (e.g., "Production Code Reviews")
- **Frequency** (how often you do this)
- **Example conversations** (links to specific instances)
- **Why it should be a skill** (benefits and time savings)
- **Pattern details** (what's consistent across instances)

### Medium Priority Recommendations
Good candidates but lower frequency or impact

### Low Priority / Not Recommended
Patterns that appeared but don't meet skill-worthiness criteria

### Already Covered
Patterns already handled by existing skills (validates what's working)

## Example Output

See the `examples/` folder for sample reports showing what Skill Finder produces.

## Requirements

- **Minimum conversations**: 20+ for meaningful pattern detection (more is better)
- **Project access**: Only analyzes conversations in the current project
- **Conversation history**: Patterns must appear 3+ times to be recommended

## Privacy

Skill Finder:
- ✅ Only analyzes conversations in your current project
- ✅ Doesn't expose sensitive data in summaries
- ✅ Anonymizes examples when presenting patterns
- ✅ Respects conversation privacy settings
- ❌ Cannot access incognito conversations
- ❌ Cannot access conversations in other projects

## What Makes a Good Skill Recommendation?

Skill Finder recommends patterns that are:
- **Frequent**: Appears 3+ times
- **Repeatable**: Clear, consistent structure
- **Time-intensive**: Takes 5+ minutes per instance
- **Automatable**: Would benefit from standardization
- **Unique**: Not already covered by existing skills

It won't recommend:
- One-off requests
- Simple single-prompt tasks
- Highly variable requests with no clear pattern
- Things already handled by existing skills

## Next Steps After Getting Recommendations

1. **Review the high-priority patterns** - these offer the most value
2. **Click through example conversations** - understand what's common
3. **Pick one to build first** - start with highest frequency + impact
4. **Use Skill Builder** (companion skill) to generate the SKILL.md
5. **Test and refine** - iterate based on actual usage

## Companion Skill

**Skill Builder** (coming soon) - Takes a Skill Finder recommendation and generates a complete SKILL.md file for you.

**Workflow:**
1. Skill Finder identifies patterns → recommends skills
2. You pick one
3. Skill Builder creates the SKILL.md
4. You test and refine

## Examples

See real example outputs in the `examples/` folder:
- `full_analysis_report.md` - Complete analysis with multiple patterns
- `code_review_pattern.md` - Detailed breakdown of a specific pattern
- `focused_search_example.md` - Focused search for a specific topic

## Contributing

Found a bug or have a suggestion? Open an issue or submit a pull request!

## License

MIT License - Use freely, attribution appreciated

---

**Ready to discover your skill opportunities?** Install Skill Finder and ask: "What skills should I create?"