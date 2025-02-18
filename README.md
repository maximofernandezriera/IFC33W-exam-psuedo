# IFC33W-exam-psuedo

### 1

```
FUNCIÓN numeroDeDigitos(n)
    SI n < 10 ENTONCES
        RETORNAR 1
    FIN SI

    RETORNAR 1 + numeroDeDigitos(n / 10)
FIN FUNCIÓN
```


### 2

```
public class EdificiosVistaAlOeste {

    public static int edificiosVistaAlOeste(int[] alturas) {
        int n = alturas.length;
        int contador = 0; // Contador de edificios con vista al oeste
        int maximoActual = 0;

        // Según lo dibujado en clase debemos recorrer el array de derecha a izquierda
        for (int i = n - 1; i >= 0; i--) {
            if (alturas[i] > maximoActual) {
                contador++;
                maximoActual = alturas[i]; // Actualizamos la altura máxima
            }
        }

        return contador;
    }

    public static void main(String[] args) {
        int[] edificios1 = {3, 7, 8, 3, 6, 1};
        int[] edificios2 = {4, 2, 3, 1};
        int[] edificios3 = {5, 3, 8, 4, 7, 2, 6, 1, 9, 3, 5};

    }
}

```

### 5

```
FUNCIÓN generarSubsecuencias(cadena)
    resultado = CrearListaVacia()                 // Lista para almacenar las subsecuencias
    generarSubsecuenciasRecursivo(cadena, "", resultado)  // Llamada al método recursivo
    RETORNAR resultado                             // Devolver la lista con todas las subsecuencias
FIN FUNCIÓN

FUNCIÓN generarSubsecuenciasRecursivo(cadena, subsecuenciaActual, resultado)
    SI longitud(cadena) = 0 ENTONCES
        Añadir subsecuenciaActual A resultado     // Añadir la subsecuencia actual a la lista
        RETORNAR
    FIN SI

    // Incluir el primer carácter de la cadena en la subsecuencia actual
    generarSubsecuenciasRecursivo(subcadena(cadena, 1, longitud(cadena)), subsecuenciaActual + cadena[0], resultado)

    // Excluir el primer carácter de la cadena en la subsecuencia actual
    generarSubsecuenciasRecursivo(subcadena(cadena, 1, longitud(cadena)), subsecuenciaActual, resultado)
FIN FUNCIÓN

```

```

FUNCIÓN principal()
    cadena1 = "xyz"
    cadena2 = "xy"
    cadena3 = "a"
```

### 4

´´´
import java.util.HashMap;
import java.util.Map;

public class MinimoBebidas {

    public static int minimoBebidas(Map<Integer, int[]> preferencias) {
        HashMap<Integer, Integer> contadorBebidas = new HashMap<>();

        // Contamos la frecuencia de cada bebida en las preferencias de los clientes
        for (int cliente : preferencias.keySet()) {
            int[] bebidasPreferidas = preferencias.get(cliente);
            for (int bebida : bebidasPreferidas) {
                contadorBebidas.put(bebida, contadorBebidas.getOrDefault(bebida, 0) + 1);
            }
        }

        // Encontramos el número mínimo de bebidas necesarias
        int minBebidas = 0;
        while (!contadorBebidas.isEmpty()) {
            int bebidaMasFrecuente = -1;
            int maxFrecuencia = 0;

            // Encontramos la bebida más frecuente
            for (Map.Entry<Integer, Integer> entry : contadorBebidas.entrySet()) {
                if (entry.getValue() > maxFrecuencia) {
                    bebidaMasFrecuente = entry.getKey();
                    maxFrecuencia = entry.getValue();
                }
            }

            // Revisamos la frecuencia de la bebida más frecuente
            contadorBebidas.remove(bebidaMasFrecuente);
            minBebidas++;
        }

        return minBebidas;
    }

    public static void main(String[] args) {
        Map<Integer, int[]> preferencias = new HashMap<>();
        preferencias.put(0, new int[]{0, 1, 3, 6});
        preferencias.put(1, new int[]{1, 4, 7});
        preferencias.put(2, new int[]{2, 4, 7, 5});
        preferencias.put(3, new int[]{3, 2, 5});
        preferencias.put(4, new int[]{5, 8});

        System.out.println(minimoBebidas(preferencias));
    }
}


```
