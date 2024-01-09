```
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
##                                                   %
## Author: solbob                                    %
## Useful LaTeX Macros/Helpers/Snippets              %
## Desc: Aggregate snippets collected from reading   %
##       TeX manuals and stackexchange posts.        %
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
```

## Using this file
```TeX
\makeatletter
\input{custom.tex}
\makeatother
```

## Macros
```TeX
\newcommand{\etal}{\mbox{\textit{et al.}}}
\newcommand{\eg}[1]{(e.g., {#1})}
\newcommand{\ie}[1]{(i.e., {#1})}
\newcommand{\secxref}[1]{\mbox{Section~\ref{#1}}}
\newcommand{\tabxref}[1]{\mbox{Table~\ref{#1}}}
\newcommand{\stabxref}[1]{\mbox{Table~\ref{#1}}}
\newcommand{\figxref}[1]{\mbox{Figure~\ref{#1}}}
\newcommand{\codexref}[1]{\mbox{Listing~\ref{#1}}}
\newcommand{\eqxref}[1]{\mbox{Expression~(\ref{#1})}}
```


# Float Environments
## Side-by-side figures
```TeX
\usepackage[skip=2pt]{subcaption}
\begin{figure}[htb]
    \centering
    \subcaptionbox{
        TITLE\label{fig:LABEL_A}}{\includegraphics[width=0.40\linewidth]{image.png}
    }\subcaptionbox{
        TITLE\label{fig:LABEL_B}}{\includegraphics[width=0.40\linewidth]{image.png}
    }
    \caption{this is a caption.}
    \label{fig:img}
\end{figure}
```

## Resize tikz 
```TeX
\begin{figure}[htb]
    \centering
    \resizebox{0.5\textwidth}{!}{%
        \input{tikz_fig.tex}%
    }
    \caption{Caption}
    \label{fig:enter-label}
\end{figure}
```



## Custom code style
```TeX
\usepackage{listings}
\usepackage{xcolor}
\definecolor{codegreen}{rgb}{0,0.6,0}
\definecolor{codegray}{rgb}{0.5,0.5,0.5}
\definecolor{codepurple}{rgb}{0.58,0,0.82}
\definecolor{codeyellow}{rgb}{0.67,0.67,0.0}
\definecolor{backcolour}{rgb}{0.95,0.95,0.92}
\definecolor{maroon}{HTML}{AF3235}
\definecolor{codered}{HTML}{ED1B23}
\lstdefinestyle{mystyle}{
    language=Haskell,
    % backgroundcolor=\color{backcolour},   
    commentstyle=\color{codegreen},
    keywordstyle=\color{magenta},
    emph=[1]{function, definition},
    emphstyle=[1]\color{blue},
    emph=[2]{def},
    emphstyle=[2]\bfseries\color{maroon},
    otherkeywords = {->},
    keywordstyle = \bfseries\color{codepurple},
    numberstyle=\tiny\color{codegray},
    stringstyle=\color{codered},
    basicstyle=\tt\tiny,
    breakatwhitespace=false,         
    breaklines=true,                 
    captionpos=b,                    
    keepspaces=true,                 
    % numbers=left,                    
    % numbersep=5pt,                  
    showspaces=false,                
    showstringspaces=false,
    showtabs=false,                  
    tabsize=2,
    frame=lines,
    abovecaptionskip=8pt
}
```

## Side-by-side code listings
```TeX
\usepackage{caption,subcaption}
\begin{listing}[htb]
    \captionsetup{type=lstlisting}
    \begin{sublstlisting}[b]{.4\columnwidth}
        \begin{lstlisting}[style=mystyle, ]
            code a
        \end{lstlisting}
        %caption/label 
    \end{sublstlisting}\hfill
    \begin{sublstlisting}[b]{.55\columnwidth}
        \begin{lstlisting}[style=mystyle, ]
            code b    
        \end{lstlisting}
        %caption/label 
    \end{sublstlisting}
    % \caption{Caption}
\end{listing}
```


## Table spacing
```TeX
\def\arraystretch{1.5}
\setlength\tabcolsep{<whatever length>}
```

# Misc
## Symbols 
```TeX
\usepackage{pifont}
\newcommand{\cmark}{\ding{51}}%
\newcommand{\xmark}{\ding{55}}%
```

## Custom todo message + warnings
```TeX
\newcommand{\todo}[1]{{\bfseries\color{red}TODO: #1}\@latex@warning{TODO: #1!}}
```
