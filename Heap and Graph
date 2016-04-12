#include <stdio.h>
#include <stdlib.h>

typedef struct {
    int dim;
    int *a;
}heap;

typedef struct elemento {
    int nodo;
    struct elemento *next;
}elemento;

typedef elemento *link;

void inizializzaArray (int *a) {
    a[0] = 0;
}

void inizializzaArrayStruct (heap *h) {
    h->dim = 0;
}

void stampArray (int *a) {
    int i, k = 1;
    for (i=1; i<=a[0]; i++) {
        printf("(%d)%d   ", i, a[i]);
        if (i == k) {
            printf("\n");
            k = (i*2)+1;
        }
    }
    printf("\n\n");
}

void stampArrayStruct (heap *h) {
    int i, k = 1;
    for (i=1; i<=h->dim; i++){
        printf("(%d)%d   ", i, h->a[i]);
        if (i == k) {
            printf("\n");
            k = (i*2)+1;
        }
    }
    printf("\n\n");
}

void maxHeapify (int *a) {
    int i;
    for (i = (a[0]+1)/2; i>=1; i--) {
        int c = -1, aux, max = -1, t = i;
        while(t != c){
            c = t;
            max = a[c];
            if (( 2*c < (a[0]+1) ) && (a[c] < a[2*c])){
                t = 2*c;
                max = a[t];
            }
            if (( 2*c+1 < (a[0]+1) ) && (a[2*c + 1] > max))
                t = 2*c + 1;
            if ( c != t ){
                aux = a[c];
                a[c] = a[t];
                a[t] = aux;
            }
        }
    }
    printf("Bilanciamento eseguito con successo\nL'array che mi hai passato ora è un maxHeap!!\n");
}

void maxHeapifyStruct (heap *h) {
    int i;
    for (i = (h->dim+1)/2; i>=1; i--) {
        int c = -1, aux, max = -1, t = i;
        while(t != c){
            c = t;
            max = h->a[c];
            if (( 2*c < (h->dim+1) ) && (h->a[c] < h->a[2*c])){
                t = 2*c;
                max = h->a[t];
            }
            if (( 2*c+1 < (h->dim+1) ) && (h->a[2*c + 1] > max))
                t = 2*c + 1;
            if ( c != t ){
                aux = h->a[c];
                h->a[c] = h->a[t];
                h->a[t] = aux;
            }
        }
    }
    printf("Bilanciamento eseguito con successo\nLa struct che mi hai passato ora è un maxHeap!!\n");
}

void minHeapify (int *a) {
    int i;
    for (i = (a[0]+1)/2; i>=1; i--) {
        int c = -1, aux, max = -1, t = i;
        while(t != c){
            c = t;
            max = a[c];
            if (( 2*c < (a[0]+1) ) && (a[c] > a[2*c])){
                t = 2*c;
                max = a[t];
            }
            if (( 2*c+1 < (a[0]+1) ) && (a[2*c + 1] < max))
                t = 2*c + 1;
            if ( c != t ){
                aux = a[c];
                a[c] = a[t];
                a[t] = aux;
            }
        }
    }
    printf("Bilanciamento eseguito con successo\nL'array che mi hai passato ora è un minHeap!!\n");
}

void minHeapifyStruct (heap *h) {
    int i;
    for (i = (h->dim+1)/2; i>=1; i--) {
        int c = -1, aux, max = -1, t = i;
        while(t != c){
            c = t;
            max = h->a[c];
            if (( 2*c < (h->dim+1) ) && (h->a[c] > h->a[2*c])){
                t = 2*c;
                max = h->a[t];
            }
            if (( 2*c+1 < (h->dim+1) ) && (h->a[2*c + 1] < max))
                t = 2*c + 1;
            if ( c != t ){
                aux = h->a[c];
                h->a[c] = h->a[t];
                h->a[t] = aux;
            }
        }
    }
    printf("Bilanciamento eseguito con successo\nLa struct che mi hai passato ora è un minHeap!!\n");
}

