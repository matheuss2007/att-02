# att-02
// 2 é o único número par que é primo
if (num == 2) return true;

// Números pares maiores que 2 não são primos
if (num % 2 == 0) return false;

// Verifica se o número é divisível por qualquer número ímpar
for (int i = 3; i * i <= num; i += 2) {
    if (num % i == 0) return false;
}

return true;
}

int main() { int num;

cout << "Digite um número: ";
cin >> num;

if (isPrime(num)) {
    cout << num << " é um número primo." << endl;
} else {
    cout << num << " não é um número primo." << endl;
}

return 0;
}

QUESTÃO 12: #include using namespace std;

int main() { int N;

cout << "Digite o valor de N: ";
cin >> N;

// Verifica se o valor de N é válido (não-negativo)
if (N < 0) {
    cout << "O valor de N deve ser um número natural (não-negativo)." << endl;
    return 1;
}

// Calcula a soma usando a fórmula
int soma = N * (N + 1) / 2;

cout << "A soma dos primeiros " << N << " números naturais é: " << soma << endl;

return 0;
}

QUESTÃO 13: #include using namespace std;

int main() { int N;

cout << "Digite o valor de N (número de termos): ";
cin >> N;

// Verifica se o valor de N é válido (positivo)
if (N <= 0) {
    cout << "O valor de N deve ser um número positivo." << endl;
    return 1;
}

// Variáveis para armazenar os termos da sequência de Fibonacci
long long a = 0, b = 1, c;

cout << "Os primeiros " << N << " termos da sequência de Fibonacci são:" << endl;

// Exibe o primeiro termo
if (N >= 1) cout << a << " ";

// Exibe o segundo termo
if (N >= 2) cout << b << " ";

// Calcula e exibe os termos seguintes
for (int i = 3; i <= N; ++i) {
    c = a + b;
    cout << c << " ";
    a = b;
    b = c;
}

cout << endl;

return 0;
}

QUESTÃO 14: #include using namespace std;

int main() { int num, numInvertido = 0;

cout << "Digite um número inteiro: ";
cin >> num;

int numOriginal = num; // Armazena o número original para exibir depois, se necessário

// Converte o número para positivo se for negativo
if (num < 0) {
    num = -num;
}

// Inverte o número
while (num > 0) {
    int digito = num % 10; // Extrai o último dígito
    numInvertido = numInvertido * 10 + digito; // Adiciona o dígito ao novo número invertido
    num /= 10; // Remove o último dígito do número original
}

// Exibe o número invertido
cout << "Número invertido: " << (numOriginal < 0 ? -numInvertido : numInvertido) << endl;

return 0;
}

QUESTÃO 15: #include #include // Inclui a biblioteca para a função pow using namespace std;

int main() { double base, expoente;

cout << "Digite a base: ";
cin >> base;

cout << "Digite o expoente: ";
cin >> expoente;

// Calcula a potência usando a função pow
double resultado = pow(base, expoente);

cout << base << " elevado a " << expoente << " é: " << resultado << endl;

return 0;
}

QUESTÃO 16: #include using namespace std;

bool isPalindrome(int num) { int original = num; int invertido = 0;

// Converte o número para positivo se for negativo
if (num < 0) {
    return false;
}

// Inverte o número
while (num > 0) {
    int digito = num % 10;
    invertido = invertido * 10 + digito;
    num /= 10;
}

return original == invertido;
}

int main() { int num;

cout << "Digite um número: ";
cin >> num;

if (isPalindrome(num)) {
    cout << num << " é um palíndromo." << endl;
} else {
    cout << num << " não é um palíndromo." << endl;
}

return 0;
}

QUESTÃO 17: #include using namespace std;

// Função para calcular o Máximo Divisor Comum (MDC) usando o Algoritmo de Euclides int calcularMDC(int a, int b) { while (b != 0) { int resto = a % b; a = b; b = resto; } return a; }

int main() { int num1, num2;

cout << "Digite o primeiro número: ";
cin >> num1;

cout << "Digite o segundo número: ";
cin >> num2;

if (num1 < 0 || num2 < 0) {
    cout << "Os números devem ser não-negativos." << endl;
    return 1;
}

int mdc = calcularMDC(num1, num2);

cout << "O Máximo Divisor Comum (MDC) de " << num1 << " e " << num2 << " é: " << mdc << endl;

return 0;
}

QUESTÃO 18: #include using namespace std;

// Função para calcular o Máximo Divisor Comum (MDC) usando o Algoritmo de Euclides int calcularMDC(int a, int b) { while (b != 0) { int resto = a % b; a = b; b = resto; } return a; }

// Função para calcular o Mínimo Múltiplo Comum (MMC) int calcularMMC(int a, int b) { if (a == 0 || b == 0) return 0; // MMC de qualquer número com 0 é 0 return (a * b) / calcularMDC(a, b); }

