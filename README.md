# Media Representation of Religious Orders in Croatian Digital Space

## Medijska zastupljenost redovničkih zajednica u hrvatskom digitalnom prostoru

### Overview

This research project analyzes how Croatian digital media portrays members of religious orders (monks and nuns) using the theoretical framework of attention economy. Using the DigiKat database of digital content from 2021 to 2025, we filter posts containing references to religious communities and analyze the distribution of media attention, gender asymmetries, platform differences, and dominance of specific orders.

### Working Paper

**[View the full analysis (HTML version)](https://raw.githack.com/lusiki/Redovnicke-zajednice/main/R/analysis_v3.html)**

**[Download the full analysis (Word version)](https://github.com/lusiki/Redovnicke-zajednice/raw/main/R/analysis_v4.docx)**

### Research Questions

1. Which religious community receives the most media attention?
2. Is there a difference in representation between male and female religious communities?
3. On which platforms is most content about religious orders published?
4. Attention concentration: Do all orders receive equal attention or does a small number dominate?

### Hypotheses

| Hypothesis | Prediction | Measurement |
|------------|------------|-------------|
| H1: Attention Concentration | Small number of orders receives majority of attention | Gini coefficient > 0.60 |
| H2: Thematic Selection | Media prefer secular topics | Spiritual topics < 20% |
| H3: Gender Asymmetry | Male orders receive more attention | Male share > 60% |
| H4: Platform Differences | Different platforms, different patterns | Significant variation |
| H5: Franciscan Dominance | Franciscans dominate media space | Share > 30% |
| H6: Engagement | Different orders generate different engagement | Significant differences |

### Project Structure

```
Redovnicke-zajednice/
├── README.md              # This file
├── CLAUDE.md              # AI context file for efficient consumption
├── .gitignore             # Git ignore rules
├── R/
│   ├── analysis.qmd       # Main Quarto analysis document
│   └── analysis.rmarkdown # R Markdown version
├── docs/                  # GitHub Pages output (HTML)
│   └── index.html         # Rendered analysis
└── output/                # Generated outputs (figures, tables)
```

### Data Source

- **Database**: DigiKat (Digitalni Katolicizam) project database
- **Period**: 2021-2025
- **Source**: Croatian digital media content collected via Determ media monitoring platform
- **Platforms**: Web portals, Facebook, Instagram, YouTube, Twitter, forums, comments

### Methodology

1. **Keyword-based filtering**: Comprehensive list of Croatian terms for religious orders (male and female), including specific order names, generic terms, and institutional references
2. **Classification system**: Automatic categorization by order family (Franciscan, Dominican, Jesuit, Benedictine, etc.), gender, and specific order
3. **Metrics**: Post counts, interaction totals, Gini coefficients, sentiment analysis

### Key Findings Summary

The analysis reveals:
- High concentration of media attention among a small number of religious orders
- Significant platform variation in coverage patterns
- Gender-based differences in media representation
- Predominantly positive sentiment in coverage

### Requirements

To reproduce the analysis:

```r
# Required R packages
install.packages(c(
  "tidyverse", "data.table", "scales", "ggplot2",
  "knitr", "kableExtra", "ineq", "viridis",
  "lubridate", "tidytext", "stringi"
))
```

### Authors

DigiKat Project Team

### License

This research is part of the DigiKat (Digitalni Katolicizam) project.

### Citation

If you use this research, please cite:

```
DigiKat Project (2025). Media Representation of Religious Orders in Croatian Digital Space:
An Attention Economy Analysis. Working Paper.
Available at: https://lusiki.github.io/Redovnicke-zajednice/
```

---

*Keywords: attention economy, religious orders, media representation, digital media, Croatia, Franciscans, Dominicans, Jesuits, nuns, monks*
