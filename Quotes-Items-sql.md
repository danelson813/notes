 [[Quotes-pipeline-sql]]. [[Quotes-spider-sql]]
import scrapy  
  
  
class QuotesItem(scrapy.Item):  
    define the fields for your item here like:  
	name = scrapy.Field() title = scrapy.Field()  
	author = scrapy.Field()  
	tag = scrapy.Field()