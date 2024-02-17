# Programa-de-Ordenamineto-Metodo-Burbuja
#include <iostream>


void bubbleSortAsc(int arr[], int n) {
    for (int i = 0; i < n - 1; ++i) {
        for (int j = 0; j < n - i - 1; ++j) {
            if (arr[j] > arr[j + 1]) {
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
}


void bubbleSortDesc(int arr[], int n) {
    for (int i = 0; i < n - 1; ++i) {
        for (int j = 0; j < n - i - 1; ++j) {
            if (arr[j] < arr[j + 1]) {
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
}

int main() {
    int arr[10];

    std::cout << "Ingrese 10 valores enteros:\n";
    for (int i = 0; i < 10; ++i) {
        std::cout << "Valor " << i + 1 << ": ";
        std::cin >> arr[i];
    }

    char orden;
    std::cout << "Ingrese 'a' para orden ascendente o 'd' para orden descendente: ";
    std::cin >> orden;

    if (orden == 'a') {
        bubbleSortAsc(arr, 10);
        std::cout << "Arreglo ordenado en orden ascendente:\n";
    } else if (orden == 'd') {
        bubbleSortDesc(arr, 10);
        std::cout << "Arreglo ordenado en orden descendente:\n";
    } else {
        std::cout << "Opción no válida.\n";
        return 1;
    }

    for (int i = 0; i < 10; ++i) {
        std::cout << arr[i] << " ";
    }
    std::cout << std::endl;

    return 0;
}