void insertKeyInMaxHeap (int k, int *a) {      
    if (a[0] == 0) {
        a = (int *) realloc (a, 2*sizeof(int));
        a[0]++;
        a[a[0]] = k;
        printf("L'array che mi hai passato è vuoto.\nInserisco la radice..\n");
    }        
    else {
        a = (int *) realloc (a, (a[0]+2)*sizeof(int));
        a[0]++;
        a[a[0]] = k;
        int temp, i = a[0];
        while (i>1) {
            if (a[i]>a[i/2]) {
                temp = a[i];
                a[i] = a[i/2];
                a[i/2] = temp;
            }
            i /= 2;
        }
    }        
    printf("Inserimento in maxHeap eseguito con successo!\n");
}

void insertKeyInMaxHeapStruct (int k, heap *h) {
    if (h->dim == 0) {
        h->a = malloc (2*sizeof(int));
        h->a[1] = k;
        h->dim++;
        printf("La struct che mi hai passato è vuota.\nInserisco la radice..\n");
    }
    else {
        h->a = (int *) realloc (h->a, (h->dim+2)*sizeof(int));
        h->dim++;
        h->a[h->dim] = k;
        int temp, i = h->dim;
        while (i>1) {
            if (h->a[i]>h->a[i/2]) {
                temp = h->a[i];
                h->a[i] = h->a[i/2];
                h->a[i/2] = temp;
            }
            i /= 2;
        }
    }
    printf("Inserimento in maxHeapStruct eseguito con successo!\n");
}

void insertKeyInMinHeap (int k, int *a) {      
    if (a[0] == 0) {
        a = (int *) realloc (a, 2*sizeof(int));
        a[0]++;
        a[a[0]] = k;
        printf("L'array che mi hai passato è vuoto.\nInserisco la radice..\n");
    }        
    else {
        a = (int *) realloc (a, (a[0]+2)*sizeof(int));
        a[0]++;
        a[a[0]] = k;
        int temp, i = a[0];
        while (i>1) {
            if (a[i]<a[i/2]) {
                temp = a[i];
                a[i] = a[i/2];
                a[i/2] = temp;
            }
            i /= 2;
        }
    }        
    printf("Inserimento in maxHeap eseguito con successo!\n");
}

void insertKeyInMinHeapStruct (int k, heap *h) {
    if (h->dim == 0) {
        h->a = (int *) malloc (2*sizeof(int));
        h->a[1] = k;
        h->dim++;
        printf("La struct che mi hai passato è vuota.\nInserisco la radice..\n");
    }
    else {
        h->a = (int *) realloc (h->a, (h->dim+2)*sizeof(int));
        h->dim++;
        h->a[h->dim] = k;
        int temp, i = h->dim;
        while (i>1) {
            if (h->a[i]<h->a[i/2]) {
                temp = h->a[i];
                h->a[i] = h->a[i/2];
                h->a[i/2] = temp;
            }
            i /= 2;
        }
    }
    printf("Inserimento in minHeapStruct eseguito con successo!\n");
}

int extractKeyFromMaxHeapAndGetPosition (int k, int *a) {
    if (a[0] != 0) {
        int i, temp;
        _Bool trovato = 0;
        for (i = 1; i<=a[0] && !trovato; i++)
            if (a[i] == k) {
                temp = a[i];
                a[i] = a[a[0]];
                a[a[0]] = temp;
                a[0]--;
                trovato = 1;
                maxHeapify(a);
            }
        if (trovato) {
            printf("L'elemento %d è stato estratto con successo dall'array!!\n", k);
            return i-1;
        }
        printf("L'elemento %d non appartiene all'array!!\n", k);
    }
    else {
        printf("L'array che mi hai passato è vuoto, non posso estrarre!!\n");
        return -1;
    }
}

