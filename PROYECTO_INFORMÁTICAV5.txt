#include <stdio.h> 
#include <wchar.h>                                                              //*Lib xra caracteres especiales
#include <locale.h>
#include <stdlib.h>
#include <string.h>                                                             //*Lib xra cadenas
#include <conio.h>                                                              //*Lib xra getch
#include <stdbool.h>

#define FILAS 11
#define COLUMNAS 3
#define LONGITUD_PALABRA 20
#define TRUE 1
#define FALSE 0
#define MAX_PLANTAS 33
#define MAX_LONGITUD 50

typedef struct {
    char nombre[MAX_LONGITUD];
    char cuidados[MAX_LONGITUD];
} Planta;

void inicializarPlantas(Planta plantas[]) {
    strcpy(plantas[0].nombre, "girasol");
    strcpy(plantas[0].cuidados, " riegos diarios, 25° C, abono en meses de crecimiento");

    strcpy(plantas[1].nombre, "cebolla");
    strcpy(plantas[1].cuidados, "riego moderado, 15 y 23° C para ir saludable");
    
    strcpy(plantas[2].nombre, "altramuz");
    strcpy(plantas[2].cuidados, "tenerla tanto a pleno sol como en semisombra, 10 a 13° C.");
    
    strcpy(plantas[3].nombre, "espinaca");
    strcpy(plantas[3].cuidados, "riego frecuente, 14 horas de luz de sol");
    
    strcpy(plantas[4].nombre, "milenrama");
    strcpy(plantas[4].cuidados, "riego neutro, pleno sol completo");
    
    strcpy(plantas[5].nombre, "patata");
    strcpy(plantas[5].cuidados, "poco frecuente, fresca");
    
    strcpy(plantas[6].nombre, "la angélica");
    strcpy(plantas[6].cuidados, "riego diario o cada dos días, 15° C.");
    
    strcpy(plantas[7].nombre, "bambú");
    strcpy(plantas[7].cuidados, "riego solo en los primeros días de siembra., desde -15° C hasta más de 20° C.");
    
    strcpy(plantas[8].nombre, "alhelí");
    strcpy(plantas[8].cuidados, "riego regular pero poco frecuente, 5 y 25° C.");
    
    strcpy(plantas[9].nombre, "amapola");
    strcpy(plantas[9].cuidados, "riego moderado, entre los 18 y los 33° C.");
    
    strcpy(plantas[10].nombre, "berenjena");
    strcpy(plantas[10].cuidados, "1 litro de agua por planta cada 3 días, 22 a 26 °C.");
    
    strcpy(plantas[11].nombre, "champiñón");
    strcpy(plantas[11].cuidados, "riego promedio de 75 a 80%., 12 y los 14 ºC");
    
    strcpy(plantas[12].nombre, "col de Bruselas");
    strcpy(plantas[12].cuidados, "riego moderado, sombra parcial en suelos profundos");
    
    strcpy(plantas[13].nombre, "ajo");
    strcpy(plantas[13].cuidados, "riegos más ligeros y frecuentes (cada 2 días), sentre 13 y 24 °C");
    
    strcpy(plantas[14].nombre, "guisantes");
    strcpy(plantas[14].cuidados, "riego humedad constante, 6 y 35 °C ");
    
    strcpy(plantas[15].nombre, "zanahoria");
    strcpy(plantas[15].cuidados, "riego de 30 a 45 minutos , 16 y 18°C");
    
    strcpy(plantas[16].nombre, "maíz");
    strcpy(plantas[16].cuidados, "riego 50 - 60 ml por semana, 30 y 34°C");
    
    strcpy(plantas[17].nombre, "hojas");
    strcpy(plantas[17].cuidados, "riego todas las semanas, pleno sol");
    
    strcpy(plantas[18].nombre, "brócoli");
    strcpy(plantas[18].cuidados, "riego moderado constante, 16 y 18 °C");
    
    strcpy(plantas[19].nombre, "patata");
    strcpy(plantas[19].cuidados, " hasta dos veces por semana, 10 a 25 ºC");
    
    strcpy(plantas[20].nombre, "legumbre");
    strcpy(plantas[20].cuidados, "de 1 y 3 riegos de auxilio ligeros, en un lugar fresco, seco y protegido de la humedad");
    
    strcpy(plantas[21].nombre, "alfalfa");
    strcpy(plantas[21].cuidados, "riego cada 17 días, entre 15 y 25ºC.");
    
    strcpy(plantas[22].nombre, "arveja");
    strcpy(plantas[22].cuidados, "riego moderado, sombra parcial");
    
    strcpy(plantas[23].nombre, "maní");
    strcpy(plantas[23].cuidados, "riego 500 y 1000 mm, 15 a 30ºC");
    
    strcpy(plantas[24].nombre, "haba");
    strcpy(plantas[24].cuidados, "riego moderado, clima fresco pero con mucha luz solar");
    
    strcpy(plantas[25].nombre, "lenteja");
    strcpy(plantas[25].cuidados, "riego una vez cada 2 días, 6º y 28º");
    
    strcpy(plantas[26].nombre, "soya");
    strcpy(plantas[26].cuidados, "riego mediante sistemas de riego por aspersión , 21 y 27 °C");
    
    strcpy(plantas[27].nombre, "tamarindo");
    strcpy(plantas[27].cuidados, "riego con una frecuencia que impida que la tierra se seque, 22 a 24 °C");
    
    strcpy(plantas[28].nombre, "judía");
    strcpy(plantas[28].cuidados, "22 y 35 °C, 2 a 3 veces a la semana.");
    
    strcpy(plantas[29].nombre, "guisante");
    strcpy(plantas[29].cuidados, "riego  2 o 3 veces por semana.,  6ºC y 35ºC");
    
    strcpy(plantas[30].nombre, "garbanzo");
    strcpy(plantas[30].cuidados, "riega con agua y suspende el riego hasta dos semanas más tarde, templado cálido");
    
}

