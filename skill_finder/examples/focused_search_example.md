# Example: Focused Search

This shows what happens when you ask Skill Finder to search for a specific pattern.

---

**User**: "Do I ask about Python debugging enough that it should be a skill?"

**Skill Finder**: "Let me search for Python debugging patterns in your conversations...

[Searching with keywords: 'debug python', 'python error', 'python bug', 'traceback', 'python exception']

Found 11 conversations involving Python debugging. Analyzing the pattern...

---

## Pattern: Python Debugging & Error Resolution

**Frequency**: 11 times (last 3 months)  
**Category**: High Priority  
**Average time per session**: 5-10 minutes  
**Total time spent**: ~1.5 hours

### What You're Doing

**Your typical debugging flow**:
1. Share error message/traceback (100% of cases)
2. Ask for explanation of what's wrong (100%)
3. Get fix suggestions (100%)
4. Sometimes ask for prevention strategies (70%)

**Example conversations**:
- [Sept 12](https://claude.ai/chat/abc123) - AttributeError in pandas dataframe
- [Oct 3](https://claude.ai/chat/def456) - TypeError in function call
- [Oct 20](https://claude.ai/chat/ghi789) - Import error with package versions
- [Nov 5](https://claude.ai/chat/jkl012) - KeyError in dictionary access
- [Nov 12](https://claude.ai/chat/mno345) - IndexError in list slicing

### Pattern Consistency

**What's consistent across all your debugging sessions**:
- ✅ You always include the full traceback
- ✅ You typically ask "why is this happening?" for root cause
- ✅ You want both the fix AND the explanation
- ✅ 70% of the time you ask "how do I prevent this in the future?"
- ✅ You prefer understanding over quick fixes

**Error types you encounter most**:
- AttributeError (27% of cases)
- TypeError (18%)
- KeyError (18%)
- ImportError (18%)
- IndexError (9%)
- Other (10%)

### Should This Be a Skill?

**YES - This is an excellent candidate**

**Why**:
1. **High frequency**: 11 times in 3 months (3.7x/month)
2. **Clear structure**: Error → Explain → Fix → Prevent
3. **Time-intensive**: 5-10 minutes per session
4. **Consistent approach**: You always want root cause understanding
5. **Teachable pattern**: Can be systematized

### What a Python Debugging Skill Would Provide

**Immediate Analysis**:
- Parse the traceback automatically
- Identify error type and root cause
- Explain what the error means in plain language

**Fix Suggestions**:
- Provide 2-3 potential fixes
- Explain why each fix works
- Show code examples
- Indicate which fix is recommended and why

**Prevention Strategies**:
- How to avoid this error in the future
- Type hints, validation, or defensive coding techniques
- IDE/linter configuration to catch earlier
- Testing approaches to prevent regression

**Educational Component**:
- Common patterns for this error type
- Related errors you should know about
- Best practices for this area of Python

**Output Format**:
```
# Python Error Analysis

## Error Summary
[Error type and quick diagnosis]

## What Happened
[Plain language explanation of root cause]

## Fix Options

### Option 1: [Fix name] ⭐ RECOMMENDED
[Code example]
Why this works: [Explanation]

### Option 2: [Alternative fix]
[Code example]
Why this works: [Explanation]

## Prevention
- [How to avoid this in the future]
- [Linting/tooling recommendations]
- [Testing approach]

## Related Patterns
[Similar errors and how to handle them]
```

### Time Savings Potential

**Current state**:
- 11 debugging sessions × 7.5 min average = ~82 minutes per 3 months
- Extrapolated: ~5.5 hours per year

**With skill**:
- Automated traceback parsing: saves 1-2 min per session
- Structured fixes: saves 2-3 min per session
- Prevention strategies: 1 min per session
- **Total savings**: 4-6 min per session
- **Annual savings**: ~2-3 hours

**But the real value is**:
- Consistency in debugging approach
- Learning prevention patterns
- Building debugging expertise over time
- Reduced frustration from repetitive errors

### Detailed Pattern Analysis

**AttributeError patterns** (3 cases):
- Accessing attributes that don't exist
- Confusing similar method names (.append vs .extend)
- Wrong object type after transformation

**TypeError patterns** (2 cases):
- Passing wrong argument types to functions
- Incompatible operations (adding string + int)

**KeyError patterns** (2 cases):
- Accessing dictionary keys that don't exist
- Using wrong key name (typo)

**ImportError patterns** (2 cases):
- Package version conflicts
- Missing dependencies

### Should You Build This Skill?

**Recommendation: YES**

**Priority: High**

**Reasons**:
1. Frequent enough to justify (3.7x/month)
2. Has clear, repeatable structure
3. Would improve debugging efficiency
4. Educational value (helps you learn patterns)
5. Could reduce error recurrence

**Next Steps**:
1. Review the 11 debugging conversations
2. Extract your systematic approach
3. Identify common fix patterns
4. Use Skill Builder to create "Python Debugging Assistant" skill
5. Test on next few debugging sessions

**Estimated time to build**: 2-3 hours  
**Annual ROI**: 2-3 hours saved + improved debugging skills

**Want me to help you build this skill, or would you like to see details on another pattern first?**