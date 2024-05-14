---
title: Using the official exchange rate in Venezuela's e-commerce
description: Latin America and Venezuela in particular, presents unique challenges for e-commerce, including local laws and  tax regulations required to engage with the consumer base. A simple web scraper built in Python with FastAPI can be useful for a software developer who wants to access the exchange rate from the official website of Banco Central de Venezuela.  We will briefly explore when this is a good idea  to a how to do it. 
date: 2024-01-19
categories:
    - Web Scrapping 
---
Photo by [Frederick Medina](https://unsplash.com/@frederickjmedina?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash) on [Unsplash](https://unsplash.com/photos/person-holding-two-brown-doughnuts-LxyT2CgQSj8?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash)


## Situation

Venezuela's e-commerce sector is expected to grow due to increasing Internet penetration, development of the legal framework, and improved capabilities of banks to provide secure transactions [^1]. After the pandemic business boomed, it's required by law to have a bill in the national currency (Bs.) but most products and transactions are advertised in USD. let's see two examples:

**Librería La Alegría** is a bookstore and stationery store that offers over 15,000 products related to office supplies, school items, art supplies, technical and school books, games, and more. The store also provides a cultural center for the city with workshops for children and events[^2].

It's tech stack is an Odoo instance. There's no mobile app. The billing is done directly in a store.  A [quick search](https://apps.odoo.com/apps/modules/browse?search=BCV) indicates that there are 3 extension and on of them is free. But it might not be open source, I couldn't find the repo.

**Tu Zona Market** is an online marketplace that connects local vendors with customers. The platform offers a range of products, including groceries, electronics, and home appliances, and provides customers with a seamless shopping experience in two states [^3].

Uses Angular what looks like express backend, I can't really be sure. So they needed two things for getting the:

1. A web scraper: a program that extracts data from a website by parsing its HTML code.
2. RESTful APIs with minimal code and high performance.
3. Database Storage for historical data (for returns, refunds and the like).

If you use a service like [Exchange Rate API](https://www.exchangerate-api.com/) you can get the daily exchange rate, but you could get rate limited quickly. 

## Solution
### If you got hardware
Creating a web scraper and using it with [crawlab](https://www.crawlab.cn/en) as storage in MongoDB is a great solution.

### If you don't
A simple web scraper built in Python with FastAPI can be useful for a software developer who wants to access and analyze the financial data from the official website of Banco Central de Venezuela.

By using a web scraper built in Python with FastAPI, you can:

- Automate the process of fetching the latest exchange rates, from the website of Banco Central de Venezuela.
- Convert the scraped data into JSON format, which can be stored, transmitted, and processed by various applications and tools.
- Create a custom API that exposes the scraped data as endpoints, which can be accessed by other developers or users who need the data for their own purposes.
- Apply data analysis, visualization, or machine learning techniques to the scraped data, using the rich set of libraries and packages available in Python.

I made a base public in ths repo. Let me know if you have any questions.



[^1]: E-commerce in Venezuela. <https://www.lloydsbanktrade.com/en/market-potential/venezuela/ecommerce>.
[^2]: Librería La Alegría. <https://www.librerialaalegria.com.ve/>.
[^3]: Tu Zona Market. <https://tuzonamarket.com/>.

