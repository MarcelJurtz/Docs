# LaTeX Cheatsheet

## Abbildungen

```Latex
\begin{figure}
  \includegraphics[width=\linewidth *0.8]{images/ablauf-stellen-matrix.png}
  \caption[Titel im Abbildungsverzeichnis]{Abbildungstitel (Inklusive Quellenangabe (2017, S. 42))}
  \label{fig:querverweis}
\end{figure}
```

## Tabellen

```Latex
\begin{longtable}{Spaltendefinitionen}
	l: links
	c: zentriert
	r: rechts
	p{breite}: festgelegte breite, links, automatischer Zeilenumbruch
	|: Rahmen
\cline{von-bis}
\hline
\multicolumn{Anzahl verbundener Spalten}{Spaltendefinition}{Text}
```


## Verweise
```Latex
\cite{Bibtex-Key}
\nocite{Bibtex-Key}
	Erzeugt einen Eintrag im Literaturverzeichnis ohne Verweis im Text
```

## Glossar
```Latex
\newglossaryentry{label}{name={},description={}}
gls{label}
```

## Code-Snippets
```Latex
Quellcode:
\lstset{language=Java}
\lstinputlisting[caption={},label={},firstline=x,lastline=x,firstnumber=x]{src/file}
\lstinline!code!
```

## Anhang
```Latex
\appsection{Title}{Label}
\appref{Label}
```


## Stichwortverzeichnis
```Latex
\index{Stichwort}
\index{Stichwort auf Ebene 1!Stichwort auf Ebene 2}
\index{Stichwort 1|see{Stichwort 2}}
```

## Literaturverzeichnis

Erstellen mit [Jabref](jabref.sourceforge.net).
