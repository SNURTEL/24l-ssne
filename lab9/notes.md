- VAE - enkoder o przestrzeni ukrytej N-wymiarowej koduje N średnich i N odchyleń standardowych
- Jakbyśmy do przestrzeni ukrytej dodali wektor one-hot kodujący klasę, możemy przy generacji wskazać którą klasę chcemy dostać
    - wtedy przestrzeń ukryta koduje tylko cechy wspólne - przykłady są kompletnie pomieszane
- Problem z VAE - dziury w przestrzeni
- konieczne do działanai - reparametrization trick i relularyzacja (KLD) minibatcha (?) aby sumował się do rozkładu standardowego

---------

- GAN
- Generator - wypluwa przykłady na podstawie wektrora wejściowego
- Dyskryminator - po prostu klasyfikator, zwraca 0 lub 1

- Dwa optymalizatory - osobny na generator i dyskryminator
- Dyskryminator wstępnie uczymy

- Uczenie dyskryminatora 
  - Najpierw liczymy błąd na prawdziwych przykładach
  - Potem na przykładach wyplutych przez genrator
  - Gradient liczymy na submie obu

- Uczenie generatora
  - Te same wygenerowane przykłady przepuszczamy przez dyskryminator
  - Liczymy błąd (oczekujemy że klasa będzie 1!)

- *mode(l) collapse* - generator uczy się jednego przykładu (np jednej klasy) i cały czas ją zwraca

- GAN warunkowany klasą
  - Na wejście generatora poza szumem wchodzi klasa w one-hot
  - Do dyskrymiantora tak samo
  - Zapobiega zapadnięciu się modelu tylko częściowo - model może po prostu nauczyć się jednego perfekcyjnego przykładu dla każdej klasy


- Ewaluacja modeli genereatywnych
  - Bierzemy jakiś klasyfikator z zewnątrz i używamy go do oceny generowanych przykładów - nie musi działać dobrze, GAN może zwrócić inny rozkład 
  - Fretchet distance - porównujemy rozkłady przykładów wygenerowanych i faktycznych