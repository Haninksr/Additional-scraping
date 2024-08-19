

# Article Scraper

This project is a Python-based web scraper designed to extract articles from a website using its sitemap. The scraper collects metadata and content, such as the article's title, keywords, author, publication date, and other attributes. The scraped data is then saved as JSON files, organized by year and month.

## Table of Contents

- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Classes](#classes)
- [Configuration](#configuration)
- [Contributing](#contributing)
- [License](#license)

## Features

- Fetches and parses sitemaps to retrieve article URLs.
- Scrapes article details including title, author, publication date, keywords, full text, and more.
- Handles additional data such as video duration, language, description, and HTML classes.
- Saves scraped data in JSON format, organized by year and month.

## Prerequisites

- Python 3.7+
- Required Python libraries:
  - `requests`
  - `beautifulsoup4`
  - `lxml`

## Installation

1. **Clone the repository:**

   ```sh
   git clone https://github.com/your-username/article-scraper.git
   cd article-scraper
   ```

2. **Create a virtual environment (optional but recommended):**

   ```sh
   python -m venv venv
   source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
   ```

3. **Install the required dependencies:**

   ```sh
   pip install -r requirements.txt
   ```

   *Note: Create a `requirements.txt` file with the following content:*

   ```
   requests
   beautifulsoup4
   lxml
   ```

## Usage

1. **Run the scraper:**

   ```sh
   python additional_scraping.py
   ```

2. **Output:**

   - The scraper will generate JSON files in the `output/` directory, organized by year and month (e.g., `articles_2024_08.json`).

## Classes

### `Article`

A data class representing an article, with the following attributes:

- `url`: The URL of the article.
- `post_id`: The article's post ID.
- `title`: The title of the article.
- `keywords`: A list of keywords associated with the article.
- `thumbnail`: URL of the article's thumbnail image.
- `publication_date`: The date the article was published.
- `last_updated`: The date the article was last updated.
- `author`: The author's name.
- `full_text`: The full text content of the article.
- `video_duration`: The duration of any video associated with the article.
- `lang`: The language of the article.
- `description`: The description of the article.
- `classes`: A dictionary representing the classes in the article's HTML body.

### `SitemapParser`

A class that handles the fetching and parsing of sitemaps to retrieve article URLs.

- `get_monthly_sitemap()`: Retrieves the monthly sitemap URLs from the main sitemap.
- `get_article_urls(sitemap_url)`: Extracts article URLs from a given monthly sitemap.

### `ArticleScraper`

A class responsible for scraping individual articles and extracting relevant data.

- `scrape()`: Scrapes the article at the specified URL and returns an `Article` object.

### `FileUtility`

A class that handles file operations, particularly saving the scraped articles as JSON files.

- `save_to_json(articles, year, month)`: Saves a list of `Article` objects to a JSON file, named based on the specified year and month.

## Configuration

- **Sitemap URL**: Modify the `sitemap_url` in the `SitemapParser` initialization to scrape articles from a different website.

- **Output Directory**: Change the `output_dir` in the `FileUtility` class to save the JSON files in a different directory.

## Contributing

If you'd like to contribute to this project, feel free to fork the repository and submit a pull request. Please ensure that your code follows best practices and includes appropriate tests.

## License

This project is licensed under the MIT License. 

