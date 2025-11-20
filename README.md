# Telephone-Directory-in-C
#include <stdio.h>
#include <string.h>


struct PhoneDirectory {
    char phoneNumber[11];  // 10 digits + null terminator
    char location[50];
};




void searchLocation(struct PhoneDirectory directory[], int total, const char *searchNumber) {
    for (int i = 0; i < total; i++) {
        if (strcmp(directory[i].phoneNumber, searchNumber) == 0) {
            printf("Phone Number : %s\n", directory[i].phoneNumber);
            printf("Location/Area: %s\n", directory[i].location);
            return;
        }
    }
    printf("Phone number %s not found in the directory.\n", searchNumber);
}


int main() {
    int totalEntries = 5;  


    struct PhoneDirectory directory[5] = {
        {"1234567890", "New York"},
        {"9876543210", "Los Angeles"},
        {"5551234567", "Chicago"},
        {"1112223333", "San Francisco"},
        {"4445556666", "Mexico City"}
    };


    char searchNumber[11];


    printf("Enter phone number to search (10 digits, no dashes): ");
    scanf("%10s", searchNumber);


    searchLocation(directory, totalEntries, searchNumber);


    return 0;
}
