# OOP6

import requests

c_from = raw_input('What currency you want to convert from?')
c_from = c_from.upper()

c_to = raw_input('What currency you want to convert to?')
c_to = c_to.upper()

amount = float(raw_input('How much you want to convert?'))

url = ('http://rate-exchange.appspot.com/currency?from=%s&to=%s&q=1') % (c_from, c_to)
print url

r = requests.get(url)
print r.json()['v']

print amount*r.json()['v']
