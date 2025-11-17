---
name: skill-finder
description: Discovers which skills you should create by analyzing your conversation history for repeatable patterns. Identifies the tasks you ask Claude to do repeatedly and recommends which ones would benefit from being formalized into dedicated skills.
---

# Skill Finder

## Description
Discovers which skills you should create by analyzing your conversation history for repeatable patterns. Identifies the tasks you ask Claude to do repeatedly and recommends which ones would benefit from being formalized into dedicated skills.

Think of it as your personal skill opportunity detector - it watches what you do and says "you should make a skill for that."

## When to Use This Skill
Use Skill Finder when you want to:
- Discover what custom skills would be most valuable for your workflow
- Understand which tasks you perform repeatedly with Claude
- Identify opportunities to formalize frequent requests into reusable skills
- Prioritize which skills to build first based on your actual usage patterns
- Audit your Claude usage for optimization opportunities

## How It Works

### 1. Search Your Conversations
Skill Finder uses the `conversation_search` tool to scan your conversation history looking for patterns.

**Configuration options:**
- **Scope**: Recent conversations, specific date range, or all history
- **Topics**: Focus on specific domains or search everything
- **Minimum frequency**: How many times should a pattern appear to be worth a skill (default: 3+)

### 2. Identify Repeatable Patterns
For each conversation, it identifies:
- What you were asking Claude to do
- The structure of your request
- Whether this is a one-off or repeatable pattern
- The category/domain (code review, data analysis, writing, etc.)

### 3. Present Recommendations
Shows you prioritized recommendations with:

**For each pattern:**
- **Name**: What you're doing repeatedly
- **Frequency**: How often this appears
- **Examples**: Links to 2-3 conversations where you did this
- **Why it should be a skill**: What you'd gain from formalizing it
- **Priority**: High/Medium/Low based on frequency and complexity

### 4. Help You Decide
For each recommendation, you can:
- See the specific conversations where you did this
- Understand what's common across them
- Decide if it's worth making a skill
- Get a sense of time savings potential

**Note:** Skill Finder ONLY recommends. It doesn't build skills for you - that's what Skill Builder does.

## Output Format
```
# Skill Recommendations Based on Your Conversations

**Analysis Period**: [Date range]
**Conversations Analyzed**: [N]
**Patterns Found**: [M]

## 🔥 High Priority (Do These First)

### 1. [Pattern Name] - Appears [X] times
**What you're doing**: [Brief description]
**Example conversations**:
- [Link to conversation 1] - [One-line summary]
- [Link to conversation 2] - [One-line summary]
- [Link to conversation 3] - [One-line summary]

**Why make this a skill**:
- You do this [X] times per [timeframe]
- Takes [Y] minutes each time
- Has clear repeatable structure
- Would benefit from standardization

**Potential time savings**: [Estimate]

---

### 2. [Next pattern...]

## 💡 Medium Priority (Good Candidates)

[Similar format, lower frequency or impact]

## 🤔 Maybe Later (Appeared but Low Priority)

[Patterns that appeared 1-2 times or are already handled well]

## ✅ Already Covered by Existing Skills

[Patterns you have existing skills for - shows what's working]

---

**Next Steps**:
1. Pick a high-priority pattern
2. Review those conversations to understand what's common
3. Use Skill Builder to create the skill (or build it manually)
4. Test and refine
```

## Quality Standards

### What Makes a Good Skill Recommendation

**Recommend when**:
- ✅ Appears 3+ times (configurable threshold)
- ✅ Has clear, repeatable structure
- ✅ Takes meaningful time (5+ minutes per instance)
- ✅ Would benefit from standardization
- ✅ Not already well-handled by existing skills

