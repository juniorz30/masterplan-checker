# masterplan-checker
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    int nummer;
    int herinneren[3] = {0, 0, 0}; // Voor de 3 mogelijkheden: positief, negatief, en 0

    while (true) // Blijf vragen tot de gebruiker -999 invoert anders stopt die en gaat die naar die samenvatting
    {
        nummer = get_int("Geef mij een nummer (bij -999 stopt het): ");

        if (nummer == -999)
        {
            break; // Stop de lus(gebruik break en geen return 1 anders stop de programma volledig!), daardoor kan je error hebben
        }
        else if (nummer > 0)
        {
            herinneren[0]++; // Tel een positief nummer
        }
        else if (nummer < 0)
        {
            herinneren[1]++; // Tel een negatief nummer
        }
        else
        {
            herinneren[2]++; // Tel de nullen
        }
    }

    // Print de samenvatting
    printf("Samenvatting:\n");
    printf("Positieve nummers: %i\n", herinneren[0]);
    printf("Negatieve nummers: %i\n", herinneren[1]);
    printf("Nullen: %i\n", herinneren[2]);

    return 0; // Programma succesvol beëindigen
}
