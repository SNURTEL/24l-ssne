Wakacje są blisko, wszyscy już myślą o wyjazdach - ale jak tu dobrze ocenić hotel, żeby jak najbardziej się nim cieszyć?

Zadanie polega na stworzeniu modelu, który będzie klasyfikował liczbę gwiazdek przyznanych hotelowi (rating, klasa = liczba_gwiazdek - 1) na podstawie recenzji, jaką otrzymał (review).
Wszelkie chwyty dozwolone :) Mogą Państwo przewidywać klasy w oparciu o klasyczną metodę bag of words, inne metody reprezentacji dokumentów (np. TF-IDF), korzystać z embeddingów, gotowych modeli językowych itd. Do dyspozycji mają Państwo dane treningowe, oczekuję od Państwa pliku csv z wygenerowanymi predykcjami.
Proszę zwrócić uwagę na fakt, że jest to problem klasyfikacji wieloklasowej z mocno niezbalansowanym zbiorem danych!
Proszę także Państwa o przetestowanie kilku (co najmniej trzech) podejść do klasyfikacji - mogą (ale nie muszą!) być to gotowe modele, najlepiej o różnych architekturach.

Bardzo proszę, żeby zwrócili mi Państwo archiwum zip (wystarczy jedna osoba z zespołu), proszę też o zastosowanie się do instrukcji:
- Archiwum i wszystkie pliki powinny być nazwane {poniedzialek/piatek}_nazwisko1_nazwisko2
- W archiwum proszę (bez zbędnych podfolderów!) umieścić pliki ze swoim kodem i testowe predykcje nazwane zgodnie z sekwencją  {poniedzialek/piatek}_nazwisko1_nazwisko2.csv
- Testowe predykcje powinny mieć kolejność zgodną z kolejnością sekwencji, do których się odnoszą w zbiorze testowym. Plik csv nie powinien mieć nagłówka ani indeksów.

Proszę o dokładne dokumentowanie wykonanych eksperymentów!

Uwaga: proszę dokładnie sprawdzić swoje rozwiązania i predykcje. W związku z końcem semestru, nie będzie możliwości dosyłania poprawek.