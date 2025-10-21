Organise, categorise, and analyse user needs to uncover patterns, duplicates, and gaps.

## Input

- Collection of user need `.md` files
- Existing categories, themes, and journey stages (from current needs)

## What This Does

This command processes a collection of user needs to improve quality, consistency, and analytical value:

1. **Standardises structure** - Ensures all needs follow the template format correctly
2. **Assigns metadata** - Adds categories, themes, and journey stage tags
3. **Identifies patterns** - Finds duplicates, gaps, and common outcomes
4. **Improves consistency** - Standardises similar language across related needs
5. **Documents insights** - Creates analysis report and research recommendations

## Skills Used

This command orchestrates these skills:

- `validate-need-quality` - Verify needs meet quality standards
- `identify-need-patterns` - Find themes, duplicates, and gaps across the collection
- `render-user-need` - Update needs with new metadata and standardised formatting

## Expected Outputs

- Standardised need files with complete, consistent metadata
- Categories and themes assigned across all needs
- Analysis report: `example-1/outputs/needs-analysis.md`
- Research questions: `example-1/outputs/research-questions.md` (if gaps identified)
- Archived duplicates: `example-1/outputs/needs/archived/` (if merges performed)

## Analysis Report Structure

The command generates `example-1/outputs/needs-analysis.md` containing:

- Summary statistics (total needs, user types, journey stages, categories)
- Distribution analysis by journey stage and user type
- Common patterns and themes
- Duplicates merged
- Gaps identified
- Recommendations for further research or refinement

## Success Indicators

- ✓ Duplicates merged (verified via similarity searches)
- ✓ Categories assigned (no empty category fields)
- ✓ Analysis report created
- ✓ Gaps documented (research questions file exists)

## Related Commands

- [sketch-user-needs](commands/discovery/research/process/sketch-user-needs.md) — Initial extraction of needs from research
- [map-journey](commands/discovery/explore/map-journey.md) — Identify stages for journey stage mapping

## References

See [user-needs-refinement-process](references/user-needs-refinement-process.md) and [user-needs-best-practices](references/user-needs-best-practices.md) for detailed methodology and examples.
