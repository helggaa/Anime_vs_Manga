# Manga Readers Are Mad (Or Not?): Analyzing Fan Sentiment on Anime Adaptations — What The Community Really Thinks

If you've ever been in an anime discussion, you know the drill: *"The manga was better," "They ruined the pacing," "Why did they censor that scene?"* Fans are passionate — and often critical — when their favorite manga gets adapted. But what do they actually complain about the most?

This project analyzes **over 1,000 fan comments** across **11 well-known anime series**, collected from posts on Reddit, TikTok, and MyAnimeList that specifically ask for or discuss comparisons between the anime adaptation and its source material. We break down sentiment by aspect, moving beyond simple likes and dislikes to understand why fans feel the way they do—which aspects drive positive reactions, and what consistently triggers negative backlash.

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
- **Selection criteria:** Posts explicitly comparing anime to manga or asking "which is better?" and whatnot

---

## 📝 Aspects of the Dataset

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

## 🏷️ Sentiment Definition

In this analysis, each comment is labeled with an **overall sentiment** toward the anime adaptation compared to its source material:

- **Negative** – The commenter prefers the manga, criticizes the anime, or expresses disappointment with the adaptation. (e.g., *"The manga is amazing."*)

- **Positive** – The commenter prefers the anime, praises the adaptation, or expresses dissatisfaction with the manga. (e.g., *"I prefer the anime more than the manga."*)

- **Neutral** – The commenter has mixed feelings, finds both versions equally good/bad, or simply states facts without clear preference.

> 💡 **Note:** A "positive" sentiment does **not** always mean the fan loves the anime unconditionally — it can also mean they dislike the manga. Conversely, a "negative" sentiment often indicates a preference for the manga over the anime.

---

## 🔍 Methodology

1. **Data Collection** – Scraped from public posts and comments.
2. **Cleaning** – Removed duplicates and off‑topic content.
3. **Aspect & Sentiment Labeling** – Each comment was manually/automatically tagged with one or more aspects and an overall sentiment (positive, neutral, negative).
4. **Explosion** – Multi‑aspect comments were exploded so each aspect–sentiment pair becomes a separate row.
5. **Analysis**:
   - Overall sentiment across all series
   - Standard deviation of overall sentiment per series (divisiveness)
   - Frequency counts of aspects
   - Net sentiment per aspect and per series
   - Positive proportion per aspect
   - Co‑occurrence matrix (raw and Jaccard similarity)
   - Correlation between *Fidelity* sentiment and overall sentiment
   - Word clouds per series and across all series

---

## 📈 Key Findings

1.  **Predominantly Critical:** Overall, discussions lean more towards negative sentiment (44.7%), suggesting fans are often more vocal about their disappointments than their praises, though positive opinions remain substantial (32.9%).

2.  **Divisiveness Varies Greatly:** Series like ***'One Punch Man'*** and ***'Hunter x Hunter'*** emerged as the most divisive, characterized by high standard deviations in sentiment, indicating a strong mix of both positive and negative reactions. Conversely, ***'Tokyo Ghoul'*** showed the least divisiveness, primarily due to a uniformly negative reception.

3.  **'Fidelity' is Paramount:** *'Fidelity'* (faithfulness to the source material) is by far the **most discussed aspect**, leading to a strong, statistically significant positive correlation with overall sentiment (Spearman ρ = 0.67). This confirms that how well an adaptation sticks to its source material is a critical determinant of fan satisfaction.

4.  **Audiovisual Aspects Are Strengths:** *'Music/OST'* and *'Voice Acting'* consistently receive the highest positive rates (82.0% and 81.7% respectively), highlighting audio quality as a reliable strength in anime adaptations. *'Animation'* also generally garners positive sentiment.

5.  **'Pacing' and 'Characterization' Are Weaknesses:** Conversely, *'Pacing'* (26.5% positive rate) and *'Characterization'* (32.3% positive rate) are the most frequent targets of criticism, indicating these narrative and developmental elements are common pain points in adaptations.

6.  **Interconnected Criticisms:** Aspect co-occurrence analysis shows that *'Fidelity'* is a central connector, frequently discussed alongside *'Pacing'*, *'Animation'*, and *'Art Style'*. This suggests that a perceived lack of faithfulness often triggers broader criticisms related to narrative flow and visual execution. Audiovisual elements (*'Animation'*, *'Music/OST'*, *'Voice Acting'*) also form a tightly interlinked cluster.

---

## 🚧 Limitations

- **Data Imbalance:** The number of comments varies significantly across series (e.g., `Naruto` with 289 comments vs. `One Punch Man` with 104). Aspects are also unevenly represented—*Fidelity* dominates (833 mentions), while *Production/Staff* (116) and *Tone/Atmosphere* (113) are underrepresented.

- **Annotation Consistency:** Two human annotators labeled sentiment and aspects, which may introduce subjectivity and inconsistency, especially for ambiguous or sarcastic comments.

- **Simplistic Sentiment Scale:** The three‑point scale (`positive`/`neutral`/`negative`) oversimplifies nuanced opinions. A more granular scale or separate labels for "prefers anime" vs. "prefers manga" could provide clearer insights.

- **Aspect Coverage:** Other potentially relevant aspects were not included, which might miss additional patterns.

- **Platform and Selection Bias:** Data was collected only from posts explicitly comparing anime to manga. Fans who engage in such discussions may hold stronger opinions than the general audience, and platforms like Reddit and TikTok have their own demographic biases.

- **Lack of Dataset Transparency:** Direct links to original comments are not provided, which limits verifiability and reproducibility. Future work should consider making the dataset more transparent (e.g., through anonymized traceable references) to confirm the authenticity of the scraped data.

- **Temporal Context Ignored:** The analysis does not account for when comments were posted. Sentiment toward an adaptation can shift over time (e.g., after a poorly received sequel season or director's statement). A longitudinal study could capture such dynamics.
