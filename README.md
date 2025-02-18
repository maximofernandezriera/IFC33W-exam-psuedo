# IFC33W-exam-psuedo

### 1

```
FUNCIÓN numeroDeDigitos(n)
    SI n = 0 ENTONCES
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
