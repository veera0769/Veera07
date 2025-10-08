class Animal:
 def __init__(self, name, sound):
 self.name = name
 self.sound = sound
 def make_sound(self):
 print(f"{self.name} says {self.sound}")
class Dog(Animal):
 def __init__(self, name, sound, breed):
 super().__init__(name, sound)
 self.breed = breed
class Cat(Animal):
 def __init__(self, name, sound, favorite_food):
 super().__init__(name, sound)
 self.favorite_food = favorite_food
dog = Dog("Buddy", "Woof", "Golden Retriever")
cat = Cat("Whiskers", "Meow", "Tuna")
print(dog.name, dog.breed)
dog.make_sound()
print(cat.name, cat.favorite_food)
cat.make_sound()
