# Define the Student class
class Student:
    def __init__(self, name, roll_no):
        # Constructor: called when a new student object is created
        self.name = name
        self.roll_no = roll_no

    def display_info(self):
        # Method to print student details
        print(f"Name: {self.name}, Roll No: {self.roll_no}")


# Define the Classroom class
class Classroom:
    def __init__(self, class_name):
        # Constructor: initializes a classroom with its name
        self.class_name = class_name
        self.students = []   # empty list to store Student objects

    def add_student(self, student):
        # Adds a student to the classroom
        self.students.append(student)
        print(f"✅ Student {student.name} added to {self.class_name}")

    def show_students(self):
        # Displays all students in the classroom
        if not self.students:
            print("⚠️ No students in this classroom.")
        else:
            print(f"\n👩‍🎓 Students in {self.class_name}:")
            for student in self.students:
                student.display_info()


# ---------- MAIN PROGRAM ----------
# 1. Create a classroom
classroom1 = Classroom("Python Batch A")

# 2. Create student objects
s1 = Student("Alice", 101)
s2 = Student("Bob", 102)
s3 = Student("Charlie", 103)

# 3. Add students into the classroom
classroom1.add_student(s1)
classroom1.add_student(s2)
classroom1.add_student(s3)

# 4. Display all students
classroom1.show_students()
