# Contract Management system

This project  just for mobile.

## Features

1. Create New Contact
2. View All Contact
3. Search Contact
4. Delete Contact
5. Edit

### Built

I completed this project on Java language.

### Using software: 
Netbeans

### Operating System: 
Windows 10 pro


### CODE SAMPLE

     {
        System.out.println(String.format("%5s%3s%s", "1.", " ", "Create New Contact"));
        System.out.println(String.format("%5s%3s%s", "2.", " ", "View All Contact"));
        System.out.println(String.format("%5s%3s%s", "3.", " ", "Search Contact"));
        System.out.println(String.format("%5s%3s%s", "4.", " ", "Delete Contact"));
        System.out.println(String.format("%5s%3s%s", "5.", " ", "Exit"));
        System.out.println("---------------------------");
        System.out.print(" Enter Your Choice : ");
        }

## Running the tests

Now this porject will be run just Java based software  like Netbeans and eclipse

### METHOD

/ Get Input From User and Create a new Contact
    private static Contact createNewContact(Scanner scanner) {
        String name, email, phone;
        Contact contact;

        scanner.nextLine();

        System.out.println("Fill The Below Form Correctly");

        System.out.print("Enter Name* : ");
        name = scanner.nextLine();

        System.out.print("Enter Phone No* : ");
        phone = scanner.nextLine();

        System.out.print("Enter Email (Type N if Not Available) : ");
        email = scanner.nextLine();

        if (email.equalsIgnoreCase("n")) {
            contact = new Contact(name, phone);
        } else {
            contact = new Contact(name, phone, email);
        }

        return contact;
    }

    // Show All Contact method
    private static void showAllContacts(ArrayList<Contact> contacts) {
        System.out.println("All Contacts....");
        System.out.println("----------------------------");

        int i = 0;
        for (Contact contact : contacts) {
            String email = contact.getEmail();
            System.out.println(String.format("%-5d%-20s%-15s%-50s", i++, contact.getName(), contact.getPhoneNo(), email == null ? "N/A": email));
        }
        System.out.println("----------------------------");
    }

    // Search List Method
    private static void searchList(ContactList contactList, Scanner scanner) {
        scanner.nextLine();

        System.out.print("Enter Name to Search: ");
        String name = scanner.nextLine();

        Contact contact = contactList.searchContact(name);

        if (contact != null) {
            String email = contact.getEmail();
            System.out.println(String.format("%-20s%-15s%-50s", contact.getName(), contact.getPhoneNo(), email == null ? "N/A": email));
        } else {
            System.out.println("Contacts Not Found...");
        }
    }

    // Delete Contact Method
    private static void deleteContact(ContactList contactList, Scanner scanner) {
        showAllContacts(contactList.getContacts());
        System.out.print("Enter Index No: ");
        int index = scanner.nextInt();

        contactList.removeContact(index);
        System.out.println("Successfully Removed...");
    }
}

### DEDICATION

* **Mst. Farzana Sadia**
* **(senior lecturer)**
* **Daffodil International University**

 

## Authors

* **Md: Rabbi Islam** 
* **STUDENT (SOFTWARE ENGINEERING Dept**
* **Daffodil international university**



