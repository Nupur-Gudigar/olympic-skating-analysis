# 🥇 Olympic Figure Skating: Art vs Technical Power (2006–2026)

![Banner](./skating.gif)

## 👋 Hi, I'm Nupur!!

Just another chronically online girl who fell into a very specific internet rabbit hole.

It started with **Alysa Liu**, who felt like a shot of espresso to me. Watching her skate made me want to understand figure skating, and suddenly I was binge-learning the sport from YouTubers. Once I understood scoring, I couldn't stop thinking about one debate fans constantly argue about:

> 🎯 In Olympic figure skating, does technical difficulty win medals or does artistry?

Everything in this project is built to answer that one question.

**📊 [PROJECT LINK →](https://nupur-gudigar.github.io/olympic-skating-analysis/)**  *Turn music on for a cute surprise* 🎵

**📓 Python Notebook:** This repository contains the full analysis notebook with code, visualizations, and insights

## 📖 What This Project Is About

This data story analyzes **six Olympic Games (2006–2026)** in men's and women's singles figure skating.

I explain the scoring system in simple terms, build a custom **Tech Dominance metric**, compare medalists vs non-medalists, and visualize judging trends across eras — all designed to be accessible to non-technical readers.

### The Key Metric: `tech_dominance`

```
tech_dominance = TES / (TES + PCS)
```

This ratio measures what percentage of a skater's total score comes from technical elements (jumps, spins) vs artistic components (choreography, interpretation). It's era-neutral, meaning we can compare a 2006 performance to a 2026 performance fairly — because the sport's scoring system has evolved dramatically over 20 years.




## 🗃️ The Dataset

**Here's the thing:** there was no ready-made dataset for this. I spent way too long searching Kaggle before accepting it simply didn't exist. Figure skating is niche, and nobody had compiled historical Olympic score sheets with both technical (TES) and artistic (PCS) components across multiple years.

So I built it myself.

### Data Source
All data comes from **[ISU](https://www.isuresults.com/)** (International Skating Union) — the official governing body of figure skating. They archive every competition result, broken down by segment and score component. It's all there publicly, just not in CSV format.

I tried web scraping first. Keyword: *tried*. It was taking longer to debug than to just do it manually. So I opened the result pages, compiled the data in Excel, and exported two CSV files with different levels of granularity.

### The Two Datasets

#### 🔹 `olympics_singles_long.csv`
One row per skater **per segment** (Short Program and Free Skate separately)

**Columns:** `year`, `gender`, `segment`, `rank_segment`, `skater`, `nation`, `tss`, `tes`, `pcs`, `ded`

**288 rows** — every single Olympic performance since 2006

#### 🔹 `olympics_singles_agg.csv`  
One row per skater **per Olympics** with everything aggregated

**Columns:** `year`, `gender`, `final_rank`, `skater`, `nation`, `total_tss`, `sp_rank`, `fs_rank`, `tss_sp`, `tes_sp`, `pcs_sp`, `tss_fs`, `tes_fs`, `pcs_fs`, `tes_total`, `pcs_total`, `tech_dominance`, `medal`

This is the main file used for analysis. The `tech_dominance` column was calculated in Excel and then validated in Python.

**Coverage:**  
- **Years:** 2006, 2010, 2014, 2018, 2022, 2026  
- **Events:** Men's Singles, Women's Singles  
- **Data Points:** Every skater who competed in the Short Program

### Why I'm Proud of This

It took the most time, but it made the project **completely original**. I might publish this dataset to Kaggle once the project is polished — because if I had to build it from scratch, someone else probably struggled to find it too. Figure skating deserves better dataset representation.

## 🎬 What the Analysis Shows

The notebook is structured like a story with three acts:

### Act 1: The Arena
A scatter plot of every Olympic performance since 2006. Each dot is one skater, one Games. Gold medalists cluster toward the right side — higher technical dominance. You can find high-scoring skaters across the whole spectrum, but champions lean technical.

### Act 2: The Sport Evolves  
Has technical dominance always predicted gold? Or has Olympic skating quietly shifted over time? This section tracks gold medalists year by year for both men and women, revealing how the sport's priorities have evolved across eras.

### Act 3: The Full Picture
Statistical breakdowns, interactive Plotly charts, and deeper dives into the relationship between tech_dominance, total scores, and medal outcomes. This is where we get into the weeds — comparing Short Program vs Free Skate importance, gender differences, and outlier performances.

**Key Insight:** Artistry keeps you in the game. Technical difficulty wins it.

## 🛠️ Tech Stack

- **Python** — Data analysis and visualization
- **Pandas** — Data manipulation
- **Plotly** — Interactive charts (heavily used in the notebook and webpage)
- **Matplotlib** — Static visualizations
- **Excel** — Initial data compilation and calculation
- **HTML/CSS/JS** — Custom webpage design
- **GitHub Pages** — Hosting the live project




## Final Thoughts

This started as curiosity about one skater and turned into a full data project. I learned how to manually build datasets, validate metrics, choose the right visualizations, and present findings in a way that doesn't require a statistics degree to understand.

If you're into figure skating, Python, or just like Inspiring People, I hope you enjoyed this. And if you're still here reading this README... thank you. That means a lot.

## 🙏 Acknowledgments

- **ISU (International Skating Union)**
- **Figure skating YouTubers** (especially [Cathy](https://www.youtube.com/watch?v=6s8zNzJ-BaU)) for making the scoring system actually understandable
- **Alysa Liu** for being the internet rabbit hole that started it all
- **The figure skating community**
- **Pink Pantheress and Zara Larsson for the catchy song**