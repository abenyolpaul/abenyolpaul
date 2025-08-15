## Hi there 👋
.

🦸 Assignment 1: Design Your Own Class – Superhero Edition
# Base class
class Superhero:
    def __init__(self, name, power, origin):
        self.name = name
        self.power = power
        self.origin = origin

    def introduce(self):
        print(f"I am {self.name} from {self.origin}, and my power is {self.power}!")

    def use_power(self):
        print(f"{self.name} uses {self.power}!")

# Subclass with inheritance and polymorphism
class FlyingHero(Superhero):
    def __init__(self, name, power, origin, flight_speed):
        super().__init__(name, power, origin)
        self.flight_speed = flight_speed

    def use_power(self):
        print(f"{self.name} soars through the sky at {self.flight_speed} km/h using {self.power}!")

# Another subclass
class TechHero(Superhero):
    def __init__(self, name, power, origin, gadgets):
        super().__init__(name, power, origin)
        self.gadgets = gadgets

    def use_power(self):
        print(f"{self.name} deploys {', '.join(self.gadgets)} to execute {self.power}!")

# Example usage
hero1 = FlyingHero("Skybolt", "Wind Blast", "Cloud City", 800)
hero2 = TechHero("Circuit", "Cyber Hack", "Neo-Tokyo", ["Drone", "EMP Blaster"])

hero1.introduce()
hero1.use_power()

hero2.introduce()
hero2.use_power()

🎭 Activity 2: Polymorphism Challenge – Vehicles in Motion
# Base class
class Vehicle:
    def move(self):
        raise NotImplementedError("Subclasses must implement this method.")

# Subclasses with polymorphic behavior
class Car(Vehicle):
    def move(self):
        print("🚗 Driving on the road.")

class Plane(Vehicle):
    def move(self):
        print("✈️ Flying through the clouds.")

class Boat(Vehicle):
    def move(self):
        print("🛥️ Sailing across the sea.")

class Bicycle(Vehicle):
    def move(self):
        print("🚴 Pedaling down the trail.")

# Function to demonstrate polymorphism
def travel(vehicle: Vehicle):
    vehicle.move()

# Example usage
vehicles = [Car(), Plane(), Boat(), Bicycle()]
for v in vehicles:
    travel(v)






