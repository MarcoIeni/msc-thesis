# Realization and performance evaluation of a hybrid UWB/WiFi indoor localization system

[![Built with Spacemacs](https://cdn.rawgit.com/syl20bnr/spacemacs/442d025779da2f62fc86c2082703697714db6514/assets/spacemacs-badge.svg)](http://spacemacs.org/)

My thesis for M.Sc. Computer Science and Engineering at Politecnico di Milano.

This thesis was written by using [org-mode](https://orgmode.org/) and [this](https://github.com/Lordmzn/ClassicThesis-at-DEIB) template.

## Overview
The main purpose of this thesis is to analyze the performances of different hybrid localization approaches, which combine in a smart way some of the most relevant indoor localization techniques.

I developed a testbed for hybrid indoor localization, which is made of a DecaWave TREK1000 evaluation kit, which utilizes Ultra-wideband (UWB) as wireless protocol and two-way ranging (TWR) as localization technique, and four Raspberry Pi 3 model B, which enable to perform localization with WiFi and RSS.
The DecaWave kit is composed of four EVB1000 boards and I configured three of them as anchors and one of them as tag.

Similarly, I configured three Raspberry Pi’s as WiFi access points and the remaining one in a way that constantly scans wireless networks in order to measures the RSSI from the three WiFi access points.

I carried out the measurements at a laboratory with different wide areas, in which I was able to reproduce both Line-of-sight (LOS) and Non-line-of-sight (NLOS) conditions.

The work was done at the IoT Lab of Politecnico di Milano.
I programmed the boards in C with ST System Workbench.

## Compiling the thesis
If you wish to compile the thesis by yourself because you are interested in doing your own thesis with org-mode read this section.

If you wish to use the same template that I used in this thesis, add the following to your emacs config in order to:

```
(with-eval-after-load 'ox-latex
    (add-to-list 'org-latex-classes
                 '("scrreprt" "\\documentclass[ twoside,
			openright,
			% letterpaper a4paper
			titlepage,
			numbers=noenddot,
      bibliography=totoc,
			headinclude, %1headlines
            		footinclude=true,
			cleardoublepage=empty,
			abstractoff, % <--- obsolete, remove (todo)
			BCOR=5mm,
			paper=a4,
fontsize=11pt]{scrreprt}"
                    ("\\chapter{%s}" . "\\chapter*{%s}")
                    ("\\section{%s}" . "\\section*{%s}")
                    ("\\subsection{%s}" . "\\subsection*{%s}")
                    ("\\subsubsection{%s}" . "\\subsubsection*{%s}"))
                 ))
```

Open the 'thesis.org' file and execute `(org-latex-export-to-pdf)` in order to export as LaTeX file and convert it to PDF file.

If you have problems with citations execute the following commands (twice if needed):
```
latex thesis
bibtex thesis
latex thesis
latex thesis
```
