#include <stdio.h>
#include <stdlib.h>


double valorAbsoluto(double numero)
{
    if (numero < 0)
    {
        return numero * -1;
    }
    return numero;
}

double raizCuadrada(int numero)
{
    double margen = 0.000001;
    double estimacion = 2.0;
    while (valorAbsoluto((estimacion * estimacion) - numero) >= margen)
    {
        double cociente = numero / estimacion;
        double promedio = (cociente + estimacion) / 2.0;
        printf("Estimación: %lf. Cociente: %lf. Promedio: %lf\n", estimacion, cociente, promedio);
        estimacion = promedio;
    }
    return estimacion;
}

int main(int argc, char const *argv[])
{
    int numero;

    printf("Ingresa un número: ");
    scanf("%d", &numero);
    double raiz = raizCuadrada(numero);
    printf("La raíz cuadrada de %d es %lf", numero, raiz);
    return 0;
}
