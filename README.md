def display_menu():
    print("\nPhonebook Application")
    print("1. Add a contact")
    print("2. Remove a contact")
    print("3. Search for a contact")
    print("4. Display all contacts")
    print("5. Exit")

def add_contact(phonebook):
    name = input("Enter contact name: ")
    phone = input("Enter phone number: ")
    phonebook[name] = phone
    print(f"Contact {name} added successfully.")

def remove_contact(phonebook):
    name = input("Enter the name of the contact to remove: ")
    if name in phonebook:
        del phonebook[name]
        print(f"Contact {name} removed successfully.")
    else:
        print("Contact not found.")

def search_contact(phonebook):
    name = input("Enter the name to search for: ")
    if name in phonebook:
        print(f"{name}: {phonebook[name]}")
    else:
        print("Contact not found.")

def display_contacts(phonebook):
    if phonebook:
        print("\nPhonebook Contacts:")
        for name, phone in phonebook.items():
            print(f"{name}: {phone}")
    else:
        print("Phonebook is empty.")

def main():
    phonebook = {}
    while True:
        display_menu()
        choice = input("Enter your choice: ")

        if choice == '1':
            add_contact(phonebook)
        elif choice == '2':
            remove_contact(phonebook)
        elif choice == '3':
            search_contact(phonebook)
        elif choice == '4':
            display_contacts(phonebook)
        elif choice == '5':
            print("Exiting the phonebook application. Goodbye!")
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()