int extractKeyFromMaxHeapStructAndGetPosition (int k, heap *h) {
    if (h->dim != 0) {
        int i, temp;
        _Bool trovato = 0;
        for (i = 1; i<=h->dim && !trovato; i++)
            if (h->a[i] == k) {
                temp = h->a[i];
                h->a[i] = h->a[h->dim];
                h->a[h->dim] = temp;
                h->dim--;
                trovato = 1;
                maxHeapifyStruct(h);
            }
        if (trovato) {
            printf("L'elemento %d è stato estratto con successo dalla struct!!\n", k);
            return i-1;
        }
        printf("L'elemento %d non appartiene alla struct!!\n", k);
    }
    else {
        printf("La struct che mi hai passato è vuota, non posso estrarre!!\n");
        return -1;
    }
}

int extractKeyFromMinHeapAndGetPosition (int k, int *a) {
    if (a[0] != 0) {
        int i, temp;
        _Bool trovato = 0;
        for (i = 1; i<=a[0] && !trovato; i++)
            if (a[i] == k) {
                temp = a[i];
                a[i] = a[a[0]];
                a[a[0]] = temp;
                a[0]--;
                trovato = 1;
                minHeapify(a);
            }
        if (trovato) {
            printf("L'elemento %d è stato estratto con successo dall'array!!\n", k);
            return i-1;
        }
        printf("L'elemento %d non appartiene all'array!!\n", k);
    }
    else {
        printf("L'array che mi hai passato è vuoto, non posso estrarre!!\n");
        return -1;
    }
}

int extractKeyFromMinHeapStructAndGetPosition (int k, heap *h) {
    if (h->dim != 0) {
        int i, temp;
        _Bool trovato = 0;
        for (i = 1; i<=h->dim && !trovato; i++)
            if (h->a[i] == k) {
                temp = h->a[i];
                h->a[i] = h->a[h->dim];
                h->a[h->dim] = temp;
                h->dim--;
                trovato = 1;
                minHeapifyStruct(h);
            }
        if (trovato) {
            printf("L'elemento %d è stato estratto con successo dalla struct!!\n", k);
            return i-1;
        }
        printf("L'elemento %d non appartiene alla struct!!\n", k);
    }
    else {
        printf("La struct che mi hai passato è vuota, non posso estrarre!!\n");
        return -1;
    }
}

void stampGraph (int **G, int V) {
    int i, j;
    for (i = 0; i<V; i++) {
        for (j = 0; j<V; j++) {
            if (G[i][j] == 1)
                printf("[%d][%d]:%d  ", i, j, G[i][j]);
            else
                printf("[%d][%d]:   ", i, j);
        }
        printf("\n");
    }
}

void buildGraph (int **G, int V) {
    int i, j, cont = 0;
    _Bool building = 0;
    char scelta = 'n';
    
    printf("Vuoi inserire un arco ? (y/n)");
    scanf(" %c", &scelta);
    printf("\n");
    if (scelta == 'y')
        building = 1;
    
    while (building && cont != (V*(V-1))/2) {
        printf("Dimmi gli indici dei nodi tra cui inserire un arco: [][]");
        scanf("%d %d", &i, &j);
        printf("\n");
        if (i>=V || j>=V) {
            printf("Hai sbagliato!\nMi hai chiesto di creare un arco tra due nodi che non esistono!\n");
        }
        else if (i == j) {
            printf("Hai sbagliato!\nMi hai chiesto di creare un arco in un solo nodo!\n");
        }
        else if (G[i][j] == 1 || G[j][i] == 1) {
            printf("Hai sbagliato!\nMi hai chiesto di creare un arco tra due nodi che sono già legati!\n");
        }
        
        else {
            G[i][j] = 1;
            G[j][i] = 1;
            cont++;
        }
        printf("Vuoi inserire un altro arco ? (y/n)");
        scanf(" %c", &scelta);
        printf("\n");
        if (scelta == 'n') {
            building = 0;
        }
    }
    printf("Matrice d'adiacenza creata con successo!!\n");
}

