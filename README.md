# mojkozien#include <iostream>
#include <cstdlib>
#include <time.h>

using namespace std;

int main()
{
  const int N = 31; // liczba elementów
  int d[N + 1],i,j,k,x;

  srand((unsigned)time(NULL));

  cout << "   Tworzenie  kopca\n"
          "----------------------\n"
          "(C)2005 Jerzy Walaszek\n\n";

// Inicjujemy zbiór d[] liczbami pseudolosowymi od 0 do 9

  for(i = 1; i <= N; i++) d[i] = rand() % 10;

// Budujemy kopiec

  for(i = 2; i <= N; i++)
  {
    j = i; k = j / 2;
    x = d[i];
    while((k > 0) && (d[k] < x))
    {
      d[j] = d[k];
      j = k; k = j / 2;
    }
    d[j] = x;
  }

// Prezentujemy wyniki

  x = (N + 1) / 2; k = 2;
  for(i = 1; i <= N; i++)
  {
    for(j = 1; j <= x - 1; j++) cout << " ";
    cout << d[i];
    for(j = 1; j <= x; j++) cout << " ";
    if(i + 1 == k)
    {
      k += k; x /= 2; cout << endl;
    }
  }

// Gotowe

  cout << endl << endl;
  return 0;
} 
