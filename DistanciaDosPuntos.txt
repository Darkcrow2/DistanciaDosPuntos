#include <iostream>
#include <stdio.h>
#include <string.h>
#include <math.h>

int main()
{
	/*
	float x1, x2, y1, y2, distancia;
	printf("Agregue la primera coordenada: \n");
	scanf("%f %f", &x1, &y1);

	printf("Agregue la segunda coordenada: \n");
	scanf("%f %f", &x2, &y2);

	distancia = sqrt(pow((x2 - x1), 2) + pow((y2 - y1), 2));

	printf("La distancia entre los dos puntos es: %f\n", distancia);
	*/

	
	char string1[255], string2[255], punto1[2], punto2[2];	//Inicializo las variables
	float distancia;
	printf("Agregue la primera coordenada (X1, Y1): \n");	//Pido al usuario que ingrese las coordenadas
	fgets( string1, sizeof(string1), stdin);	//Obtendo el string ingresado

	char *p = string1;
	int numeros = 0;
	while (*p) {	//Hacer hasta que el último caracter sea leido
		if (isdigit(*p) && numeros < 2) {
			float k = strtod(p, &p);
			punto1[numeros] = k;
			numeros++;
		}
		else {
			p++;
		}
	}

	printf("Agregue la segunda coordenada (X1, Y1): \n");
	fgets(string2, sizeof(string2), stdin);

	char *q = string2;
	numeros = 0;
	while (*q) {	//Hacer hasta que el último caracter sea leido
		if (isdigit(*q) && numeros < 2) {
			float k = strtod(q, &q);
			punto2[numeros] = k;
			numeros++;
		}
		else {
			q++;
		}
	}

	distancia = sqrt(pow((punto1[0] - punto2[0]), 2) + pow((punto1[1] - punto2[1]), 2));

	printf("La distancia entre dos puntos es: %f\n", distancia);

	return 0;
}
