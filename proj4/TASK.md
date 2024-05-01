Tym razem zadanie będzie polegało na stworzeniu modelu generatywnego który generował będzie nowe obrazki przedstawiające znaki drogowe. Do wyboru mają Państwo dowolny model generatywny (VAE, GAN, GLOW, VAEGAN, czy modele dyfuzyjne. W przypadku tych ostatnich polecam zapoznanie się z takim notebookiem: https://huggingface.co/learn/diffusion-course/en/unit1/3, jeżeli będą Państwo chętni to możemy wspólnie przejść przez niego w ramach laborek konsultacyjnych.

Zbiór danych udostępniłem Państwu przez onedrive (trafic_32.zip) i ma taką samą strukturę jak poprzednio (zgodną z domyślnymi ustawieniami ImageFolderu). Znaki podzielone są na klasy, które jak najbardziej mogą Państwo wykorzystywać do generowania próbek. Tym razem zamiast predykcji proszę o zwrócenie mi kodu z implementacją eksperymentów i przykładowe 1000 próbek wygenerowanych za pomocą Państwa metody.
Bardzo proszę żeby jak zwykle zwracali mi Państwo archiwum zip, jak zwykle proszę też o zastosowanie się do instrukcji:
- Archiwum powinno być nazwane jak ostatnio poniedzialek/piatek_nazwisko1_nazwisko2.zip (lub nazwa drużyny)
- W archiwum proszę bez zbędnych podfolderów umieścić pliki ze swoim kodem i wygenerowane obrazki nazwane odpowiednio poniedzialek_nazwisko1_nazwisko2.pt (lub nazwa drużyny)
- Wygenerowane obrazki, proszę zapisywać po prostu w formie torchowego tensora (na cpu, po detach, czyli np. wykonując komendę torch.save(generated_imgs.cpu().detach(),"poniedzialek_nazwisko1_nazwisko2.pt") ). Tensor zgodnie z konwencją powinien mieć wymiary [1000, 3, 32, 32]

Ewaluacja:
- Wygenerowane obrazki porównywał będę do zbioru testowego za pomocą metryki Frechet Inception Distance o której wspominałem na ćwiczeniach. Jeżeli chcieliby Państwo z niej skorzystać do ewaluacji swoich modeli, to odsyłam do repozytorium z wygodną implementacją: https://github.com/mseitzer/pytorch-fid
- W zbiorze testowym obrazki mają ten sam rozkład klas co w treningowym
- Proszę pamiętać o denormalizacji próbek :)