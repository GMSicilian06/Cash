# Cash

#include <cs50.h>
#include <stdio.h>

int dividendo(int cash);

int diez(int restante);

int cinco(int restante_1);

int uno(int restante_2);

int total(int i, int k, int m, int s);

int main()
{
    int cash = get_int("cuánto será el cambio: ");

    int i = dividendo(cash);

    int restante = cash - 25 * i;

    int k = diez(restante);

    int restante_1 = restante - 10 * k;

    int m = cinco(restante_1);

    int restante_2 = restante_1 - 5 * m;

    int s = uno(restante_2);

    int t = total(i, k, m, s);

    printf("%d\n", t);

    return 0;
}

int dividendo(int cash)
{
    if (cash < 25)
    {
        return 0;
    }
    for (int i = 0; 25 * i <= cash; i++)
    {
        if (25 * (i + 1) > cash)
        {
            return i;
        }
    }
    return 0;

}






int diez(int restante)
{
    if (restante < 10)
    {
        return 0;
    }
    for (int k = 0; 10 * k <= restante; k++)
    {
        if (10 * (k + 1) > restante)
        {
            return k;
        }
    }
    return 0;
}

int cinco(int restante_1)
{
    if (restante_1 < 5)
    {
        return 0;
    }
    for (int m = 0; 5 * m <= restante_1; m++)
    {
        if (5 * (m + 1) > restante_1)
        {
            return m;
        }
    }
    return 0;
}

int uno(int restante_2)
{
    if (restante_2 < 1)
    {
        return 0;
    }
    else
    {
        return restante_2;
    }
    return 0;
}

int total(int i, int k, int m, int s)
{
    return i + k + m + s;
}
