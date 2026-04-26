# Bluesky Posts Dataset for Depression Detection

This repository provides a curated dataset of public posts from Bluesky, designed to support research in natural language processing and digital mental health. The dataset includes anonymized textual content and engagement-related metadata, along with expert annotations indicating the presence of depression-related linguistic cues.

---

## Overview

The dataset contains **4,568 English-language posts**, of which **514 (11.2%)** are labeled as *depressive*. Labels reflect the presence of linguistic signals associated with depressive states and **do not constitute clinical diagnoses**.

The data has been preprocessed to improve quality and usability, including:

* Removal of emojis
* Removal of duplicate posts
* Anonymization of personally identifiable information (PII)

---

## Dataset Schema

Each row corresponds to a single post with the following attributes:

| Column        | Type      | Description                                                    |
| ------------- | --------- | -------------------------------------------------------------- |
| `text`        | string    | Anonymized textual content of the post                         |
| `repostCount` | int       | Number of reposts                                              |
| `replyCount`  | int       | Number of replies                                              |
| `likeCount`   | int       | Number of likes                                                |
| `link`        | binary    | Indicates whether the post contains a link (1 = yes, 0 = no)   |
| `image`       | binary    | Indicates whether the post contains an image (1 = yes, 0 = no) |
| `createdAt`   | timestamp | Timestamp of the post based on the author's local timezone     |
| `depressive`  | binary    | Annotation label (1 = depressive, 0 = non-depressive)          |

---

## Data Collection and Ethics

Posts were collected using the Apify scraping tool, restricted to **publicly available content** in accordance with ethical standards for digital mental health research (e.g., Digital Mental Health Research).

To preserve user privacy:

* Usernames, URLs, and other identifying information were removed
* Only anonymized text and aggregated metadata are retained
* Data sharing is limited to minimize risks of re-identification

Despite these precautions, complete anonymization of text data cannot be guaranteed due to potential re-identification via linguistic patterns. Users of this dataset are expected to follow ethical guidelines and avoid attempts to re-identify individuals.

---

## Data Retrieval Strategy

Initial data collection was guided by a lexicon of depression-related expressions derived from:

* Clinical frameworks such as PHQ-9
* Diagnostic criteria from the DSM-5
* Prior NLP research (e.g., DEPTWEET)

This approach aimed to balance clinical relevance with informal language commonly observed in social media.

---

## Annotation Process

Posts were manually annotated by **two clinical psychologists** using a binary labeling scheme:

* `depressive` (presence of depression-related cues)
* `non-depressive`

### Annotation protocol:

* Calibration phase with 200 jointly reviewed posts
* Resolution of ambiguous cases (e.g., irony, metaphor, third-person references)
* Consensus-based disagreement resolution

### Inter-annotator agreement:

* Cohen’s Kappa: **0.81** (substantial agreement)

---

## Preprocessing Pipeline

The dataset underwent the following preprocessing steps:

1. Removal of emojis
2. Deduplication of posts
3. Filtering of ambiguous content (e.g., unclear intent, metaphorical usage without self-disclosure)
4. Anonymization of text and metadata

These steps were applied to reduce noise and improve the interpretability of annotations.

---

## Limitations

* Labels reflect **linguistic signals**, not clinical diagnoses
* Potential bias due to lexicon-based data collection
* Residual risk of re-identification through writing style
* Class imbalance (approximately 11% depressive posts)

---

## Usage

This dataset is intended for:

* Text classification and NLP research
* Mental health signal detection
* Social media analysis

It is **not intended for clinical or diagnostic use**.

---

## Citation

If you use this dataset, please cite the relevant academic work or repository.

---

## License

Please refer to the repository’s license file for terms of use.

---

## Contact

For questions or collaboration inquiries, please open an issue in this repository.