**Don't recommend when**:
- ❌ Appears only 1-2 times (not frequent enough)
- ❌ Highly variable structure (no clear pattern)
- ❌ Too simple (single prompt, no workflow)
- ❌ Already covered by existing skills
- ❌ Requires constant human judgment (can't be systematized)

### Presentation Quality

**For each recommendation, provide**:
- Clear pattern name (what user is doing)
- Accurate frequency count
- 2-3 representative example conversations (with links)
- Explanation of why it should be a skill
- Realistic time savings estimate
- Pattern details (what's consistent across instances)

**Don't**:
- Over-promise time savings
- Recommend patterns that aren't actually repeatable
- Expose sensitive information from conversations
- Suggest skills for things that are actually one-offs

## Search Strategy

### Initial Discovery Queries
Use broad searches to identify common domains:
- "code review"
- "debug", "error", "fix"
- "sql", "query", "database"
- "analyze", "data", "statistics"
- "write", "document", "draft"
- "explain", "understand"
- "optimize", "improve", "refactor"

### Pattern Clustering
After initial search:
1. Group conversations by topic/intent
2. Look for structural similarities
3. Count frequency of each pattern
4. Identify common elements across instances

### Frequency Thresholds
- **High Priority**: 8+ occurrences
- **Medium Priority**: 4-7 occurrences
- **Low Priority**: 3 occurrences
- **Below threshold**: 1-2 occurrences (mention but don't recommend)

## Example Interactions

### Example 1: Basic Discovery

**User**: "What skills should I create based on my conversations?"

**Skill Finder**: "I'll analyze your conversation history to find repeatable patterns that would make good skills.

**Quick questions first**:
- How far back should I look? (Recent, last 3 months, all time?)
- Should I focus on any specific topics, or search everything?
- Minimum frequency: How many times should something appear to recommend it? (I suggest 3+)

What are your preferences?"

**User**: "Last 3 months, everything, minimum 3 times"

**Skill Finder**: "Got it. Searching conversations from Aug 16 - Nov 16 for patterns appearing 3+ times...

[Uses conversation_search with various keywords]

Found 47 conversations. Analyzing for patterns...

# Skill Recommendations

**Analysis Period**: Aug 16 - Nov 16, 2025
**Conversations Analyzed**: 47
**Patterns Found**: 7

## 🔥 High Priority

### 1. Production Code Reviews - Appears 15 times

**What you're doing**: Reviewing code for security vulnerabilities, best practices, and performance issues. You have a consistent checklist approach across all reviews.

**Example conversations**:
- [Oct 15 conversation](https://claude.ai/chat/abc123) - Auth code security review
- [Oct 28 conversation](https://claude.ai/chat/def456) - API endpoint vulnerability check  
- [Nov 3 conversation](https://claude.ai/chat/ghi789) - SQL injection risk analysis

**Why make this a skill**:
- You do this ~15 times per month
- Each review follows similar structure (security → performance → style)
- Currently takes 15-20 minutes per review
- A skill could apply your checklist automatically

**Potential time savings**: 5+ hours/month if streamlined

**Pattern details**:
- 100% include security checks
- 87% include performance analysis
- 73% include refactoring suggestions
- You always explain the "why" behind issues

---

### 2. SQL Query Optimization - Appears 12 times

**What you're doing**: Analyzing slow queries, explaining what they do, and rewriting them for better performance.

**Example conversations**:
- [Sept 22](https://claude.ai/chat/jkl012) - Slow JOIN optimization
- [Oct 5](https://claude.ai/chat/mno345) - Subquery rewrite for large dataset
- [Oct 19](https://claude.ai/chat/pqr678) - Complex query explanation

**Why make this a skill**:
- You do this ~12 times per month
- Follows pattern: analyze → explain bottleneck → suggest indexes → rewrite
- A skill could standardize the analysis workflow

**Potential time savings**: 2-3 hours/month

---

### 3. Data Quality Checks - Appears 8 times

**What you're doing**: Loading datasets and running exploratory analysis - null checks, summary stats, outlier detection, data type validation.

**Example conversations**:
- [Sept 5](https://claude.ai/chat/stu901) - CSV quality check
- [Sept 18](https://claude.ai/chat/vwx234) - Summary statistics generation
- [Oct 8](https://claude.ai/chat/yza567) - Outlier detection

**Why make this a skill**:
- Highly repetitive workflow
- Same checks every time
- Currently manual process
- Perfect candidate for automation

**Potential time savings**: 1-2 hours/month

---

## 💡 Medium Priority

### 4. Meeting Note Summarization - Appears 5 times
**What you're doing**: Converting meeting transcripts into structured action items and decisions.
**Why make this a skill**: Consistent format needs, but lower frequency.

### 5. API Documentation Writing - Appears 4 times
**What you're doing**: Creating standard API endpoint documentation.
**Why make this a skill**: Clear template opportunity, moderate frequency.

---

## 🤔 Maybe Later

### Technical Blog Post Outlines - Appears 2 times
Not quite frequent enough yet, but watch this pattern as you blog more.

---

## ✅ Already Covered by Existing Skills

### Document Formatting - Appears 6 times
You're already using the `docx` skill for this effectively.

---

**My recommendation**: Start with Production Code Reviews - it's your most frequent pattern with highest time savings potential.

Want to see more details on any of these patterns?"

---

### Example 2: Focused Search

**User**: "Do I ask about Python debugging enough that it should be a skill?"

**Skill Finder**: "Let me search for Python debugging patterns...

[Uses conversation_search with: 'debug python', 'python error', 'python bug', 'traceback', 'python exception']

Found 11 conversations involving Python debugging. Let me analyze the pattern...

**Pattern: Python Debugging & Error Resolution**

**Frequency**: 11 times (last 3 months)
**Category**: High Priority

**What you're doing**:
1. Share error message/traceback
2. Ask for explanation of what's wrong
3. Get fix suggestions
4. Sometimes ask for prevention strategies

**Example conversations**:
- [Sept 12](https://claude.ai/chat/abc123) - AttributeError in pandas
- [Oct 3](https://claude.ai/chat/def456) - TypeError in function call
- [Oct 20](https://claude.ai/chat/ghi789) - Import error with packages

**Pattern consistency**:
- You always include the full traceback ✅
- You typically ask "why is this happening?" ✅
- You want both the fix AND the explanation ✅
- 70% of the time you ask how to prevent similar issues

**Should this be a skill? YES**

**Why**:
- High frequency (11 times in 3 months)
- Clear structure (error → explain → fix → prevent)
- Takes 5-10 minutes per debug session
- A skill could systematize the debugging approach

**Potential skill features**:
- Automatic traceback analysis
- Root cause explanation
- Fix suggestions with explanation
- Prevention strategies
- Similar error pattern detection

**Estimated time savings**: 1-1.5 hours/month

**Next step**: Use Skill Builder to create a 'Python Debugging Assistant' skill based on these patterns."

---

### Example 3: Understanding a Recommendation

**User**: "Tell me more about the SQL query optimization pattern"

**Skill Finder**: "Here's the detailed breakdown of your SQL optimization pattern:

**SQL Query Optimization Pattern**

**Frequency**: 12 conversations over 3 months
**Average time**: 12-15 minutes per conversation
**Total time spent**: ~2.5-3 hours

**Your typical workflow**:
1. **Share the slow query** (100% of cases)
2. **Explain current performance** (92% - "takes 45 seconds, should be faster")
3. **Ask what's wrong** (100%)
4. **Get optimization suggestions** (100%)
5. **Ask about indexes** (75% of cases)
6. **Request rewritten query** (83% of cases)

**Common themes across your queries**:
- JOIN optimization (67% of cases)
- Subquery → CTE refactoring (42%)
- Index recommendations (75%)
- N+1 query problems (33%)
- Aggregation optimization (50%)

**What makes this skill-worthy**:
- ✅ **Highly repetitive**: Same workflow every time
- ✅ **Clear structure**: Follows predictable analysis pattern
- ✅ **Time-intensive**: 12-15 min per query
- ✅ **High frequency**: ~4 times per month
- ✅ **Teachable**: Has systematic approach

**What a skill would do**:
- Automatically analyze query structure
- Identify common bottlenecks (missing indexes, N+1, etc.)
- Suggest specific optimizations
- Provide rewritten query with explanations
- Include before/after performance estimates

**Conversations to review**:
1. [Sept 22](https://claude.ai/chat/abc) - Complex JOIN taking 45 sec
2. [Oct 5](https://claude.ai/chat/def) - Subquery in WHERE clause
3. [Oct 12](https://claude.ai/chat/ghi) - Missing index on foreign key
4. [Oct 19](https://claude.ai/chat/jkl) - Aggregation without proper GROUP BY
5. [Nov 2](https://claude.ai/chat/mno) - N+1 query in ORM

Review these conversations to see what's common, then build a skill that captures your optimization approach."

## Limitations

**What Skill Finder Can Do**:
- ✅ Identify repeatable patterns in your conversations
- ✅ Show you what you do frequently
- ✅ Recommend which patterns should become skills
- ✅ Provide example conversations for each pattern
- ✅ Prioritize recommendations by frequency and impact

**What Skill Finder Cannot Do**:
- ❌ Build the skills for you (that's Skill Builder's job)
- ❌ Analyze conversations outside current project
- ❌ Access incognito conversations
- ❌ Detect patterns appearing <3 times (below threshold)
- ❌ Guarantee a skill will be useful (requires your validation)

**Important Notes**:
- Works best with 20+ conversations minimum
- More conversations = better pattern detection
- Recommendations are based on observation, not guarantees
- You must validate that patterns are actually valuable
- Links to conversations require those conversations still exist

## Privacy & Data Handling

**What gets analyzed**:
- Conversation topics and themes
- Request types and structure
- Frequency of similar requests
- Project-scoped conversations only

**What doesn't appear in results**:
- Sensitive data from conversations
- Personal information
- Specific code/data unless relevant to pattern
- Conversations from other projects

**Data presentation**:
- Examples are summarized, not quoted verbatim
- Sensitive content is redacted when necessary
- User can request removal of any example
- All analysis stays within project scope

---

**Ready to discover your skill opportunities?**

Ask: "What skills should I create?" or "Analyze my conversations for patterns"