int main() { int num1, num2;

cout << "Digite o primeiro número: ";
cin >> num1;

cout << "Digite o segundo número: ";
cin >> num2;

if (num1 < 0 || num2 < 0) {
    cout << "Os números devem ser não-negativos." << endl;
    return 1;
}

int mmc = calcularMMC(num1, num2);

cout << "O Mínimo Múltiplo Comum (MMC) de " << num1 << " e " << num2 << " é: " << mmc << endl;

return 0;
}

QUESTÃO 19: #include using namespace std;

// Função para verificar se um número é perfeito bool isPerfect(int num) { if (num <= 1) return false; // Números menores ou iguais a 1 não são perfeitos

int somaDivisores = 0;

// Calcula a soma dos divisores próprios
for (int i = 1; i <= num / 2; ++i) {
    if (num % i == 0) {
        somaDivisores += i;
    }
}

// Verifica se a soma dos divisores é igual ao número
return somaDivisores == num;
}

int main() { int num;

cout << "Digite um número: ";
cin >> num;

if (isPerfect(num)) {
    cout << num << " é um número perfeito." << endl;
} else {
    cout << num << " não é um número perfeito." << endl;
}

return 0;
}

QUESTÃO 20: #include using namespace std;

// Função para ordenar o vetor usando o algoritmo Bubble Sort void bubbleSort(int arr[], int n) { for (int i = 0; i < n - 1; ++i) { for (int j = 0; j < n - i - 1; ++j) { if (arr[j] > arr[j + 1]) { // Troca arr[j] e arr[j + 1] int temp = arr[j]; arr[j] = arr[j + 1]; arr[j + 1] = temp; } } } }

// Função para exibir os elementos do vetor void exibirVetor(int arr[], int n) { for (int i = 0; i < n; ++i) { cout << arr[i] << " "; } cout << endl; }

int main() { int n;

cout << "Digite o número de elementos no vetor: ";
cin >> n;

int* arr = new int[n]; // Cria um vetor dinamicamente

cout << "Digite os elementos do vetor: ";
for (int i = 0; i < n; ++i) {
    cin >> arr[i];
}

// Ordena o vetor
bubbleSort(arr, n);

// Exibe o vetor ordenado
cout << "Vetor ordenado em ordem crescente: ";
exibirVetor(arr, n);

delete[] arr; // Libera a memória alocada para o vetor

return 0;
}

QUESTÃO 21: #include using namespace std;

// Função para realizar a busca linear em um vetor int buscaLinear(const int arr[], int n, int valor) { for (int i = 0; i < n; ++i) { if (arr[i] == valor) { return i; // Retorna o índice onde o valor foi encontrado } } return -1; // Retorna -1 se o valor não for encontrado }

int main() { int n, valor;

cout << "Digite o número de elementos no vetor: ";
cin >> n;

int* arr = new int[n]; // Cria um vetor dinamicamente

cout << "Digite os elementos do vetor: ";
for (int i = 0; i < n; ++i) {
    cin >> arr[i];
}

cout << "Digite o valor a ser buscado: ";
cin >> valor;

int resultado = buscaLinear(arr, n, valor);

if (resultado != -1) {
    cout << "Valor " << valor << " encontrado no índice " << resultado << "." << endl;
} else {
    cout << "Valor " << valor << " não encontrado no vetor." << endl;
}

delete[] arr; // Libera a memória alocada para o vetor

return 0;
}

QUESTÃO 22: #include using namespace std;

// Função para realizar a busca binária em um vetor ordenado int buscaBinaria(const int arr[], int n, int valor) { int esquerda = 0; int direita = n - 1;

while (esquerda <= direita) {
    int meio = esquerda + (direita - esquerda) / 2;
    
    if (arr[meio] == valor) {
        return meio; // Valor encontrado, retorna o índice
    }
    
    if (arr[meio] < valor) {
        esquerda = meio + 1; // Descartar a metade esquerda
    } else {
        direita = meio - 1; // Descartar a metade direita
    }
}

return -1; // Valor não encontrado
}

int main() { int n, valor;

cout << "Digite o número de elementos no vetor: ";
cin >> n;

int* arr = new int[n]; // Cria um vetor dinamicamente

cout << "Digite os elementos do vetor (em ordem crescente): ";
for (int i = 0; i < n; ++i) {
    cin >> arr[i];
}

cout << "Digite o valor a ser buscado: ";
cin >> valor;

int resultado = buscaBinaria(arr, n, valor);

if (resultado != -1) {
    cout << "Valor " << valor << " encontrado no índice " << resultado << "." << endl;
} else {
    cout << "Valor " << valor << " não encontrado no vetor." << endl;
}

delete[] arr; // Libera a memória alocada para o vetor

return 0;
}

