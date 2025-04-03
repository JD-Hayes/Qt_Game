# Re-create the LaTeX assignment file after execution state reset

updated_assignment = r"""
\documentclass[12pt]{article}
\usepackage{geometry}
\geometry{margin=1in}
\usepackage{enumitem}
\usepackage{xcolor}
\usepackage{titlesec}
\titleformat{\section}{\Large\bfseries}{\thesection}{1em}{}

\title{CSC Frameworks Assignment: Turn-Based Game with Crow + Qt}
\author{}
\date{}

\begin{document}

\maketitle

\section*{Overview}

In this assignment, you will design and implement a small turn-based adventure game using a \textbf{Crow (C++) backend server} and a \textbf{Qt (C++) graphical frontend}. Your player can move, encounter enemies, attack them, use potions, and level up. This is a foundational exercise in building real-time connected applications using modern C++ frameworks.

\section*{Goals}
\begin{itemize}
  \item Practice building and integrating a RESTful backend using Crow
  \item Learn to create dynamic UIs with Qt and communicate using JSON
  \item Model a persistent game state shared across requests
  \item Demonstrate ability to test and explain full-stack application behavior
\end{itemize}

\section{Requirements}

You must implement the following features:

\subsection*{1. Movement System}
\begin{itemize}
  \item Add directional buttons (North, South, East, West) to the Qt frontend
  \item Each button sends a POST request to \texttt{/move} with a direction
  \item The backend updates and returns the player's position
\end{itemize}

\subsection*{2. Enemy Encounter}
\begin{itemize}
  \item At a fixed position (e.g., \texttt{x=2, y=1}), an enemy appears
  \item The server sets \texttt{enemy\_alive = true} and sends an encounter message
  \item The frontend displays “An enemy appears!” to the user
\end{itemize}

\subsection*{3. Turn-Based Combat}
\begin{itemize}
  \item Add an “Attack” button in Qt
  \item Each attack reduces enemy HP; if still alive, the enemy strikes back
  \item When enemy HP reaches 0, the player levels up and enemy resets
\end{itemize}

\subsection*{4. Potion System}
\begin{itemize}
  \item A “Use Potion” button increases player HP up to a maximum
  \item The server handles this and returns the updated HP
\end{itemize}

\subsection*{5. State Display}
\begin{itemize}
  \item The Qt UI should show messages, player HP, level, and position
  \item Make use of QLabel and layout tools to clearly organize feedback
\end{itemize}

\section{Deliverables}

You must submit the following items to the provided GitHub Classroom repository:

\begin{enumerate}
  \item \texttt{crow\_main.cpp} — backend server source file
  \item \texttt{qt\_main.cpp} — frontend UI and logic source file
  \item \texttt{README.md} — instructions for building and running both components
  \item \textbf{Panopto video} — 5–7 minute screen recording that:
  \begin{itemize}
    \item Shows the application running
    \item Walks through key parts of your code
    \item Explains how the client and server interact
  \end{itemize}
\end{enumerate}

\section{Grading Rubric (100 points)}

\begin{tabular}{p{0.6\textwidth}r}
\textbf{1. UI and Backend Design Clarity} & 25 pts \\
Clear structure, logical UI layout, clean game state modeling & \\
\textbf{2. Application Implementation} & 25 pts \\
Functioning features (movement, combat, potion, level-up) & \\
\textbf{3. Code Quality and Readability} & 25 pts \\
Consistent style, helpful comments, good separation of concerns & \\
\textbf{4. Panopto Video Explanation} & 25 pts \\
Explains logic, demonstrates interaction, is clear and complete & \\
\end{tabular}

\section*{Bonus (up to 6 extra points)}
\begin{itemize}
  \item \textbf{Visited Tile Tracking (2\%)} – Tiles the player has moved through appear visually different in the UI.
  \item \textbf{Minimap View (2\%)} – A smaller view of the full scene is displayed beside the main game view.
  \item \textbf{Animated Movement (2\%)} – Player movement is animated using Qt transitions instead of jumping.
\end{itemize}

\end{document}
"""

with open("/mnt/data/turn_based_game_assignment_with_bonus.tex", "w") as f:
    f.write(updated_assignment)

"/mnt/data/turn_based_game_assignment_with_bonus.tex"