void buildGraphList (link *A, int V) {
    int i, j, iCont = 0, jCont = 0;
    _Bool building = 0, iFound = 0, jFound = 0;
    char scelta = 'n';
    
    printf("Vuoi inserire un arco ? (y/n)");
    scanf(" %c", &scelta);
    printf("\n");
    if (scelta == 'y')
        building = 1;
    
    while (building && iCont != (V*(V-1))/2) {
        printf("Dimmi gli indici dei nodi tra cui inserire un arco: [][]");
        scanf("%d %d", &i, &j);
        printf("\n");
        if (i>=V || j>=V) {
            printf("Hai sbagliato!\nMi hai chiesto di creare un arco tra due nodi che non esistono!\n");
        }
        else if (i == j) {
            printf("Hai sbagliato!\nMi hai chiesto di creare un arco in un solo nodo!\n");
        }
        else {
            if (A[i] == NULL) {
                A[i] = calloc(1, sizeof(elemento));
                A[i]->nodo = j;
                A[i]->next = NULL;
                iCont++;
            }
            else {
                link temp = A[i];
                if (iCont == 1) {
                    if (temp->nodo == j)
                        iFound = 1;
                }
                while (temp->next != NULL && iFound == 0) {
                    if (temp->nodo == j) {
                        iFound = 1;
                    }
                    else {
                        temp = temp->next;
                    }
                }
                if (iFound == 0) {
                    temp->next = calloc(1, sizeof(elemento));
                    temp->next->nodo = j;
                    temp->next->next = NULL;
                    iCont++;
                }
            }
//          ORA FACCIO SPECULARE PER LA j
            if (A[j] == NULL) {
                A[j] = calloc(1, sizeof(elemento));
                A[j]->nodo = i;
                A[j]->next = NULL;
                jCont++;
            }
            else {
                link temp = A[j];
                if (jCont == 1) {
                    if (temp->nodo == i)
                        jFound = 1;
                }
                while (temp->next != NULL && jFound == 0) {
                    if (temp->nodo == i) {
                        jFound = 1;
                    }
                    else {
                        temp = temp->next;
                    }
                }
                if (jFound == 0) {
                    temp->next = calloc(1, sizeof(elemento));
                    temp->next->nodo = i;
                    temp->next->next = NULL;
                    jCont++;
                }
            }
            if (iFound)
                printf("Hai sbagliato!\nMi hai chiesto di creare un arco tra due nodi che sono già legati!\n");
            iFound = 0, jFound = 0;
        }
        printf("Vuoi inserire un altro arco ? (y/n)");
        scanf(" %c", &scelta);
        printf("\n");
        if (scelta == 'n') {
            building = 0;
        }
    }
    printf("Lista d'adiacenza creata con successo!!\n");
}

int detectMaxRankGraph (int **G, int V) {
    int i, j, sum = 0, ans = -1, *aux = calloc(V, sizeof(int));
    
    for (i = 0; i<V; i++)
        for (j = 0; j<V; j++)
            aux[i] += G[i][j];
    
    for (i = 0; i<V; i++)
        if (sum <= aux[i]) {
            sum = aux[i];
            ans = i;
        }
    
    return ans;
}

int detectMaxRankGraphList (link *A, int V) {
    int i, sum = 0, ans, *aux = calloc(V, sizeof(int));
    for (i = 0; i<V; i++) {
        link temp = A[i];
        while (temp != NULL) {
            aux[i]++;
            temp = temp->next;
        }
    }
    for (i = 0; i<10; i++)
        if (sum <= aux[i]) {
            sum = aux[i];
            ans = i;
        }
    return ans;
}

void countIsolatedNodes (int **G, int V) {
    int i, j, cont = 0, *aux = (int *) calloc (V, sizeof(int));
    
    for (i = 0; i<V; i++)
        for (j = 0; j<V; j++)
            aux[i] += G[i][j];
    
    for (i = 0; i<V; i++)
        if (aux[i] == 0) {
            printf("Il nodo %d è isolato!\n", i);
            cont++;
        }
    if (cont != 0)
        printf("In totale i nodi isolati del grafo che mi hai passato sono %d\n", cont);
    else
        printf("Il grafo che mi hai passato non ha nodi isolati!!\n");
}

