from tinydb import TinyDB, Query

db = TinyDB('db.json')

db.insert({dict})

db.all()  list all the records
or
for item in db:
    print(item)

To use Query

Fruit = Query()
db.search(Fruit.type == 'peaches')
db.search(Fruit.count > 5)

db.update({count: 10}, Fruit.type == 'apple')

db.remove(Fruit.count < 5)
db.truncate()       removes all the data in the db. 