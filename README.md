# Manga Readers Are Mad (Or Not?): Analyzing Fan Sentiment on Anime Adaptations — What The Community Really Thinks

If you've ever been in an anime discussion, you know the drill: *"The manga was better," "They ruined the pacing," "Why did they censor that scene?"* Fans are passionate — and often critical — when their favorite manga gets adapted. But what do they actually complain about the most?

This project analyzes **over 1,000 fan comments** across **11 well-known anime series**, collected from posts on Reddit, TikTok, and MyAnimeList that specifically ask for or discuss comparisons between the anime adaptation and its source material. We go beyond simple likes and dislikes, breaking down sentiment by **specific aspects** — such as *Fidelity*, *Animation*, *Pacing*, *Voice Acting*, *Censorship*, and more — to understand *why* fans feel the way they do, which aspects drive positive reactions, and what consistently triggers negative backlash.

---

## 🎯 Objectives

- Identify the most frequently discussed aspects when comparing anime to manga.
- Measure net sentiment (positive vs. negative) per aspect and per series.
- Determine which aspects are most positively or negatively received.
- Analyze how aspects co‑occur in fan comments.
- Test the hypothesis that **Fidelity** (faithfulness to source material) is the strongest predictor of overall satisfaction.
- Rank series by "divisiveness" (standard deviation of sentiment).
- Visualize the language of fan criticism using word clouds.

---

## 📊 Dataset

- **1,780 raw comments** (after cleaning)
- **4,154 aspect–sentiment pairs** after exploding multi‑aspect comments
- **11 anime series** analyzed:

| Series | # Comments |
|--------|------------|
| Naruto | 289 |
| Hunter x Hunter | 238 |
| Demon Slayer | 230 |
| Tokyo Ghoul | 211 |
| One Piece | 140 |
| Mob Psycho 100 | 134 |
| Gintama | 116 |
| Bleach | 109 |
| K-On! | 105 |
| The Promised Neverland | 104 |
| One Punch Man | 104 |

- **Sources:** Reddit, TikTok, MyAnimeList
- **Selection criteria:** Posts explicitly comparing anime to manga or asking "which is better?"

---

## 📝 Aspects Analyzed

| Aspect | Description |
|--------|-------------|
| Fidelity | Faithfulness to source material |
| Animation | Visual quality, fluidity, art in motion |
| Pacing | Narrative speed, filler episodes |
| Art Style | Character design, backgrounds, aesthetics |
| Music/OST | Soundtrack, opening/ending themes |
| Voice Acting | Performance of seiyuu (dub/sub) |
| Censorship | Content alteration, gore, mature themes |
| Expansion | Added scenes, anime‑original content |
| Characterization | Depth, consistency, development of characters |
| Production/Staff | Director, studio, budget |
| Tone/Atmosphere | Mood, emotional impact, humor/seriousness balance |

---

## 🔍 Methodology

1. **Data Collection** – Scraped from public posts and comments.
2. **Cleaning** – Removed duplicates, non‑English, and off‑topic content.
3. **Aspect & Sentiment Labeling** – Each comment was manually/automatically tagged with one or more aspects and an overall sentiment (positive, neutral, negative).
4. **Explosion** – Multi‑aspect comments were exploded so each aspect–sentiment pair becomes a separate row.
5. **Analysis**:
   - Frequency counts of aspects
   - Net sentiment per aspect and per series
   - Positive proportion per aspect
   - Co‑occurrence matrix (raw and Jaccard similarity)
   - Correlation between *Fidelity* sentiment and overall sentiment
   - Standard deviation of overall sentiment per series (divisiveness)
   - Word clouds per series

---

## 📈 Key Findings

### 1. Overall Sentiment
- **Negative leads** (44.7%), followed by **Positive** (32.9%), then **Neutral** (22.4%).
- Most discussions are critical, though positive opinions remain substantial.

### 2. Most Discussed Aspects
- **Fidelity** (20.7% of mentions) dominates – adaptation faithfulness is the #1 fan concern.
- **Animation** (16.9%) and **Pacing** (11.8%) follow.
- **Art Style** (11.3%) and **Music/OST** (10.4%) are also major topics.

### 3. Net Sentiment Heatmap
- **Positive clusters:** *Music/OST*, *Voice Acting*, *Expansion*, *Animation*.
- **Negative clusters:** *Fidelity*, *Pacing*, *Characterization*, *Censorship* (in many series).
- Series like *Mob Psycho 100* and *Gintama* show strong positive net sentiment; *Tokyo Ghoul* and *The Promised Neverland* are heavily negative.

### 4. Positive Breakdown (Proportions)
- **Music/OST** (82.0%) and **Voice Acting** (81.7%) are the most consistently praised.
- **Fidelity** (37.2%) and **Pacing** (26.5%) have the lowest positive rates – fans are rarely happy with these when they criticize.

### 5. Co‑occurrence of Aspects
- **Fidelity** strongly co‑occurs with *Pacing*, *Art Style*, and *Animation*.
- **Music/OST** and *Voice Acting* form a tight audiovisual cluster.
- **Animation** and *Art Style* often appear together.

### 6. Hypothesis: Fidelity Drives Overall Satisfaction
- **Spearman correlation ρ = 0.67** (p < 0.0001) – strong positive monotonic relationship.
- When fans praise fidelity, they tend to praise the series overall; when they criticize fidelity, overall sentiment is also negative.

### 7. Most Divisive Series (highest sentiment std dev)
| Series | Std Dev | Controversy Score |
|--------|---------|-------------------|
| One Punch Man | 0.844 | 0.1345 |
| Hunter x Hunter | 0.837 | 0.1250 |
| Naruto | 0.781 | 0.1026 |
| Demon Slayer | 0.777 | 0.0919 |
| Bleach | 0.776 | 0.0990 |

- Low divisiveness: *Tokyo Ghoul* (uniformly negative) and *Mob Psycho 100* (uniformly positive).

### 8. Word Clouds
- Common positive words: *amazing*, *perfect*, *beautiful*, *faithful*, *masterpiece*.
- Common negative words: *filler*, *slow*, *ruined*, *cringe*, *skip*, *disappointing*.

---

## 📁 Repository Structure

