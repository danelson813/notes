[[Quotes-Items-sql]] [[Quotes-pipeline-sql]]
import scrapy  
from ..items import QuotesItem  
  
  
class QuoteSpider(scrapy.Spider):  
    name = 'quote'  
    allowed_domains = ['quotes.toscrape.com']  
    start_urls = ['https://quotes.toscrape.com']  
  
    def parse(self, response):  
        items = QuotesItem()  
  
        all_div_quotes = response.css('div.quote')  
  
        for quote in all_div_quotes:  
            title = quote.css('span.text::text').extract()  
            author = quote.css('.author::text').extract()  
            tag = quote.css('.tag::text').extract()  
  
            items['title'] = title  
            items['author'] = author  
            items['tag'] = tag  
  
            yield items