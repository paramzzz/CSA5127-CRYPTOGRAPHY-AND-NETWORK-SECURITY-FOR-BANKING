#include <stdio.h>
#include <string.h>
#define MAX 100
void encryptRailFence(char *text, int rails) {
    char rail[rails][MAX];
    int len = strlen(text);
    int i, j;

    for (i = 0; i < rails; i++)
        for (j = 0; j < len; j++)
            rail[i][j] = '\n';

    int dir_down = 0;
    int row = 0;

    for (i = 0; i < len; i++) {
        rail[row][i] = text[i];

        if (row == 0 || row == rails - 1)
            dir_down = !dir_down;

        row += dir_down ? 1 : -1;
    }

 
    printf("Encrypted Text: ");
    for (i = 0; i < rails; i++)
        for (j = 0; j < len; j++)
            if (rail[i][j] != '\n')
                printf("%c", rail[i][j]);
    printf("\n");
}


void decryptRailFence(char *cipher, int rails) {
    char rail[rails][MAX];
    int len = strlen(cipher);
    int i, j;

 
    for (i = 0; i < rails; i++)
        for (j = 0; j < len; j++)
            rail[i][j] = '\n';

    int dir_down, row = 0;
    dir_down = 0;

    for (i = 0; i < len; i++) {
        rail[row][i] = '*';

        if (row == 0 || row == rails - 1)
            dir_down = !dir_down;

        row += dir_down ? 1 : -1;
    }

    int index = 0;
    for (i = 0; i < rails; i++)
        for (j = 0; j < len; j++)
            if (rail[i][j] == '*' && index < len)
                rail[i][j] = cipher[index++];

    row = 0;
    dir_down = 0;
    printf("Decrypted Text: ");
    for (i = 0; i < len; i++) {
        printf("%c", rail[row][i]);

        if (row == 0 || row == rails - 1)
            dir_down = !dir_down;

        row += dir_down ? 1 : -1;
    }
    printf("\n");
}


int main() {
    char text[MAX], choice;
    int rails;

    printf("Enter number of rails: ");
    scanf("%d", &rails);
    getchar(); 

    printf("Encrypt or Decrypt? (E/D): ");
    scanf("%c", &choice);
    getchar();

    if (choice == 'E' || choice == 'e') {
        printf("Enter plaintext: ");
        fgets(text, MAX, stdin);
        text[strcspn(text, "\n")] = '\0'; 
        encryptRailFence(text, rails);
    } else if (choice == 'D' || choice == 'd') {
        printf("Enter ciphertext: ");
        fgets(text, MAX, stdin);
        text[strcspn(text, "\n")] = '\0';
        decryptRailFence(text, rails);
    } else {
        printf("Invalid choice.\n");
    }

    return 0;
}
OUTPUT
Enter number of rails: 2
Encrypt or Decrypt? (E/D): E
Enter plaintext: welcome to my session
Encrypted Text: wloet yssinecm om eso
Decrypted Text :welcome to my session




