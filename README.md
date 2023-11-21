# Basic-api

\documentclass{article}

\title{Movie API with FastAPI}
\date{}

\begin{document}

\maketitle

\section*{Overview}

This is a simple FastAPI application that provides CRUD operations for managing movies. It includes endpoints for listing movies, retrieving a specific movie by ID, creating a new movie, updating an existing movie, and deleting a movie. Additionally, there's an authentication mechanism using JWT to secure certain endpoints.

\section*{Endpoints}

\subsection*{1. Home}

\begin{itemize}
  \item \textbf{URL}: \texttt{/}
  \item \textbf{Method}: \texttt{GET}
  \item \textbf{Description}: Returns a simple HTML response with the message "Hello world."
\end{itemize}

\subsection*{2. Login}

\begin{itemize}
  \item \textbf{URL}: \texttt{/login}
  \item \textbf{Method}: \texttt{POST}
  \item \textbf{Description}: Authenticates a user and generates a JWT token.
  \item \textbf{Request Body}:
  \begin{verbatim}
  {
    "email": "admin@gmail.com",
    "password": "admin"
  }
  \end{verbatim}
  \item \textbf{Response}:
  \begin{itemize}
    \item Successful login:
    \begin{verbatim}
    {
      "token": "<JWT_TOKEN>"
    }
    \end{verbatim}
    \item Unsuccessful login:
    \begin{verbatim}
    {
      "detail": "Credenciales invalidas"
    }
    \end{verbatim}
  \end{itemize}
\end{itemize}

\subsection*{3. Get Movies}

\begin{itemize}
  \item \textbf{URL}: \texttt{/movies}
  \item \textbf{Method}: \texttt{GET}
  \item \textbf{Description}: Retrieves a list of movies.
  \item \textbf{Authentication}: Requires a valid JWT token for access.
\end{itemize}

\subsection*{4. Get Movie by ID}

\begin{itemize}
  \item \textbf{URL}: \texttt{/movies/\{id\}}
  \item \textbf{Method}: \texttt{GET}
  \item \textbf{Description}: Retrieves details of a specific movie by ID.
  \item \textbf{Path Parameter}:
  \begin{itemize}
    \item \texttt{id}: ID of the movie (integer).
  \end{itemize}
\end{itemize}

\subsection*{5. Get Movies by Category}

\begin{itemize}
  \item \textbf{URL}: \texttt{/movies/}
  \item \textbf{Method}: \texttt{GET}
  \item \textbf{Description}: Retrieves a list of movies filtered by category.
  \item \textbf{Query Parameter}:
  \begin{itemize}
    \item \texttt{category}: Movie category (string).
  \end{itemize}
\end{itemize}

\subsection*{6. Create Movie}

\begin{itemize}
  \item \textbf{URL}: \texttt{/movies}
  \item \textbf{Method}: \texttt{POST}
  \item \textbf{Description}: Adds a new movie to the list.
  \item \textbf{Request Body}:
  \begin{verbatim}
  {
    "title": "Movie Title",
    "overview": "Movie Overview",
    "year": 2022,
    "rating": 9.5,
    "category": "Action"
  }
  \end{verbatim}
\end{itemize}

\subsection*{7. Update Movie}

\begin{itemize}
  \item \textbf{URL}: \texttt{/movies/\{id\}}
  \item \textbf{Method}: \texttt{PUT}
  \item \textbf{Description}: Updates details of a specific movie by ID.
  \item \textbf{Path Parameter}:
  \begin{itemize}
    \item \texttt{id}: ID of the movie (integer).
  \end{itemize}
  \item \textbf{Request Body}:
  \begin{verbatim}
  {
    "title": "Updated Movie Title",
    "overview": "Updated Movie Overview",
    "year": 2023,
    "rating": 8.0,
    "category": "Adventure"
  }
  \end{verbatim}
\end{itemize}

\subsection*{8. Delete Movie}

\begin{itemize}
  \item \textbf{URL}: \texttt{/movies/\{id\}}
  \item \textbf{Method}: \texttt{DELETE}
  \item \textbf{Description}: Deletes a specific movie by ID.
  \item \textbf{Path Parameter}:
  \begin{itemize}
    \item \texttt{id}: ID of the movie (integer).
  \end{itemize}
\end{itemize}

\section*{Authentication}

JWT (JSON Web Token) is used for authentication. To access certain endpoints, include the JWT token in the \texttt{Authorization} header.

\end{document}