# Example: Detailed Pattern Breakdown

This shows what Skill Finder provides when you ask for more details on a specific pattern.

---

## SQL Query Optimization Pattern - Detailed Analysis

**Frequency**: 12 conversations over 3 months  
**Average time**: 12-15 minutes per conversation  
**Total time spent**: ~2.5-3 hours  
**Category**: High Priority

### Your Typical Workflow

**Step 1: Share the slow query** (100% of cases)
- You provide the SQL query
- Usually mention current performance: "takes 45 seconds"
- Often include table sizes or row counts

**Step 2: Explain current performance** (92% of cases)
- Context about why it's too slow
- Expected vs. actual performance
- Impact on users or application

**Step 3: Ask what's wrong** (100%)
- "Why is this so slow?"
- "What's the bottleneck here?"
- "How can I optimize this?"

**Step 4: Get optimization suggestions** (100%)
- Receive analysis of query structure
- Identification of specific bottlenecks
- Recommendations for improvement

**Step 5: Ask about indexes** (75% of cases)
- "What indexes should I create?"
- "Will indexing help here?"
- Request specific index recommendations

**Step 6: Request rewritten query** (83% of cases)
- "Can you rewrite this to be faster?"
- "Show me the optimized version"
- Want side-by-side comparison

### Common Themes Across Your Queries

**JOIN optimization** (67% of cases)
- Multiple JOIN operations
- Cartesian products
- JOIN order optimization
- Missing indexes on JOIN columns

**Subquery → CTE refactoring** (42%)
- Subqueries in WHERE clauses
- Repeated subqueries
- Converting to Common Table Expressions
- Improving readability + performance

**Index recommendations** (75%)
- Missing indexes identified
- Composite index suggestions
- Index on foreign keys
- Covering indexes

**N+1 query problems** (33%)
- ORM-generated queries
- Missing eager loading
- Batch operation opportunities
- JOIN instead of separate queries

**Aggregation optimization** (50%)
- GROUP BY performance
- Aggregate function optimization
- Materialized view suggestions
- Pre-computation strategies

### What Makes This Skill-Worthy

✅ **Highly repetitive**: Same workflow every time  
✅ **Clear structure**: Follows predictable analysis pattern  
✅ **Time-intensive**: 12-15 min per query  
✅ **High frequency**: ~4 times per month  
✅ **Teachable**: Has systematic approach that can be codified

### What a Skill Would Provide

**Automated Analysis**:
- Query structure breakdown
- Bottleneck identification
- Table scan detection
- JOIN order analysis

**Specific Recommendations**:
- Index creation suggestions
- Query rewrite options
- Execution plan improvements
- Best practice checks

**Educational Component**:
- Explain WHY optimizations work
- Before/after comparisons
- Performance estimation
- Similar pattern recognition

**Output Format**:
```
# Query Optimization Analysis

## Current Query
[formatted query]

## Performance Issues Identified
1. [Issue 1 with explanation]
2. [Issue 2 with explanation]

## Recommended Optimizations

### 1. Index Recommendations
[specific indexes with CREATE statements]

### 2. Query Rewrite
[optimized query with explanations]

### 3. Additional Suggestions
[other improvements]

## Expected Performance Impact
[before/after estimates]
```

### Example Conversations to Review

**1. [Sept 22] - Complex JOIN taking 45 seconds**
- 4-table JOIN without proper indexes
- Cartesian product created by missing WHERE condition
- Solution: Added composite index + fixed JOIN condition
- Result: 45s → 2s

**2. [Oct 5] - Subquery in WHERE clause**
- Subquery executed for every row
- Same subquery appeared 3 times in query
- Solution: Converted to CTE, reused 3 times
- Result: 30s → 5s

**3. [Oct 12] - Missing index on foreign key**
- Foreign key JOIN with no index
- Full table scan on 2M row table
- Solution: Added index on FK column
- Result: 60s → 3s

**4. [Oct 19] - Aggregation without proper GROUP BY**
- COUNT(*) on entire table for each group
- Missing composite index for GROUP BY
- Solution: Added covering index with GROUP BY columns
- Result: 40s → 8s

**5. [Nov 2] - N+1 query pattern in ORM**
- Django ORM generating separate queries for each item
- Missing select_related() call
- Solution: Added eager loading
- Result: 500 queries → 1 query, 15s → 1s

### Skill Implementation Recommendations

**Core Capabilities**:
1. Query parsing and structure analysis
2. Execution plan interpretation (if available)
3. Index recommendation engine
4. Query rewriting with explanations
5. Performance estimation

**Input Format**:
```
Query: [SQL query]
Context: [Optional - table sizes, current performance]
Database: [Optional - PostgreSQL, MySQL, etc.]
```

**Success Criteria**:
- Identifies 80%+ of optimization opportunities
- Provides actionable recommendations
- Includes clear explanations
- Estimates performance improvements

**Next Steps**:
1. Review these 5 conversations in detail
2. Extract common analysis patterns
3. Define the skill's diagnostic checklist
4. Create optimization recommendation templates
5. Build the skill with Skill Builder