## What websites:

Anything. Just write an URL from which the crawler will begin to extract info, and click on links ("a" anchors).

## What info:
- Email
- Phone numbers (from phone links or extracted from text)
- LinkedIn
- Twitter
- Instagram
- Facebook

## Why:
lead generation for your marketing and sales teams for instance

## Tutorial:
The Apify team did a [step-by-step guide](https://blog.apify.com/contact-information-scraper-7104cb0df25e/) to using Contact Details Scraper. Thanks to them.

## Input Configuration
- **Start URLs** - list of URLs where the crawler should start. 
You can enter multiple URLs, upload a text file with URLs, or even use a Google Sheets document. 
- **Maximum link depth** - how deep the actor will scrape links from the web pages specified in the Start URLs. If zero, the actor ignores the links and only crawls the Start URLs.
- **Stay within domain** - If enabled, the actor will only follow links on the same startUrl domain. For example, while crawling "http://www.example.com/some-page", if the crawler finds a link to http://www.another-domain.com/, it will not follow this link.
- **Pseudo URLs** - list of Regex the crawler will respect. Very useful when crawling a big website, to reduce the number of pages the crawler will follow.

## Results
The actor stores its results into the default dataset associated with the actor run. You can then download the results in formats such as JSON, HTML, CSV, XML, or Excel. For each page crawled, the following contact information is extracted (examples shown):

- **Emails**
  ```
  alice@example.com
  bob.newman@example.com
  carl+test@example.co.uk
  ```
- **Phone numbers** - These are extracted from phone links in HTML (e.g. `<a href='tel://123456789'>phone</a>`).
  ```
  123456789
  +123456789
  00123456789
  ```
- **Uncertain phone numbers** - These are extracted from the plain text of the web page using a number of regular expressions. Note that this approach can generate false positives.
  ```
  +123.456.7890
  123456789
  123-456-789
  ```
- **LinkedIn profiles**
  ```
  https://www.linkedin.com/in/alan-turing
  en.linkedin.com/in/alan-turing
  linkedin.com/in/alan-turing
  ```
- **Twitter profiles**
  ```
  https://www.twitter.com/apify
  twitter.com/apify
  ```
- **Instagram profiles**
  ```
  https://www.instagram.com/old_prague
  www.instagram.com/old_prague/
  instagr.am/old_prague
  ```
- **Facebook profiles or pages**
  ```
  https://www.facebook.com/apifytech
  facebook.com/apifytech
  fb.com/apifytech
  https://www.facebook.com/profile.php?id=123456789
  ```

## Personal data
You should be aware that your results might contain personal data. Personal data is protected by GDPR in the European Union and by other regulations around the world. You should not scrape personal data unless you have a legitimate reason to do so. If you're unsure whether your reason is legitimate, consult your lawyers. You can also read Apify blog post on the [legality of web scraping](https://blog.apify.com/is-web-scraping-legal/).

## Notes
Thanks to Apify who created the original crawler
