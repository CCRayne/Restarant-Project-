# Restarant-Project-

class Business:
  def __init__(self, name, franchises):
    self.name = name
    self.franchises = franchises


class Franchise:
  def __init__(self, address, menus):
    self.address = address
    self.menus = menus 

  def __repr__(self):
    return self.address

  def available_menus(self, time):
    available_menus = []
    for menu in self.menus:
      if time >= menu.start_time and time <= menu.end_time:
        available_menus.append(menu)
    return available_menus

class Menu:
  def __init__(self, name, items, start_time, end_time):
    self.name = name
    self.items = items
    self.start_time =    start_time
    self.end_time = end_time

#__repr__ representation
  def __repr__(self):
    return self.name + ' menu available from ' + str(self.start_time) + ' - ' + str(self.end_time)

  def calculate_bill(self, purchased_items):
    bill = 0
    for purchased_item in purchased_items:
      if purchased_item in self.items:
        bill += self.items[purchased_item]
    return bill

#Brunch Menu
brunch_items = {
  'pancakes': 7.50, 'waffles': 9.00, 'burger': 11.00, 'sweet potato fries': 4.50, 'coffee': 1.50, 'latte': 3.00, 'tea': 1.00, 'mimosa': 10.50, 'orange juice': 3.50
}
brunch_menu = Menu('Brunch', brunch_items, 1100, 1600)

# Early bird menu
early_bird_items = {
  'salumeria': 8.00, 'salad and breadsticks (serves 2, no refills)': 14.00, 'pizza with sundried tomatoes': 9.00, 'mushroom ravioli (vegan)': 13.50, 'latte': 3.00, 'coffee': 1.50, 
}
early_bird_menu = Menu('Early Bird', early_bird_items, 1500, 1800)

#print(early_bird_menu.calculate_bill(['salumeria', 'mushroom ravioli (vegan)']))

#Dinner Menu
dinner_items = {
  'crostini with eggplant caponata': 13.00, 'caesar salad': 16.00, 'pizza with sundried tomatoes': 11.00, 'mushroom ravioli (vegan)': 13.50, 'date latte': 3.00, 'coffee': 2.00, 
}
dinner_menu = Menu('Dinner', dinner_items, 1700, 2300)

#Kids Menu
kids_items = {
  'chicken nuggets': 6.50, 'chicken wings': 12.00, 'apple juice': 3.00, 
}
kids_menu = Menu('Kids', kids_items, 1100, 2100)

menus = [brunch_menu, early_bird_menu, dinner_menu, kids_menu]

flagship = Franchise('9 Kirk Road', menus)
newest_location = Franchise('1554 Toronto Street', menus)

basta = Business("Rasta Pasta Grill", [flagship, newest_location])

#CPlace

cplace_items = {
  'eggplant': 7.00, 'squash': 8.50, 'green beans and quinoa': 8.00, 'rice and peas': 7.50
}
cplace_menu = Menu("Welcome Home", cplace_items, 1000, 2000)

cplace_restaurant = Franchise("27 Martin Avenue", [cplace_menu])

cplace = Business("Welcome Home", [cplace_restaurant)
print(cplace.franchises[0].menus[0])
