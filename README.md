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

## Abstract 

This paper describes the design and creation of an electronically augmented replica of a historical harpsichord keyboard with a typical 17th-century Italian layout to create a digital musical instrument. 
The keyboard was commissioned for exhibition in a musical instrument museum to enhance the visitor experience by providing an interface to digitised versions of instruments within the collection. 
The replica balances the competing demands of historical authenticity, public accessibility, and preservation. 
It replicates the original instrument's tactile feedback and mechanical resistance using historically informed construction techniques. Optical sensors integrated within the mechanism capture the jacks' motion data, enabling MIDI message generation. 
This work situates itself within broader discussions on the role of technology in museums. 
A keyboard interface of this type offers an opportunity to enhance visitor interaction with musical heritage while safeguarding delicate artefacts. 
The paper examines the keyboard's design principles, technical implementation, and implications, emphasising its contribution to public engagement and the long-term preservation of musical heritage.


## Markdown to Tex

```sh
pandoc src/article.md -o src/article.tex
sed -i ''  '/\\tightlist/d' src/article.tex
sed -i ''  '/\\centering/d' src/article.tex
```

## Tex to Markdown 

images reduce with 

```
sips -Z 640 *.jpg
```

```
pandoc -F pandoc-crossref --citeproc main.tex -o article.md -t markdown_strict+footnotes 
```


