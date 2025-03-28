#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define DISK_FILE "virtual_disk.img"
#define BLOCK_SIZE 256
#define MAX_BLOCKS 4096
#define MAX_FILES 128

typedef struct {
    char name[20];
    int start_block;
    int size;
    int allocation_type; // 0=contiguous, 1=linked, 2=indexed
} FileEntry;

typedef struct {
    FileEntry files[MAX_FILES];
    int file_count;
} FileSystem;

FileSystem fs;

// Initialize File System
void init_fs() {
    FILE *disk = fopen(DISK_FILE, "rb+");
    if (!disk) {
        printf("Error: Virtual disk not found.\n");
        return;
    }
    fs.file_count = 0;
    fclose(disk);
}

// Create a new file
void create_file(const char *filename, int size, int allocation_type) {
    if (fs.file_count >= MAX_FILES) {
        printf("Error: File limit reached.\n");
        return;
    }

    strcpy(fs.files[fs.file_count].name, filename);
    fs.files[fs.file_count].size = size;
    fs.files[fs.file_count].allocation_type = allocation_type;
    
    fs.files[fs.file_count].start_block = rand() % MAX_BLOCKS; // Simple allocation logic
    fs.file_count++;
    
    printf("File '%s' created using %s allocation.\n", filename,
        (allocation_type == 0) ? "Contiguous" : (allocation_type == 1) ? "Linked" : "Indexed");
}

// List all files
void list_files() {
    printf("\nStored Files:\n");
    for (int i = 0; i < fs.file_count; i++) {
        printf("Name: %s, Start Block: %d, Size: %d KB, Type: %s\n",
            fs.files[i].name, fs.files[i].start_block, fs.files[i].size,
            (fs.files[i].allocation_type == 0) ? "Contiguous" : (fs.files[i].allocation_type == 1) ? "Linked" : "Indexed");
    }
}

// Delete a file
void delete_file(const char *filename) {
    int found = 0;
    for (int i = 0; i < fs.file_count; i++) {
        if (strcmp(fs.files[i].name, filename) == 0) {
            found = 1;
            for (int j = i; j < fs.file_count - 1; j++) {
                fs.files[j] = fs.files[j + 1];
            }
            fs.file_count--;
            printf("File '%s' deleted successfully.\n", filename);
            return;
        }
    }
    if (!found) {
        printf("Error: File not found.\n");
    }
}

// File System Menu
void file_system_menu() {
    int choice;
    char filename[20];
    int size, type;
    
    while (1) {
        printf("\n1. Create File\n2. List Files\n3. Delete File\n4. Exit\nChoose an option: ");
        scanf("%d", &choice);
        
        switch (choice) {
            case 1:
                printf("Enter filename: ");
                scanf("%s", filename);
                printf("Enter size (in KB): ");
                scanf("%d", &size);
                printf("Enter allocation type (0=Contiguous, 1=Linked, 2=Indexed): ");
                scanf("%d", &type);
                create_file(filename, size, type);
                break;
            case 2:
                list_files();
                break;
            case 3:
                printf("Enter filename to delete: ");
                scanf("%s", filename);
                delete_file(filename);
                break;
            case 4:
                return;
            default:
                printf("Invalid option. Try again.\n");
        }
    }
}

int main() {
    init_fs();
    file_system_menu();
    return 0;
}