QUESTÃO 23:

QUESTÃO 24: #include <stdio.h> #include <math.h> #include <string.h>

int binarioParaDecimal(const char *binario) { int decimal = 0; int comprimento = strlen(binario);

for (int i = comprimento - 1; i >= 0; i--) {
    if (binario[i] == '1') {
        decimal += pow(2, comprimento - 1 - i);
    }
}

return decimal;
}

int main() { char binario[65]; // Assumindo um máximo de 64 bits + 1 para o terminador nulo

printf("Digite um número binário: ");
scanf("%s", binario);

// Verifica se o número binário é válido
for (int i = 0; i < strlen(binario); i++) {
    if (binario[i] != '0' && binario[i] != '1') {
        printf("Número binário inválido.\n");
        return 1;
    }
}

int decimal = binarioParaDecimal(binario);

printf("O número decimal é: %d\n", decimal);

return 0;
}

QUESTÃO 25: #include <stdio.h>

void decimalParaBinario(int numero) { // Vetor para armazenar os dígitos binários int binario[32]; int i = 0;

// Caso especial para o número 0
if (numero == 0) {
    printf("0");
    return;
}

// Calcula os dígitos binários
while (numero > 0) {
    binario[i] = numero % 2;  // Armazena o resto da divisão por 2
    numero /= 2;              // Divide o número por 2
    i++;
}

// Imprime os dígitos binários na ordem correta (reversa)
printf("Número binário: ");
for (int j = i - 1; j >= 0; j--) {
    printf("%d", binario[j]);
}
printf("\n");
}

int main() { int numeroDecimal;

printf("Digite um número decimal: ");
scanf("%d", &numeroDecimal);

decimalParaBinario(numeroDecimal);

return 0;
}

QUESTÃO 26: #include <stdio.h>

#define MAX 10 // Definindo o tamanho máximo para as matrizes

// Função para ler uma matriz void lerMatriz(int matriz[MAX][MAX], int linhas, int colunas) { printf("Digite os elementos da matriz:\n"); for (int i = 0; i < linhas; i++) { for (int j = 0; j < colunas; j++) { printf("Elemento [%d][%d]: ", i, j); scanf("%d", &matriz[i][j]); } } }

// Função para imprimir uma matriz void imprimirMatriz(int matriz[MAX][MAX], int linhas, int colunas) { printf("Matriz:\n"); for (int i = 0; i < linhas; i++) { for (int j = 0; j < colunas; j++) { printf("%d ", matriz[i][j]); } printf("\n"); } }

// Função para somar duas matrizes void somarMatrizes(int matriz1[MAX][MAX], int matriz2[MAX][MAX], int resultado[MAX][MAX], int linhas, int colunas) { for (int i = 0; i < linhas; i++) { for (int j = 0; j < colunas; j++) { resultado[i][j] = matriz1[i][j] + matriz2[i][j]; } } }

int main() { int matriz1[MAX][MAX], matriz2[MAX][MAX], resultado[MAX][MAX]; int linhas, colunas;

// Leitura do tamanho das matrizes
printf("Digite o número de linhas e colunas das matrizes: ");
scanf("%d %d", &linhas, &colunas);

// Verifica se o tamanho é válido
if (linhas > MAX || colunas > MAX || linhas <= 0 || colunas <= 0) {
    printf("Tamanho da matriz inválido.\n");
    return 1;
}

printf("Digite os elementos da primeira matriz:\n");
lerMatriz(matriz1, linhas, colunas);

printf("Digite os elementos da segunda matriz:\n");
lerMatriz(matriz2, linhas, colunas);

// Somar as matrizes
somarMatrizes(matriz1, matriz2, resultado, linhas, colunas);

// Exibir as matrizes e o resultado
printf("\nPrimeira matriz:\n");
imprimirMatriz(matriz1, linhas, colunas);

printf("\nSegunda matriz:\n");
imprimirMatriz(matriz2, linhas, colunas);

printf("\nMatriz resultante da soma:\n");
imprimirMatriz(resultado, linhas, colunas);

return 0;
}

QUESTÃO 27: #include <stdio.h>

#define MAX 10 // Definindo o tamanho máximo para as matrizes

// Função para ler uma matriz void lerMatriz(int matriz[MAX][MAX], int linhas, int colunas) { printf("Digite os elementos da matriz:\n"); for (int i = 0; i < linhas; i++) { for (int j = 0; j < colunas; j++) { printf("Elemento [%d][%d]: ", i, j); scanf("%d", &matriz[i][j]); } } }

// Função para imprimir uma matriz void imprimirMatriz(int matriz[MAX][MAX], int linhas, int colunas) { printf("Matriz:\n"); for (int i = 0; i < linhas; i++) { for (int j = 0; j < colunas; j++) { printf("%d ", matriz[i][j]); } printf("\n"); } }

