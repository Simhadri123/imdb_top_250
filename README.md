# IMDb Top 250 Movies Scraper

This repository contains an automated workflow to scrape and update the IMDb Top 250 movies list.

## Features

- **Automated Scraping:** Uses a Python script (`scrape_movies.py`) to fetch the latest IMDb Top 250 movies.
- **Scheduled Updates:** GitHub Actions workflow runs every hour at the 59th minute and can also be triggered manually.
- **Dependency Management:** Uses [uv](https://github.com/astral-sh/uv) for fast Python dependency management.
- **Automatic Commit:** Scraped data is committed and pushed automatically to the repository.

## Workflow Overview

The workflow is defined in [`.github/workflows/imdb_top_250.yaml`](./.github/workflows/imdb_top_250.yaml):

- **Checkout repository**
- **Install uv**
- **Run scraper:**  
  ```sh
  uv run --with httpx,lxml,cssselect python scrape_movies.py
  ```
- **Set git user email:**  
  Sets the git user email for commits.
- **Commit and push changes:**  
  Commits updated `.json` files with a message and pushes to the repository.

## Usage

1. **Clone the repository:**
    ```sh
    git clone https://github.com/yourusername/your-repo.git
    cd your-repo
    ```

2. **Manual Run:**
    - You can trigger the workflow manually from the GitHub Actions tab.

3. **Scheduled Run:**
    - The workflow runs automatically every hour.

## Requirements

- Python 3.8+
- [uv](https://github.com/astral-sh/uv)
- Dependencies: `httpx`, `lxml`, `cssselect`

## Output

- The scraped data is saved as `.json` files and committed to the repository.

## License

MIT License

---

**Maintainer:**  
sadaramsimhadri@gmail.com  
23f2002520@ds.study.iitm.ac.in