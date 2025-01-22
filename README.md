# haptic-harpsichord-nime-2025
Abstract and paper submission for NIME 2023

## Limits

- Abstract 200 Words
- Paper word limits
   - 6000 long    
   - 4000 medium
   - 2000 short


## Important Dates:
_All dates are 23:59 AoE (Anywhere on Earth)_

- **4 December, 2024**: Submission CMT site opens
- **29 January, 2025**: Paper and Music - Titles, abstracts and author lists due in CMT
- **5 February, 2025**: Paper and Music -  Final submissions due in CMT
- **19 February, 2025**: Workshop submissions due in CMT
- **2 April, 2025**: Acceptance decisions and reviews released
- **30 April, 2025**: Camera ready and presenter registration deadline
- **24 June, 2025**: NIME Workshops
- **25 - 27 June, 2025**: NIME Conference


## Structure

0. Abstract
1. Intro
2. Related Work and Motivation
   1. Conservation of Interaction
   2. Musical Instrument Haptics
3. Overview of Harpischord Mechanism
4. Design
   1. Interface (Roberto)
   2. Electronics      
   3. Software
5. Implementation
6. Conclusion
7. Acknowledgments
8. Reference


## Markdown to Tex

```sh
pandoc src/article.md -o src/article.tex
sed -i ''  '/\\tightlist/d' src/article.tex
sed -i ''  '/\\centering/d' src/article.tex
```
