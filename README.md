# student-management-system-
a list of dictionaries to store student data.
# Simple Student Management System

# List to store student data
students = []

# Function to add a student
def add_student():
    student_id = input("Enter Student ID: ")
    name = input("Enter Name: ")
    age = input("Enter Age: ")
    course = input("Enter Course: ")
    
    # Create a dictionary for the student
    student = {
        "ID": student_id,
        "Name": name,
        "Age": age,
        "Course": course
    }
    
    students.append(student)
    print(f"\nStudent {name} added successfully!\n")

# Function to view all students
def view_students():
    if not students:
        print("\nNo students found.\n")
        return
    print("\n--- Student List ---")
    for student in students:
        print(f"ID: {student['ID']}, Name: {student['Name']}, Age: {student['Age']}, Course: {student['Course']}")
    print()

# Function to search for a student by ID
def search_student():
    search_id = input("Enter Student ID to search: ")
    for student in students:
        if student["ID"] == search_id:
            print(f"\nFound Student: ID: {student['ID']}, Name: {student['Name']}, Age: {student['Age']}, Course: {student['Course']}\n")
            return
    print("\nStudent not found!\n")

# Function to delete a student by ID
def delete_student():
    delete_id = input("Enter Student ID to delete: ")
    for student in students:
        if student["ID"] == delete_id:
            students.remove(student)
            print(f"\nStudent ID {delete_id} deleted successfully!\n")
            return
    print("\nStudent not found!\n")

# Main menu
def main():
    while True:
        print("=== Student Management System ===")
        print("1. Add Student")
        print("2. View Students")
        print("3. Search Student")
        print("4. Delete Student")
        print("5. Exit")
        
        choice = input("Enter your choice (1-5): ")
        
        if choice == '1':
            add_student()
        elif choice == '2':
            view_students()
        elif choice == '3':
            search_student()
        elif choice == '4':
            delete_student()
        elif choice == '5':
            print("Exiting Student Management System. Goodbye!")
            break
        else:
            print("\nInvalid choice! Please try again.\n")

# Run the program
main()
