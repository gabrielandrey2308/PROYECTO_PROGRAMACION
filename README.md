#include <stdio.h> 
#include <wchar.h>                                                              //*Lib xra caracteres especiales
#include <locale.h>
#include <stdlib.h>
#include <string.h>                                                             //*Lib xra cadenas
#include <conio.h>                                                              //*Lib xra getch


#define TRUE 1
#define FALSE 0

int main () 
{
    int key, opts1, plant_type, weight;                                         //* Variables principales
    int weight1, weight2;                                                       //* Variables secundarias
    int start_times = 0;                                                        //* Cantidad de veces de uso/encendido
    char rpt = TRUE;                                                            //* Para la repetición del switch1
    int canplant; 
    printf ("\n\t\t\t\tHOLA :3\n\t BIENVENIDO AL ASISTENTE DE OPERACIONES DE TU INVERNADERO\n");  //* \t = press tab ->
    key = getch();                                                              //*pausa
    printf ("\n Selecciona una de las siguientes opciones introduciendo su número:\n ");
    printf ("\n\t1. Agregar una planta.\n\t2. Agregar material orgánico.");
    printf ("\n\t3. Iniciar asistente.\n\t0. Cancelar y apagar.\n\t");
    scanf("%d", &opts1);
    printf("\n _____________________________________________________________________________\n\n");
   // system (cls);


    do 
    {
        switch (opts1)                                                          //* Switch1
        {   
        
        case 0:
            if (opts1 == 0) {
                printf ("\n                           ______________________                            ");
                printf ("\n                          |                      |                           ");
                printf ("\n - - - - - - - - - - - - -  A P A G A N D O . . .  - - - - - - - - - - - - - ");
                printf ("\n                          |______________________|                     \n\n\n");
                key = getch();                                                  //*pausa
                rpt = FALSE;
            }else{
                printf ("\n                           ______________________                            ");
                printf ("\n                          |                      |                           ");
                printf ("\n - - - - - - - - - - - - -  A P A G A N D O . . .  - - - - - - - - - - - - - ");
                printf ("\n                          |______________________|                     \n\n\n");
                key = getch();                                                  //*pausa
                rpt = FALSE;
            }
        break;
        
        case 1:
            printf(" Ahora puede elegir el tipo de planta que va a agregar en su invernadero:");
            printf("\n\t1. Herbacea.\n\t2. Legumbre.\n\t3. Hortaliza.\n\t");
            scanf("%d", &plant_type);
            printf("\n Capacidad máxima de plantas en el invernadero: 30\n Introdusca la cantidad de plantas a cultivar: ");
            scanf("%d", &canplant);
            key = getch();                                                      //*pausa
            system("pause");
            rpt = FALSE;
        break;
    
        case 2:
            printf("¿Cual es el peso actual del contenedor?\n");
            scanf("%d", &weight1);
            printf("Ahora puedes depositar los residuos\n");
            scanf("%d", &weight2);
            weight = weight1 + weight2;
            key = getch();                                                      //*pausa
            rpt = FALSE;
        break;
        
        case 3:
            printf("\n\n\t\t\tIniciando el asistente virtual...\n");
            key = getch();                                                      //*pausa
            rpt = FALSE;
        break;
        }
    }
    while (rpt);                                                                //*se repite hasta cierto punto

    printf("\n _____________________________________________________________________________\n");
    printf("\n ---------------------ESTAS SON LAS ESTADISTICAS ACTUALES---------------------");
    printf("\n _____________________________________________________________________________\n");
    printf("\n Tipo de planta: ");
    if (plant_type == 1) {  printf("Herbacea");   }
    if (plant_type == 2) {  printf("Legumbre");   }
    if (plant_type == 3) {  printf("Hortaliza");  }
    printf("\n Porcentaje de uso del invernadero: %d", canplant*100/30);
    printf("\n Cantidad de materia orgánica: %d", weight);

    //* Continuar agregando las variables estadísticas según el tipo de planta
    //* Falta la acción de repetir el menú 1 si falta un dato

return 0;
}

/*FALTA CREAR UNA VARIABLE POR CADA QUE VALORE SI EL DATO ES 1 O 0 PARA 
ASÍ PODER PONER UN CONDICIONAL QUE PIDA EL DATO SI EL VALOR ES 0 Y QUE 
LO OMITA SI EL VALOR ES 1*/

/*ES NECESARIO ASIGNAR UN CONJUNTO DE VARIABES SEGÚN EL TIPO DE PLANTA
SELECCIONADO PARA QUE SE COPIEN EN UNAS VARIABLES ÚNICAS DEFINIDAS PARA 
LA FRECUENCIA DE APLICACIÓN DE AGUA, NUTRIENTES Y LUZ*/
