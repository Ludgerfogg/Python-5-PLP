# Python-5-PLP
python- week 5 assignment


# Base class
class Superhero:
    def __init__(self, name, alias, power_level, city):
        self.name = name  # Public attribute
        self.alias = alias  # Public attribute
        self._power_level = power_level  # Protected attribute
        self.__city = city  # Private attribute

    def introduce(self):
        return f"I am {self.alias}, protector of {self.__city}!"

    def use_power(self, power_name):
        return f"{self.alias} uses {power_name}! It's super effective!"

    def get_city(self):
        return self.__city

    def set_city(self, new_city):
        self.__city = new_city


# Subclass with polymorphism
class TechHero(Superhero):
    def __init__(self, name, alias, power_level, city, gadgets):
        super().__init__(name, alias, power_level, city)
        self.gadgets = gadgets  # Specific attribute for TechHero

    def use_power(self, power_name):
        return f"{self.alias} activates {power_name} using cutting-edge technology!"

    def show_gadgets(self):
        return f"{self.alias} has these gadgets: {', '.join(self.gadgets)}"


# Another Subclass
class MysticHero(Superhero):
    def __init__(self, name, alias, power_level, city, spells):
        super().__init__(name, alias, power_level, city)
        self.spells = spells  # Specific attribute for MysticHero

    def use_power(self, power_name):
        return f"{self.alias} casts {power_name}! The mystical energy surges!"

    def show_spells(self):
        return f"{self.alias} knows these spells: {', '.join(self.spells)}"


# Create objects
tech_hero = TechHero("Tony Stark", "Iron Tech", 95, "Metropolis", ["Arc Reactor", "Nano Suit"])
mystic_hero = MysticHero("Stephen Strange", "Sorcerer Supreme", 90, "Kamar-Taj", ["Time Manipulation", "Portal Creation"])

# Use the objects
print(tech_hero.introduce())
print(tech_hero.use_power("Nano Suit Defense Mode"))
print(tech_hero.show_gadgets())

print(mystic_hero.introduce())
print(mystic_hero.use_power("Portal Creation"))
print(mystic_hero.show_spells())

# Access encapsulated data
print(tech_hero.get_city())
tech_hero.set_city("New Tech City")
print(tech_hero.get_city())


Activity 2: Polymorphism Challenge! 


# Base class
class Vehicle:
    def __init__(self, name):
        self.name = name

    def move(self):
        raise NotImplementedError("Subclasses must implement this method.")

# Derived class for Car
class Car(Vehicle):
    def move(self):
        return f"{self.name} is driving on the road."

# Derived class for Plane
class Plane(Vehicle):
    def move(self):
        return f"{self.name} is flying in the sky."

# Derived class for Boat
class Boat(Vehicle):
    def move(self):
        return f"{self.name} is sailing on the water."

# Derived class for Train
class Train(Vehicle):
    def move(self):
        return f"{self.name} is running on the tracks."

# List of vehicles
vehicles = [
    Car("Sedan"),
    Plane("Jet"),
    Boat("Yacht"),
    Train("Express"),
]

# Demonstrate polymorphism
for vehicle in vehicles:
    print(vehicle.move())

Sedan is driving on the road.
Jet is flying in the sky.
Yacht is sailing on the water.
Express is running on the tracks.