void countIsolatedNodesList (link *A, int V) {
    int i, cont = 0;
    for (i = 0; i<V; i++) {
        if (A[i] == NULL) {
            printf("Il nodo %d è isolato!\n", i);
            cont++;
        }
    }
    if (cont != 0)
        printf("In totale i nodi isolati del grafo che mi hai passato sono %d\n", cont);
    else
        printf("Il grafo che mi hai passato non ha nodi isolati!!\n");
}

void controlIfRegularGraph (int **G, int V) {
    int i, j, *aux = (int *) calloc (V, sizeof(int));
    _Bool regular = 1;
    
    for (i = 0; i<V; i++)
        for (j = 0; j<V; j++)
            aux[i] += G[i][j];
    
    for (i = 0; i<V-1 && regular; i++)
        if (aux[i] != aux[i+1])
            regular = 0;
    
    if (regular)
        printf("Il grafo che mi hai passato è regolare!!\n");
    else
        printf("Il grafo che mi hai passato non è regolare!!\n");
}

void controlIfRegularGraphList (link *A, int V) {
    int i, sum = 0, ans, *aux = calloc(V, sizeof(int));
    _Bool regular = 1;
    for (i = 0; i<V; i++) {
        link temp = A[i];
        while (temp != NULL) {
            aux[i]++;
            temp = temp->next;
        }
    }
    
    for (i = 0; i<V-1 && regular; i++)
        if (aux[i] != aux[i+1])
            regular = 0;
    
    if (regular)
        printf("Il grafo che mi hai passato è regolare!!\n");
    else
        printf("Il grafo che mi hai passato non è regolare!!\n");
}

int main(int argc, char** argv) {
    
    int *a = (int *) malloc(1*sizeof(int));
    inizializzaArray(a);
    
    insertKeyInMaxHeap(20, a);
    insertKeyInMaxHeap(11, a);
    insertKeyInMaxHeap(0, a);
    insertKeyInMaxHeap(320, a);
    insertKeyInMaxHeap(67, a);
    insertKeyInMaxHeap(18, a);
    insertKeyInMaxHeap(45, a);
    
    stampArray(a);
    
    int t = extractKeyFromMaxHeapAndGetPosition(45, a);
    
    stampArray(a);
    
    printf("La posizione di 45 era: %d\n", t);
    
    
    
    heap h;
    inizializzaArrayStruct(&h);
    
    insertKeyInMaxHeapStruct(20, &h);
    insertKeyInMaxHeapStruct(11, &h);
    insertKeyInMaxHeapStruct(0, &h);
    insertKeyInMaxHeapStruct(320, &h);
    insertKeyInMaxHeapStruct(67, &h);
    insertKeyInMaxHeapStruct(18, &h);
    insertKeyInMaxHeapStruct(45, &h);
    
    stampArrayStruct(&h);
    
    int s = extractKeyFromMaxHeapStructAndGetPosition(45, &h);
    
    stampArrayStruct(&h);
    
    printf("La posizione di 45 era: %d\n", s);
    
    minHeapifyStruct(&h);
    
    stampArrayStruct(&h);
    
    
    
    int V = 10;    
    int i,j;
    
    int **G = (int **) calloc(V, sizeof(int*));  //creazione colonne matrice [i][j]
    
    for (i = 0; i<V; i++) {
        G[i] = (int *) calloc(V, sizeof(int));   //creazione righe matrice [i][j]
    }    
    
    buildGraph(G, V);
    
    stampGraph(G, V);
    
    printf("Il nodo con il rango massimo è il numero %d\n", detectMaxRankGraph(G, V));
    
    countIsolatedNodes(G, V);
    
    controlIfRegularGraph(G, V);
    
    link *A = calloc (V, sizeof(link));
    
    buildGraphList(A, V);
    
    printf("%d\n", detectMaxRankGraphList(A, V));
    
    countIsolatedNodesList(A, V);
    
    controlIfRegularGraphList(A, V);
    
    return (EXIT_SUCCESS);
}
