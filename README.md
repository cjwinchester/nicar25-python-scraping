# NICAR 2025: Web scraping with Python

### 🔗 [bit.ly/nicar25-python-scraping](https://bit.ly/nicar25-python-scraping)

This repo contains materials for a twoish-hour workshop at the NICAR 2025 conference in Minneapolis on using Python to scrape data from websites.

The session is scheduled for Friday, March 7, from 2:15 – 4:30 p.m. in room `Deer Lake` on the fourth floor.

### First step

Open the `cmd` application. Copy and paste this text and hit enter:

```
cd Desktop\hands_on_classes\20250307-friday-web-scraping-with-python-pre-registered-attendees-only && .\env\Scripts\activate
```

### Course outline
- Do you really need to scrape this?
- Process overview:
    - Fetch, parse, write data to file
    - Some best practices
        - Make sure you feel OK about whether your scraping project is (legally, ethically, etc.) allowable
        - Don't DDOS your target server
        - When feasible, save copies of pages locally, then scrape from those files
        - [Rotate user-agent strings](https://www.useragents.me/) and other headers if necessary to avoid bot detection
- Using your favorite brower's inspection tools to deconstruct the target page(s)
    - See if the data is delivered via undocumented API to the page in a ready-to-use format, such as JSON ([example 1](https://sdlegislature.gov/Session/Archived), [example 2](https://www.britishmuseum.org/collection)) -- [Postman](https://www.postman.com) or similar software is handy for testing out API calls
    - Is the HTML part of the actual page structure, or is it built on the fly when the page loads? ([example](https://rrctx.force.com/s/complaints))
    - Can you open the URL directly in an incognito window and get to the same content, or does the page require a specific state to deliver the content (via search navigation, etc.)? ([example](https://rrctx.force.com/s/ietrs-complaint/a0ct0000000mOmhAAE/complaint0000000008))
    - Are there [URL query parameters](https://en.wikipedia.org/wiki/Query_string) that you can tweak to get different results? ([example](https://www.worksafe.qld.gov.au/news-and-events/alerts))
- Choose tools that the most sense for your target page(s) -- a few popular options:
    - [`requests`](https://requests.readthedocs.io/en/latest/) and [`BeautifulSoup`](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)
    - [`playwright`](https://playwright.dev/python) (optionally using `BeautifulSoup` for the HTML parsing)
    - [`scrapy`](https://scrapy.org/) for larger spidering/crawling tasks
- Overview of our Python setup today
    - Activating the virtual environment
    - Jupyter notebooks
    - Running `.py` files from the command line
- Projects in this repo:
    - [South Dakota WARN notices](sd-warn)
    - [U.S. Senate press gallery](us-senate-press-gallery)
    - [Queensland workplace incidents](qld-incidents)
    - [Texas custodial death reports](tx-custodial-death-reports)

### Other resources
- [Try GitHub Actions](https://palewi.re/docs/first-github-scraper) if you need to put your scraper on a timer (you could also drop your script on a remote server, such as DigitalOcean, PythonAnywhere or Heroku, with a [`crontab` configuration](https://en.wikipedia.org/wiki/Cron)
- [Tipsheet on inspecting web elements](https://docs.google.com/document/d/12e_9VfNxME02qfSRZU_diF8Qqp6EEvnR-xtudI58GeI/edit)
- [Tipsheet on saving HTML files before scraping them](https://docs.google.com/document/d/1SMpxt2b1ClEjLBZU2cg0Y2-yqxG_UoNq5f59h_5M4P8/edit)
- [Tipsheet with some miscellaneous scraping tips](https://docs.google.com/document/d/1-D1GhYJuOus7tXomPPYACaaer6He41cdcl_7J3rsqIk/edit)

### Using Google CoLab or Binder
You can run these notebooks by plugging this GitHub repository's URL into [Google CoLab](https://colab.research.google.com/) or [Binder](https://notebooks.gesis.org/binder/), both easy-to-use, cloud-based Python notebook environments.

### Running this code at home
- Install Python, if you haven't already ([here's our guide](https://docs.google.com/document/d/1cYmpfZEZ8r-09Q6Go917cKVcQk_d0P61gm0q8DAdIdg/edit))
- Clone or download this repo
- `cd` into the repo directory and install the requirements, preferably into a virtual environment using your tooling of choice: `pip install -r requirements.txt`
- `playwright install`
- `jupyter lab` to launch the notebook server
