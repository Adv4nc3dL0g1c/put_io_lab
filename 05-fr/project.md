# System aukcyjny

## Wprowadzenie

Specyfikacja wymagań funkcjonalnych w ramach informatyzacji procesu sprzedaży produktów w oparciu o mechanizm aukcyjny. 

## Procesy biznesowe

---
<a id="bc1"></a>
### BC1: Sprzedaż aukcyjna 

**Aktorzy:** [Sprzedający](#ac1), [Kupujący](#ac2)

**Opis:** Proces biznesowy opisujący sprzedaż za pomocą mechanizmu aukcyjnego. |

**Scenariusz główny:**
1. [Sprzedający](#ac1) wystawia produkt na aukcję. ([UC1](#uc1))
2. [Kupujący](#ac2) oferuje kwotę za produkt wyższą od aktualnie najwyższej oferty. ([UC2](#uc2)) ([BR1](#br1))
3. [Kupujący](#ac2) wygrywa aukcję ([BR2](#br2))
4. [Kupujący](#ac2) przekazuje należność Sprzedającemu. ([UC3](#uc3))
5. [Sprzedający](#ac1) przekazuje produkt Kupującemu. ([UC4](#uc4))

**Scenariusze alternatywne:** 

2.A. Oferta Kupującego została przebita, a [Kupujący](#ac2) pragnie przebić aktualnie najwyższą ofertę.
* 2.A.1. Przejdź do kroku 2. ([UC2](#uc2))

3.A. Czas aukcji upłynął i [Kupujący](#ac2) przegrał aukcję. ([BR2](#br2))
* 3.A.1. Koniec przypadku użycia. ([UC5](#uc5))

---

## Aktorzy

<a id="ac1"></a>
### AC1: Sprzedający

Osoba oferująca towar na aukcji.

<a id="ac2"></a>
### AC2: Kupujący

Osoba chcąca zakupić produkt na aukcji.


## Przypadki użycia poziomu użytkownika

### Aktorzy i ich cele

[Sprzedający](#ac1):
* [UC1](#uc1): Wystawienie produktu na aukcję
* [UC4](#uc4): Potwierdzenie przekazania produktu
* [UC6](#uc6): Anulowanie aukcji 
* [UC8](#uc8): Rejestracja w systemie

[Kupujący](#ac2)
* [UC2](#uc2): Złożenie oferty na produkt
* [UC3](#uc3): Opłacenie wygranej aukcji
* [UC5](#uc5): Przeglądanie wyników aukcji
* [UC7](#uc7): Przeglądanie listy aukcji
* [UC8](#uc8): Rejestracja w systemie


---
<a id="uc1"></a>
### UC1: Wystawienie produktu na aukcję

**Aktorzy:** [Sprzedający](#ac1)

**Scenariusz główny:**
1. [Sprzedający](#ac1) zgłasza do systemu chęć wystawienia produktu na aukcję.
2. System prosi o podanie danych produktu i ceny wywoławczej.
3. [Sprzedający](#ac1) podaje dane produktu oraz cenę wywoławczą.
4. System weryfikuje poprawność danych.
5. System informuje o pomyślnym wystawieniu produktu na aukcję.

**Scenariusze alternatywne:** 

4.A. Podano niepoprawne lub niekompletne dane produktu.
* 4.A.1. System informuje o błędnie podanych danych.
* 4.A.2. Przejdź do kroku 2.

---

<a id="uc2"></a>
### UC2: Złożenie oferty na produkt

**Aktorzy:** [Kupujący](#ac2)

**Scenariusz główny:**
1. [Kupujący](#ac2) przegląda dostępne aukcje.
2. [Kupujący](#ac2) wybiera aukcję i zgłasza chęc złożenia oferty.
3. System prosi o podanie kwoty oferty.
4. [Kupujący](#ac2) podaje kwotę oferty.
5. System weryfikuje ofertę zgodnie z [BR1](#br1).
6. System informuje o pomyślnym złożeniu oferty.

**Scenariusze alternatywne:** 

5.A. Oferta nie spełnia wymagań [BR1](#br1).
* 5.A.1. System informuje o błędnej ofercie.
* 5.A.2 Przejdź do kroku 3.

---

<a id="uc3"></a>
### UC3: Opłacenie wygranej aukcji.

**Aktorzy:** [Kupujący](#ac2)

**Scenariusz główny:**
1. System powiadamia [Kupującego](#ac2) o wygraniu aukcji.
2. [Kupujący](#ac2) potwierdza chęć opłacenia aukcji.
3. System prosi o dane płatności.
4. [Kupujący](#ac2) podaje dane płatności.
5. System przetwarza płatność.
6. System informuje o pomyślnej płatności.

**Scenariusze alternatywne:** 

6.A. Płatność nie powiodła się.
* 6.A.1. System informuje o błędzie płatności.
* 6.A.2 Przejdź do kroku 3.

---

<a id="uc4"></a>
### UC4: Potwierdzenie przekazania produktu

**Aktorzy:** [Sprzedający](#ac1)

**Scenariusz główny:**
1. System powiadamia [Sprzedającego](#ac1) o dokonanej płatności przez [Kupującego](#ac2).
2. [Sprzedający](#ac1) potwierdza przygotowanie produktu do dostawy.
3. System prosi o podanie szczegółów dostawy.
4. [Sprzedający](#ac1) podaje szczegóły dostawy.
5. System rejestruje dostawę i informuje o niej [Kupującego](#ac2).

**Scenariusze alternatywne:** 

Brak szczenariuszy alternatywnych.

---

<a id="uc5"></a>
### UC5: Przeglądanie wyników aukcji

**Aktorzy:** [Kupujący](#ac2)

**Scenariusz główny:**
1. [Kupujący](#ac2) przegląda zakończone aukcje.
2. System wyświetla wyniki aukcji.
3. [Kupujący](#ac2) kończy przeglądanie wyników.


**Scenariusze alternatywne:** 

Brak scenariuszy alternatywnych.

---

<a id="uc6"></a>
### UC6: Anulowanie aukcji

**Aktorzy:** [Sprzedający](#ac1)

**Scenariusz główny:**
 Brak scenariusza głównego.


**Scenariusze alternatywne:** 

Brak scenariuszy alternatywnych.

---

<a id="uc7"></a>
### UC7: Przeglądanie listy aukcji

**Aktorzy:** [Kupujący](#ac2)

**Scenariusz główny:**
Brak scenariusza głównego.


**Scenariusze alternatywne:** 

Brak scenariuszy alternatywnych.

---

<a id="uc8"></a>
### UC8: Rejestracja w systemie

**Aktorzy:** [Sprzedający](#ac1), [Kupujący](#ac2)

**Scenariusz główny:**
Brak scenariusza głównego.


**Scenariusze alternatywne:** 

Brak scenariuszy alternatywnych.

---

## Obiewkty biznesowe (inaczje obiekty dziedzinowe lub informatycjne)

### BO1: Aukcja

Aukcja jest formą zawierania transakcji kupna-sprzedaży, w której Sprzedający określa cenę wywoławczą produktu, natomiast Kupujący mogą oferować własną ofertę zakupu każdorazowo proponując kwotę wyższą od aktualnie oferowanej kwoty. Aukcja kończy się po upływie określonego czasu. Jeśli złożona została co najmniej jedna oferta zakupy produkt nabywa ten Kupujący, który zaproponował najwyższą kwotę. 

### BO2: Produkt

Fizyczny lub cyfrowy obiekt, który ma zostać sprzedany w ramach aukcji.

## Reguły biznesowe

<a id="br1"></a>
### BR1: Złożenie oferty

Złożenie oferty wymaga zaproponowania kwoty wyższej niż aktualnie oferowana o minimum 1,00 PLN.


<a id="br2"></a>
### BR2: Rozstrzygnięcie aukcji

Aukcję wygrywa ten z [Kupujący](#ac2)ch, który w momencie jej zakończenia (upłynięcia czasu) złożył najwyższą ofertę.

## Macierz CRUDL


| Przypadek użycia                                  | Aukcja | Produkt | ... |
| ------------------------------------------------- | ------ | ------- | --- |
| UC1: Wystawienia produktu na aukcję               |    C   |    C    | ... |
| UC2: Złożenie oferty na produkt                   |    R   |    R    | ... |
| UC3: Opłacenie wygranej aukcji                    |    R   |    R    | ... |
| UC4: Potwierdzenie przekazania produktu           |    U   |    R    | ... |
| UC5: Przeglądanie wyników aukcji                  |    R   |    R    | ... |
| UC6: Anulowanie aukcji                            |    D   |         | ... |
| UC7: Przeglądanie listy aukcji                    |    L   |    L    | ... |
| UC8: Rejestracja w systemie                       |        |         | ... |

