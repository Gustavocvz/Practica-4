//Gustavo Alejandro Castro Vázquez 
//Practica 22 de Junio del 2021

#include <stdio.h>
#include <stdlib.h>
#include <stdbool.h>


typedef struct Nodo NODO;
typedef int INFO;

struct Nodo{
    INFO dato;
    NODO* siguiente;
};

typedef struct Lista LISTA;

struct Lista{
    NODO* head;
    NODO* tail;
    int num;
};

NODO* CrearNodo(INFO dato);
bool InsertarAlInicio(LISTA* lista,INFO dato);
bool InsertarAlFinal(LISTA* lista,INFO dato);
bool Insertar(LISTA* lista,INFO dato,int posicion);
bool EsVacia(LISTA* lista);
void ImprimirLista(LISTA* lista);
LISTA* crear_lista(void);

LISTA* crear_lista(void){
    LISTA* lista = (LISTA*) malloc(1*sizeof(LISTA));
    lista->head = lista->tail = NULL;
    lista->num = 0;
    return lista;
}

NODO* CrearNodo(INFO dato){
    
    //Actividad 3
    /*NODO* nodo = (NODO*) malloc(1*sizeof(NODO));
    printf("\nCon malloc");*/
    NODO* nodo = (NODO*) calloc(1,sizeof(NODO));
    printf("\nCon calloc");
    printf("\n valor de nodo: %d\n", nodo->siguiente);
    nodo->dato=dato;
    nodo->siguiente = NULL;
    return nodo;
}

bool InsertarAlInicio(LISTA* lista,INFO dato){
    NODO* nodo = CrearNodo(dato);
    if(EsVacia(lista)){
        lista->head = nodo;
        lista->tail = nodo;
        lista->tail->siguiente = nodo;  // nodo->siguiente = nodo;
        lista->num++;
        return true;
    }else{
        nodo->siguiente = lista->head;
        lista->head = nodo;
        lista->num++;
        return true;
    }
    return false;
}
bool InsertarAlFinal(LISTA* lista,INFO dato){
    NODO* nodo = CrearNodo(dato);
    if(EsVacia(lista)){
        InsertarAlInicio(lista,dato);
        return true;
    }else{
        lista->tail->siguiente = nodo;
        lista->tail = nodo; // lista->tail = lista->tail->siguiente
        lista->tail->siguiente = lista->head;
        lista->num++;
        return true;
    }
    return false;
}
bool Insertar(LISTA* lista,INFO dato,int posicion){
    if(posicion == 0) return InsertarAlInicio(lista,dato);
    else if(posicion >= lista->num) return InsertarAlFinal(lista,dato);
    else if(posicion > 0 && posicion < lista->num){
        NODO* nodo = CrearNodo(dato);
        NODO* temporal = lista->head;
        int npos = 0;
        for(npos = 0; npos < posicion-1; npos++){ 
            temporal = temporal->siguiente; // El for se rompe al llegar a posicion-1
        }
        nodo->siguiente = temporal->siguiente;
        temporal->siguiente = nodo;
        lista->num++;
        return true;
    }
    return false;
}

void Imprimirlista(LISTA* lista){
    NODO* temporal = lista->head;
    int posicion;
    printf("\n");
    for(posicion = 0; posicion < lista->num; posicion++){
        if(posicion == 0){
            temporal = lista->head;
        }else{
            temporal = temporal->siguiente;
        }
        printf("%d --> ",temporal->dato);
        printf("=direción %p--> " ,temporal);
    }

    //for(temporal = lista->head; temporal != NULL; temporal = temporal->siguiente){
    //    printf("%d --> ",temporal->dato);
    //}
    printf("NULL\n");
    system("PAUSE");
}

bool EsVacia(LISTA* lista){
    if(lista->head == NULL && lista->tail == NULL) return true;
    return false;
}

                                                /*Malloc() toma un único argumento:
                                                (la cantidad de memoria para asignar en bytes)
                                                calloc() necesita dos argumentos :
                                                (el número de variables para asignar en la memoria
                                                y el tamaño en bytes de una sola variable).
                                                realloc() aumenta o disminuye el tamaño del bloque*/ 
int main( int argc, char **argv){               //de memoria especificada. Reasigna si es necesario

    int *array, *array2= NULL, num, cont;
    printf("¿Cuántos elementos tiene el arreglo\n");
    scanf("%d", &num);
    array = (int*) calloc(num, sizeof(int));
    //array = (int*) malloc(num*sizeof(int));       
    if(array != NULL){

        for(cont= 0; cont<num; cont++){
            printf( "Ingresa el elemento %d \n", cont+1);
            scanf("%d", (array+cont));
        } //Al llamar a realloc no permite meterle datos

        printf("Vector reservado: \n \t[");
        
        for(cont= 0; cont < num; cont++){
            printf("valor:%d dir:%p", *(array+cont),array+cont);
            printf("dir:%p de array\n", array);
        }
        printf( "\t]\n");
    

    
    //Actividad 1 realloc
    
    /*free(array);
    array = (int*) realloc(array, num*sizeof(int));
    for(cont= 0; cont<num; cont++){
        printf( "Ingresa el elemento %d \n", cont+1);
        scanf("%d", (array+cont));
    } //Al llamar a realloc no permite meterle datos

    printf("Vector reservado: \n \t[");
        
    for(cont= 0; cont < num; cont++){
        printf("valor:%d dir:%p", *(array+cont),array+cont);
        printf("dir:%p de array\n", array);
    }
    printf( "\t]\n");
    */

        //Actividad 2 
        num /=3; 
        array = (int*) realloc(array, num*sizeof(int)); 
        /*realloc:aumenta o disminuye el tamaño del    
        bloque de memoria especificada.Reasigna si es necesario*/ 
        if (array != NULL){
            for (cont=0; cont<num; cont++){
                printf( "Ingresa el elemento %d\n", cont + 1);
                scanf( "%d", (array +cont));
            }
            printf( "Vector reservado: \n \t[");
            for (cont= 0; cont<num; cont++){
                printf("\tvalor:%d dir:%p", *(array +cont), array +cont);
                printf("dir:%p de array\n", array);
                printf("]\n");
            }
        }    
    }

    //ACtividad 4
    LISTA* Primerf;
    Primerf = crear_lista();
    for(int i= 0; i<4; i++){
        Insertar(Primerf, i, i);
    }
    Imprimirlista(Primerf);

    system("PAUSE");
    return 0;
        
}



