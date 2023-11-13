#include <stdio.h>
#include <string.h>
#include <stdbool.h>

struct user
{
    char name[20];
    char password[20];
    bool isLoggedIn;
};

union Data
{
    struct user user;
};

int main()
{
    union Data d1;
    char c;
    
    printf("REGISTRATION \nenter your name and password are you loggedIn now ? y : n :\n");
    scanf("%s %s %c", d1.user.name, d1.user.password,&c);

    if(c == 'y') d1.user.isLoggedIn = true;
    else d1.user.isLoggedIn = false;

    char name[20];
    char password[20];

    printf("LOGIN  \nenter your name and password :\n");
    scanf("%s %s",name,password);
    
    if (strcmp(d1.user.name, name) == 0 && strcmp(d1.user.password , password) == 0)
        printf(d1.user.isLoggedIn == true ? "LOGIN SUCCESS AND YOU ARE LOGGED" : "LOGIN SUCCESS AND YOU ARE NOT LOGGED\n");
    else
        printf("LOGIN FAILED\n");


    return 0;
}

