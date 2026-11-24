# Cifrador "Triple Mix"

Sistema web que cifra y descifra frases con el cifrado de creación propia **Triple Mix**, que combina conversión de letras a números, multiplicación, suma de posición y división con residuo.

**Probar el sistema:** https://USUARIO.github.io/NOMBRE-DEL-REPOSITORIO/

## Cómo funciona

Claves: **K** (multiplicador, entero desde 1) y **D** (divisor, entero de 2 a 26). Por defecto K = 3 y D = 7.

Cada carácter se cifra así (A=1 ... Z=26, espacio=27, p = posición en la frase):

1. n = número del carácter
2. V = (n × K) + p
3. Se divide V entre D: el cociente (q) queda como número y el residuo (r) se convierte en letra (0=A, 1=B, 2=C...)
4. Bloque cifrado = q + letra

Para descifrar: V = (q × D) + r, luego n = (V − p) ÷ K, y se convierte n en carácter (27 = espacio).

### Ejemplo (K = 3, D = 7)

| Entrada | Resultado |
|---|---|
| `HOLA MUNDO` (cifrar) | `3E6F5E1A12C6D10A7B3A7G` |
| `3E6F5E1A12C6D10A7B3A7G` (descifrar) | `HOLA MUNDO` |

## Uso

Abre `index.html` en el navegador o entra al enlace de arriba. No necesita instalar nada.

## Limitaciones

Solo letras A-Z y espacios (las tildes y la ñ se convierten en letras sin tilde). Es un cifrado con fines educativos, no es seguro para proteger información real.
