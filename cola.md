# IMPLEMENTACIÓN DE UNA COLA (QUEUE)

// Estructura de un Nodo
ESTRUCTURA Nodo
    dato
    siguiente = NULO
FIN ESTRUCTURA

// Punteros globales para controlar los extremos de la fila
frente = NULO
final = NULO

// 1. OPERACIÓN ENQUEUE (Formarse al final)
ALGORITMO enqueue(valor)
    NUEVO_NODO = Crear Nodo(valor)
    
    SI estaVacia() ENTONCES
        frente = NUEVO_NODO
        final = NUEVO_NODO
    SINO
        final.siguiente = NUEVO_NODO
        final = NUEVO_NODO
    FIN SI
FIN ALGORITMO

// 2. OPERACIÓN DEQUEUE (Atender al frente y sacarlo)
ALGORITMO dequeue()
    SI estaVacia() ENTONCES
        RETORNAR "Error: La cola está vacía"
    SINO
        NODO_ELIMINADO = frente
        frente = frente.siguiente
        
        // Si al sacar al elemento la cola quedó vacía, limpiamos el puntero final
        SI frente == NULO ENTONCES
            final = NULO
        FIN SI
        
        RETORNAR NODO_ELIMINADO.dato
    FIN SI
FIN ALGORITMO

// 3. OPERACIÓN PEEK (Mirar quién es el siguiente al frente)
ALGORITMO peek()
    SI estaVacia() ENTONCES
        RETORNAR "La cola está vacía"
    SINO
        RETORNAR frente.dato
    FIN SI
FIN ALGORITMO

// 4. OPERACIÓN ESTÁ VACÍA (Control)
ALGORITMO estaVacia()
    SI frente == NULO ENTONCES
        RETORNAR Verdadero
    SINO
        RETORNAR Falso
    FIN SI
FIN ALGORITMO