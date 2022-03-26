[[Quotes-Items-sql]] [[Quotes-spider-sql]]
import sqlite3  
  
  
class QuotesPipeline(object):  
  
    def __init__(self):  
        self.create_connection()  
        self.create_table()  
  
    def create_connection(self):  
        self.conn = sqlite3.connect("myquotes.db")  
        self.curr = self.conn.cursor()  
  
    def create_table(self):  
        self.curr.execute("""  
 DROP TABLE IF EXISTS quote_tb """)  
        self.curr.execute("""  
 CREATE TABLE quotes_tb( title text, author text, tag text )""")  
  
    def store_db(self, item):  
        self.curr.execute("""  
 INSERT INTO quotes_tb Values(?,?,?) """, (  
            item['title'][0],  
            item['author'][0],  
            item['tag'][0]  
        ))  
        self.conn.commit()  
  
    def process_item(self, item, spider):  
        self.store_db(item)  
        return item