// Função para multiplicar duas matrizes void multiplicarMatrizes(int matriz1[MAX][MAX], int linhas1, int colunas1, int matriz2[MAX][MAX], int linhas2, int colunas2, int resultado[MAX][MAX]) { // Verifica se a multiplicação é possível if (colunas1 != linhas2) { printf("A multiplicação não é possível. O número de colunas da primeira matriz deve ser igual ao número de linhas da segunda matriz.\n"); return; }

// Inicializa a matriz resultado com zeros
for (int i = 0; i < linhas1; i++) {
    for (int j = 0; j < colunas2; j++) {
        resultado[i][j] = 0;
    }
}

// Calcula o produto das matrizes
for (int i = 0; i < linhas1; i++) {
    for (int j = 0; j < colunas2; j++) {
        for (int k = 0; k < colunas1; k++) {
            resultado[i][j] += matriz1[i][k] * matriz2[k][j];
        }
    }
}
}

int main() { int matriz1[MAX][MAX], matriz2[MAX][MAX], resultado[MAX][MAX]; int linhas1, colunas1, linhas2, colunas2;

// Leitura da primeira matriz
printf("Digite o número de linhas e colunas da primeira matriz: ");
scanf("%d %d", &linhas1, &colunas1);

if (linhas1 > MAX || colunas1 > MAX || linhas1 <= 0 || colunas1 <= 0) {
    printf("Tamanho da matriz inválido.\n");
    return 1;
}

printf("Digite os elementos da primeira matriz:\n");
lerMatriz(matriz1, linhas1, colunas1);

// Leitura da segunda matriz
printf("Digite o número de linhas e colunas da segunda matriz: ");
scanf("%d %d", &linhas2, &colunas2);

if (linhas2 > MAX || colunas2 > MAX || linhas2 <= 0 || colunas2 <= 0) {
    printf("Tamanho da matriz inválido.\n");
    return 1;
}

if (colunas1 != linhas2) {
    printf("A multiplicação não é possível. O número de colunas da primeira matriz deve ser igual ao número de linhas da segunda matriz.\n");
    return 1;
}

printf("Digite os elementos da segunda matriz:\n");
lerMatriz(matriz2, linhas2, colunas2);

// Multiplicar as matrizes
multiplicarMatrizes(matriz1, linhas1, colunas1, matriz2, linhas2, colunas2, resultado);

// Exibir as matrizes e o resultado
printf("\nPrimeira matriz:\n");
imprimirMatriz(matriz1, linhas1, colunas1);

printf("\nSegunda matriz:\n");
imprimirMatriz(matriz2, linhas2, colunas2);

printf("\nMatriz resultante da multiplicação:\n");
imprimirMatriz(resultado, linhas1, colunas2);

return 0;
}

QUESTÃO 28:

QUESTÃO 29: #include <stdio.h> #include <ctype.h> // Para a função tolower

// Função para contar o número de vogais em uma string int contarVogais(const char *str) { int contador = 0; char c;

// Itera sobre cada caractere da string
while ((c = *str++) != '\0') {
    // Converte o caractere para minúscula
    c = tolower(c);

    // Verifica se o caractere é uma vogal
    if (c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u') {
        contador++;
    }
}

return contador;
}

int main() { char str[100];

// Leitura da string do usuário
printf("Digite uma string: ");
fgets(str, sizeof(str), stdin);

// Conta o número de vogais na string
int numeroDeVogais = contarVogais(str);

// Exibe o resultado
printf("Número de vogais na string: %d\n", numeroDeVogais);

return 0;
}

QUESTÃO 30: #include <stdio.h> #include <ctype.h> // Para a função isdigit

// Função que converte uma string para um número inteiro int stringParaInteiro(const char *str) { int resultado = 0; int sinal = 1; // 1 para positivo, -1 para negativo

// Ignorar espaços iniciais
while (isspace(*str)) {
    str++;
}

// Verificar o sinal
if (*str == '-') {
    sinal = -1;
    str++;
} else if (*str == '+') {
    str++;
}

// Converter a string para número inteiro
while (*str && isdigit(*str)) {
    resultado = resultado * 10 + (*str - '0');
    str++;
}

return sinal * resultado;
}

int main() { char str[100];

// Leitura da string do usuário
printf("Digite uma string para converter em inteiro: ");
fgets(str, sizeof(str), stdin);

// Remove o caractere de nova linha, se presente
str[strcspn(str, "\n")] = '\0';

// Converte a string para inteiro
int numero = stringParaInteiro(str);

// Exibe o resultado
printf("Número inteiro convertido: %d\n", numero);

return 0;
}
