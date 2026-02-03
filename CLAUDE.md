# AI Context: Religious Orders Media Analysis Project

This document provides structured context for AI assistants to efficiently understand and work with this research project.

## Project Identity

- **Title**: Media Representation of Religious Orders in Croatian Digital Space
- **Croatian Title**: Medijska zastupljenost redovničkih zajednica u hrvatskom digitalnom prostoru
- **Type**: Academic working paper / research analysis
- **Language**: Croatian (with English documentation)
- **Framework**: Attention Economy Theory
- **Status**: Active research

## Quick Summary

This project analyzes 4+ years of Croatian digital media content to understand how religious orders (monks and nuns) are portrayed. It tests whether attention economy principles (concentration of attention, winner-takes-all dynamics) apply to religious content in media.

## Core Research Questions

1. **Concentration**: Is media attention concentrated among few orders or distributed equally?
2. **Gender**: Do male religious orders receive more attention than female?
3. **Platform**: How does coverage vary across web, Facebook, Instagram, YouTube?
4. **Dominance**: Do Franciscans dominate due to historical prominence in Croatia?
5. **Engagement**: Which orders generate the most audience interaction?

## Technical Architecture

### Data Pipeline

```
DigiKat Database (Determ API)
    ↓
RDS file (merged_comprehensive.rds)
    ↓
Keyword filtering (simple_keywords vector)
    ↓
Order classification (classify_religious_order function)
    ↓
Statistical analysis + visualization
    ↓
Quarto HTML/PDF output
```

### Key Data Structures

**Input Data** (`dta_full`):
- `DATE`: Publication date
- `TITLE`: Post title
- `FULL_TEXT`: Full content
- `MENTION_SNIPPET`: Excerpt
- `SOURCE_TYPE`: Platform (web, facebook, instagram, youtube, twitter, forum, comment)
- `FROM`: Source name
- `INTERACTIONS`: Engagement count (likes, comments, shares)
- `AUTO_SENTIMENT`: Automatic sentiment (positive, neutral, negative)
- `year`: Extracted year

**Derived Variables** (`dta`):
- `ORDER`: Specific religious order identified
- `ORDER_FAMILY`: Order family grouping
- `GENDER`: Male/Female/Unknown

### Order Classification System

**Male Order Families**:
- Franciscan Family: OFM, OFMConv (Conventuals), OFMCap (Capuchins), TOR
- Dominican Family: OP
- Jesuit: SJ
- Benedictine Family: OSB, OCist
- Carmelite Family: OCarm, OCD
- Salesian Family: SDB
- Other: Paulines, Spiritans, Verbites, Dehonians, Augustinians, etc.

**Female Order Families**:
- Franciscan Family: Franciscan Sisters, Poor Clares (OSC)
- Dominican Family: Dominican Sisters (OP)
- Benedictine Family: Benedictine Nuns (OSB)
- Carmelite Family: Carmelite Nuns (OCD)
- Salesian Family: Daughters of Mary Help of Christians (FMA)
- Congregations: Ursulines, Sisters of Charity (Milosrdnice), various others

### Key Metrics Calculated

1. **Gini Coefficient**: Measures inequality in attention distribution (0=equal, 1=total concentration)
2. **Concentration Ratios**: CR1, CR3, CR5, CR10 - share of attention by top N orders
3. **Power Law R²**: Fit to rank-frequency distribution
4. **Gender Share**: Percentage of coverage by gender
5. **Platform Distribution**: Posts and interactions by platform
6. **Sentiment Distribution**: Positive/neutral/negative by order

## Croatian Terminology Reference

| Croatian | English | Context |
|----------|---------|---------|
| redovnik | monk | Male religious |
| redovnica | nun/sister | Female religious |
| časna sestra | reverend sister | Formal term for nun |
| fra | friar | Franciscan title |
| pater | father | General religious title |
| samostan | monastery/convent | Religious house |
| provincija | province | Administrative unit |
| franjevac/franjevka | Franciscan (m/f) | Franciscan order |
| dominikanac/dominikanka | Dominican (m/f) | Dominican order |
| isusovac | Jesuit | Society of Jesus |
| benediktinac/benediktinka | Benedictine (m/f) | Benedictine order |
| kapucin | Capuchin | Franciscan branch |
| milosrdnica | Sister of Charity | Major Croatian congregation |
| uršulinka | Ursuline | Teaching order |
| klarisa | Poor Clare | Contemplative Franciscan |

## File Locations

- **Main analysis**: `R/analysis.qmd`
- **Data source**: External (`C:/Users/lsikic/Luka C/HKS/Projekti/Digitalni Kat/SHKM/DigiKat/data/merged_comprehensive.rds`)
- **HTML output**: `docs/index.html` (for GitHub Pages)
- **Figures**: Generated inline in Quarto document

## Hypotheses and Thresholds

| ID | Hypothesis | Threshold | Measurement |
|----|------------|-----------|-------------|
| H1 | Attention concentration | Gini > 0.60, R² > 0.80 | Gini coefficient, power law fit |
| H2 | Thematic selection | Spiritual < 20% | Topic classification |
| H3 | Gender asymmetry | Male > 60% | Share of posts |
| H4 | Platform variation | Chi² significant | Platform distribution |
| H5 | Franciscan dominance | Share > 30% | Franciscan family posts |
| H6 | Engagement differences | Significant variance | ANOVA on interactions |

## Common Tasks for AI Assistance

1. **Extend analysis**: Add new orders to classification, new metrics
2. **Improve visualization**: Modify ggplot themes, add new chart types
3. **Statistical tests**: Add significance tests, effect sizes
4. **Translation**: Help with Croatian-English terminology
5. **Documentation**: Improve code comments, methodology sections
6. **Debugging**: Fix R/Quarto rendering issues

## Important Considerations

- **Encoding**: Croatian uses special characters (č, ć, ž, š, đ) - UTF-8 required
- **Data volume**: Full database has millions of rows; filtered subset is manageable
- **Classification accuracy**: Keyword-based; may have false positives/negatives
- **Sentiment**: Automated classification, not manually validated
- **Time period**: 2021-2025 (adjust as data grows)

## Related Projects

- **DigiKat**: Parent project studying digital Catholicism in Croatia
- **Determ**: Media monitoring platform providing data source

## Contact/Attribution

- Project: DigiKat (Digitalni Katolicizam)
- Repository: https://github.com/lusiki/Redovnicke-zajednice

---

*This file is designed for AI context loading. It prioritizes information density and structure over narrative flow.*
