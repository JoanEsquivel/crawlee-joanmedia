
# Crawlee for Python - JoanMedia Guideline

This project is based on the documentation provided in the [official repository](https://github.com/apify/crawlee-python) & [official documentation](https://crawlee.dev/python/docs/quick-start)

## Requirements

### Must Have
- [Python](https://www.python.org/downloads/)
- [PIP](https://pypi.org/project/pip/)

### Optional
- [pipx](https://github.com/pypa/pipx): Install and Run Python Applications in Isolated Environments
- [poetry](https://python-poetry.org/docs/): Poetry is a tool for dependency management and packaging in Python. It allows you to declare the libraries your project depends on and it will manage (install/update) them for you. Poetry offers a lockfile to ensure repeatable installs, and can build your project for distribution.

## Template installation
- CLI Helper: 
``` 
pipx run crawlee create [project-name]

```
- You'll be asked to choose your favorite crawler:
```
[?] Please select the template for your new Crawlee project:
   Beautifulsoup
 > Playwright
```
- You'll receive a confirmation message saying your project is installed:
```
Your project [project-name] was created.
```
- Follow the next instructions to install project dependencies and run the template
```
To run it, navigate to the directory: "cd [project-name]"
Install dependencies with "poetry install"
And run it using "poetry run python -m [project-name]".
```
- If you choose the Playwright option before, please use the following command to download the browsers required by Playwright
```
playwright install
```
In case of emergency use: ``` python3 -m pip install --force-reinstall playwright ```

## Real example using the Playwright crawler


### The crawling strategy

* Visit the store page containing the list of categories (our start URL).
* Enqueue all links to all categories.
* Enqueue all product pages from the current page.
* Enqueue links to next pages of results.
* Open the next page in queue.
* When it's a results list page, go to 2.
* When it's a product page, scrape the data.
* Repeat until all results pages and all products have been processed.
* PlaywrightCrawler will make sure to visit the pages for you, if you provide the correct requests, and you already know how to enqueue pages, so this should be fairly easy. Nevertheless, there are few more tricks that we'd like to showcase.

Website for demo: ``` https://warehouse-theme-metal.myshopify.com/collections ```


