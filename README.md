# Brochure-Making-LLM

Brochure-Making-LLM is an innovative Python project that leverages a Large Language Model (LLM) to create concise, professional brochures from company website content. This tool automates brochure generation by scraping websites, analyzing relevant pages, and summarizing content into markdown format, suitable for prospective customers, investors, or recruits.

---

## Features

- **Automated Website Scraping**: Extracts and processes web content with the `BeautifulSoup` library.
- **Relevance Filtering**: Identifies relevant links (e.g., About, Careers) for inclusion in the brochure using LLM-based decision-making.
- **Customizable Models**: Utilizes the `ollama` API with the specified LLM model (default: `llama3.2`).
- **Brochure Generation**: Combines website content and links into a markdown-formatted brochure.
- **Fallback Error Handling**: Includes mechanisms for JSON parsing and validation.

---

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/brochure-making-llm.git
   cd brochure-making-llm
   ```

2. Install the required dependencies:
   ```bash
   pip install requests beautifulsoup4 ollama
   ```

3. Start the Ollama API server (ensure it runs on `http://localhost:11434`).

---

## Usage

### 1. Initial Setup

- Configure the `OLLAMA_API`, `HEADERS`, and `MODEL` variables in the script according to your requirements.

### 2. Scraping a Website

- Update the `URL` and `COMPANY_NAME` variables in the script:
  ```python
  URL = "https://example.com"
  COMPANY_NAME = "ExampleCorp"
  ```

- Use the `Website` class to scrape content and links:
  ```python
  ed = Website(URL)
  print(ed.get_contents())
  print(ed.links)
  ```

### 3. Identify Relevant Links

- Generate relevant links JSON using `get_links`:
  ```python
  links = get_links(URL)
  print(links)
  ```

### 4. Generate a Brochure

- Create a markdown-formatted brochure:
  ```python
  create_brochure(COMPANY_NAME, URL)
  ```

---

## Example Output

**Sample Brochure**:
```markdown
# EdwardDonner

## About Us
EdwardDonner is dedicated to providing innovative solutions in [specific industry].

## Our Values
- Customer-centric approach
- Focus on innovation and sustainability

## Careers
Join our team to grow and make an impact. Check out our open positions [here](https://example.com/careers).
```

---

## Code Overview

### Key Components

- `Website`: Scrapes and processes web content and links.
- `get_links`: Extracts and identifies relevant links for the brochure.
- `create_brochure`: Combines content and generates markdown brochures using LLM.

### Example Functions
- **Scraping**:
  ```python
  ed = Website(URL)
  print(ed.get_contents())
  ```

- **Brochure Creation**:
  ```python
  create_brochure("ExampleCorp", "https://example.com")
  ```

---

## Dependencies

- Python 3.8+
- [requests](https://pypi.org/project/requests/)
- [BeautifulSoup4](https://pypi.org/project/beautifulsoup4/)
- [ollama](https://ollama.ai/)

---

## Contributing

Contributions are welcome! Feel free to fork this repository, make your improvements, and submit a pull request.

---

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

---

## Acknowledgements

- [Ollama](https://ollama.ai) for the LLM API.
- [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/) for HTML parsing.
