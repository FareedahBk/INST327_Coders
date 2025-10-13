# Credible Health Information Retrieval Tool

## Project Overview
The **Credible Health Information Retrieval Tool** is an analysis system designed to help users identify credible health information in their time of need. It will only present the most relevant and accurate informations from news articles and online outlets to defluence outside noise. The system gathers articles from multiple sources, analyzes content using both rule-based and AI approaches, flags potentially misleading information, and emphasizes transparency through audit trails of information provenance. 


## Team Members and Roles 
Fareedah Bakare | Research and Data | Collects credible sources and relevant keywords 

Donald Tobar | Frontend Lead | Focus is on the query interface and final visualization

Jimmy Monzon | Backend Developer | Implements API retrieval and credibility scoring

Kabir Jalloh | Quality and Documentation| Maintains Version Control 


## Installation & Setup
An end user would follow these steps:
1. Clone or Download Project
   git clone https://github.com/yourusername/credible-health-information-retrieval-tool.git
   
   cd credible-health-information-retrieval-tool

3. Install Libraries 
   pip install -r requirements.txt

4. Insert Your API key into the interactive query interface


## Key functions and Usage Examples 
1. 
def is_clickbait_phrase(text: str) -> bool:
    """Check if text contains common clickbait words or phrases.

    Args:
        text (str): The sentence or phrase to analyze.

    Returns:
        bool: True if clickbait language detected, False otherwise.

    Raises:
        TypeError: If text is not a string.

    Examples:
        >>> is_clickbait_phrase("This miracle cure will blow your mind!")
        True
        >>> is_clickbait_phrase("Regular exercise supports better sleep.")
        False
    """
    if not isinstance(text, str):
        raise TypeError("text must be a string")

    clickbait_terms = {
        "miracle", "you won't believe", "cure-all", "secret revealed",
        "instantly", "breakthrough", "guaranteed", "shocking"
    }

    text_lower = text.lower()
    return any(term in text_lower for term in clickbait_terms)

2. 
def is_absolute_language(text: str) -> bool:
    """Check if text contains absolute words.

    Args:
        text (str): Phrase being analyzed.

    Returns:
        bool: True if absolute language detected, False otherwise.

    Examples:
        >>> is_absolute_language("This medicine cures all symptoms of a cold")
        True
        >>> is_absolute_language("Healthy eating habits increase mood")
        False
    """
    # Validate input string
    validate_nonempty_str(text)

    #Phrases
    absolute_language = [
     "always",
        "never",
        "everyone",
        "no one",
        "all",
        "none",
        "completely",
        "totally",
        "absolutely",
    ]

    text_lower = text.lower()
    return any(term in text_lower for term in absolute_language)


## Function Library Overview and Organization 
## 1. Simple Functions:

 * def normalize_whitespace(text: str) -> str

 * def normalize_title(article_title):
   
 * def clean_health_query(query: str) -> str
   
 * def is_absolute_language(text: str) -> bool:
   
 * def source_reliability_score(domain: str, trusted: list[str], untrusted: list[str]) -> int

 * def validate_nonempty_str(value: str) -> str:

## 2. Medium Functions:

 * def extract_domain(url: str) -> str:

 * def extract_health_keywords(query: str) -> list[str]:

 * def collect_citations(text: str) -> List[str]:

 * def check_trusted_source(url: str) -> bool:
 
 * def source_comparison(text: str, knowledge_base: dict) -> dict

## 3. Complex Functions:
   
 * def build_claim_evidence_map(text: str) -> Dict[str, List[str]]:

 * def rank_health_articles(query_keywords: list[str], articles: list[dict]) -> list[tuple]:

 * def trace_information(article: dict, sources_graph: dict) -> list[str]


## Contribution Guidelines 
1. Communicate all changes clearly with descriptive commit messages
   
2. Include unit tests for all new functionality
   
3. Use clear and descriptive function names
   
4. Submit a pull request for each major change