void mostrarCuidados(const Planta plantas[], int num_plantas, const char *nombre) {
    bool encontrada = false;

    for (int i = 0; i < num_plantas; i++) {
        if (strcmp(nombre, plantas[i].nombre) == 0) {
            encontrada = true;
            printf("Cuidados para la planta '%s': %s\n", plantas[i].nombre, plantas[i].cuidados);
            break;
        }
    }

    if (!encontrada) {
        printf("No se encontraron cuidados para la planta '%s'\n", nombre);
    }
}

int obtenerValor() {
    int valor;
    printf("Por favor ingresar la cantidad de plantas a cultivar, \nrecuerde que debe ser en un intervalo de 0 a 30: ");
    scanf("%d", &valor);
    return valor;
}
int main () 
{
    int key, opts1, plant_type, weight;                                         //* Variables principales
    int weight1, weight2;                                                       //* Variables secundarias
    int start_times = 0;                                                        //* Cantidad de veces de uso/encendido
    char rpt = TRUE;                                                            //* Para la repetición del switch1
    int canplant; 
    int volverMenu = 1;
    
    printf ("\n\t\t\t\tHOLA :3\n\t BIENVENIDO AL ASISTENTE DE OPERACIONES DE TU INVERNADERO\n");  //* \t = press tab ->
    key = getch();                                                              //*pausa
    printf ("\n Selecciona una de las siguientes opciones introduciendo su número:\n ");
    printf ("\n\t1. Elegir una planta.\n\t2. Agregar material orgánico.");
    printf ("\n\t3. Iniciar asistente.\n\t0. Cancelar y apagar.\n\t");
    scanf("%d", &opts1);
    printf("\n _________\n\n");
   // system (cls);


    do 
    {
        int plant_value = 0, using_value = 0, weight_value = 0;                    //para validar si existe el dato pedido
        
        switch (opts1)                                                          //* Switch1
        {   

        case 0:
            if (opts1 == 0) {
                printf ("\n                           ____                            ");
                printf ("\n                          |                      |                           ");
                printf ("\n - - - - - - - - - - - - -  A P A G A N D O . . .  - - - - - - - - - - - - - ");
                printf ("\n                          |____|                     \n\n\n");
                key = getch();                                                  //*pausa
                rpt = FALSE;
            }else{
                printf ("\n                           ____                            ");
                printf ("\n                          |                      |                           ");
                printf ("\n - - - - - - - - - - - - -  A P A G A N D O . . .  - - - - - - - - - - - - - ");
                printf ("\n                          |____|                     \n\n\n");
                key = getch();                                                  //*pausa
                rpt = FALSE;
            }
        break;

        case 1:
        printf(" Ahora puede elegir el tipo de planta que va a agregar en su invernadero:");
            printf("\n\t1. Herbacea.\n\t2. Legumbre.\n\t3. Hortaliza.\n\t");
            scanf("%d", &plant_type);
            
    char tabla[FILAS][COLUMNAS][LONGITUD_PALABRA] = {
        {"herbaceas"   ,"hortaliza"          ,"legumbre" },
        {"girasol  "   ,"Berenjena"          ,"Alfalfa " },
        {"Cebolla  "   ,"Champiñón"          ,"Arveja  " },
        {"Altramuz "   ,"Col de Bruselas"    ,"maní    " },
        {"Espinaca "   ,"Ajo"                ,"        Haba" },
        {"Milenrama"   ,"Guisantes"          ,"Lenteja"  },
        {"Patata"      ,"        Zanahoria"          ,"Soya"     },
        {"La angélica" ,"Maíz"               ,"        Tamarindo"},
        {"Bambú"       ,"        Hojas "     ,"        Judía"},
        {"Alhelí"      ,"        Brócoli"            ,"        Guisante" },
        {"Amapola"     ,"        Patata"             ,"        Garbanzo" },
       
    };

        // Imprimir la tabla de datos
        printf("\tTabla de contenido:\n");
        
        for (int i = 0; i < FILAS; i++) {
           
        for (int j = 0; j < COLUMNAS; j++) {
            printf("%s\t", tabla[i][j]);
        }
        printf("\n");
    }
           Planta plantas[MAX_PLANTAS];
        inicializarPlantas(plantas);

        char nombre_planta[MAX_LONGITUD];
        printf("\nIngrese el nombre de la planta a utilizar: \n");
        scanf("%s", nombre_planta);
            mostrarCuidados(plantas, MAX_PLANTAS, nombre_planta);
          plant_value++;

         do {
           canplant = obtenerValor();
       } while (canplant < 0 || canplant > 31);

        printf("Valor ingresado correctamente: %d\n", canplant);
        break;

        case 2:
            printf("¿Cual es el peso actual del contenedor?\n");
            scanf("%d", &weight1);
            printf("Ahora puedes depositar los residuos\n");
            scanf("%d", &weight2);
            weight = weight1 + weight2;
            weight_value++;
            key = getch();                                                      //*pausa
            rpt = FALSE;
        break;

        case 3:
            printf("\n\n\t\t\tIniciando el asistente virtual...\n");
            key = getch();                                                      //*pausa
            rpt = FALSE;
        break;
        }
        
        while (plant_value==0, using_value==0) {
            if (plant_value==0){
                
                printf(" Ahora puede elegir el tipo de planta que va a agregar en su invernadero:");
                printf("\n\t1. Herbacea.\n\t2. Legumbre.\n\t3. Hortaliza.\n\t");
                scanf("%d", &plant_type);
                
                char tabla[FILAS][COLUMNAS][LONGITUD_PALABRA] = {
                {" herbaceas"   ,"hortaliza"          ,"legumbre" },
                {" girasol  "   ,"Berenjena"          ,"Alfalfa " },
                {" Cebolla  "   ,"Champiñón"          ,"Arveja  " },
                {" Altramuz "   ,"Col de Bruselas"    ,"maní    " },
                {" Espinaca "   ,"Ajo"                ,"        Haba" },
                {" Milenrama"   ,"Guisantes"          ,"Lenteja"  },
                {" Patata"      ,"        Zanahoria"          ,"Soya"     },
                {" La angélica" ,"Maíz"               ,"        Tamarindo"},
                {" Bambú"       ,"        Hojas "     ,"        Judía"},
                {" Alhelí"      ,"        Brócoli"            ,"        Guisante" },
                {" Amapola"     ,"        Patata"             ,"        Garbanzo" },
               
                };
            
                printf("\n\tTabla de contenido:\n");                                 // Imprimir tabla de datos
                
                for (int i = 0; i < FILAS; i++) {
                       
                    for (int j = 0; j < COLUMNAS; j++){
                      printf("%s\t", tabla[i][j]);
                    }
                    
                  printf("\n");
                }
                Planta plantas[MAX_PLANTAS];
                inicializarPlantas(plantas);
            
                char nombre_planta[MAX_LONGITUD];
                printf("\n Ingrese el nombre de la planta a utilizar: \n");
                scanf(" %s", nombre_planta);
                    mostrarCuidados(plantas, MAX_PLANTAS, nombre_planta);
                
                plant_value++;
               
                do {
                    canplant = obtenerValor();
                    } while (canplant < 0 || canplant > 31);
                    
                printf("Valor ingresado correctamente: %d\n", canplant);
                using_value++;
            }
            
            if (weight_value==0){
                weight = weight1 + weight2;
                printf("¿Cual es el peso actual del contenedor?\n");
                 scanf("%d", &weight1);
                printf("Ahora puedes depositar los residuos\n");
                 scanf("%d", &weight2);
                weight_value++;
                rpt = FALSE;
            }
        }
    }
    while (rpt = FALSE);                                                                //*se repite hasta cierto punto

    
    

    
    printf("\n _____________________________________________________________________________\n");
    printf("\n ---------------------ESTAS SON LAS ESTADISTICAS ACTUALES---------------------");
    printf("\n _____________________________________________________________________________\n");
    Planta plantas[MAX_PLANTAS];
    inicializarPlantas(plantas);

    char nombre_planta[MAX_LONGITUD];
    mostrarCuidados(plantas, MAX_PLANTAS, nombre_planta);


    //* Continuar agregando las variables estadísticas según el tipo de planta
    //* Falta la acción de repetir el menú 1 si falta un dato

return 0;
}