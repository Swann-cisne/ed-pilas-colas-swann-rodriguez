# IMPLEMENTACIÓN DE UNA PILA (STACK)

// Estructura de un Nodo
ESTRUCTURA Nodo
    dato
    siguiente = NULO
FIN ESTRUCTURA

// Puntero global que controla la cima de la pila
cima = NULO

// 1. OPERACIÓN PUSH (Insertar arriba)
ALGORITMO push(valor)
    NUEVO_NODO = Crear Nodo(valor)
    
    SI cima == NULO ENTONCES
        cima = NUEVO_NODO
    SINO
        NUEVO_NODO.siguiente = cima
        cima = NUEVO_NODO
    FIN SI
FIN ALGORITMO

// 2. OPERACIÓN POP (Eliminar y retornar de arriba)
ALGORITMO pop()
    SI estaVacia() ENTONCES
        RETORNAR "Error: La pila está vacía"
    SINO
        NODO_ELIMINADO = cima
        cima = cima.siguiente
        RETORNAR NODO_ELIMINADO.dato
    FIN SI
FIN ALGORITMO

// 3. OPERACIÓN PEEK (Ver la cima sin borrar)
ALGORITMO peek()
    SI estaVacia() ENTONCES
        RETORNAR "La pila está vacía"
    SINO
        RETORNAR cima.dato
    FIN SI
FIN ALGORITMO

// 4. OPERACIÓN ESTÁ VACÍA (Control)
ALGORITMO estaVacia()
    SI cima == NULO ENTONCES
        RETORNAR Verdadero
    SINO
        RETORNAR Falso
    FIN SI
FIN ALGORITMO
