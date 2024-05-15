- Najbardziej basic sieć rekurencyjna:
  - Warstwy "wspólne" +
  - Dwie warstwy wyjściowe - jedna wyrzuca wyjście siecim druga stan
  - `forward` przyjmuje `x` i `state`, zwraca `x` i następny `state`
  - Training loop (nieoptymalny)
    - Bierzemy wartość z sekwencji
    - Każemy sieci przewidzieć następną
    - Loss na podstawie wyjścia, stan zapisujemy

- Implementacja RNN w torchu
  - nn.RNN
  - input size - rozmiar jedengo elementu sekwencji (dla wartości skalarnych - (1,))
  - hidden size wiadomo
  - batch_first=False - defaultowo w danych przyjmowanych przez RNN rozmiar sekwencji jest pierwszym wymiarem, rozmiar batcha jest drugi
  - output, hn = rnn(x, h0)
    - Output - stan ukryty w kolejnych chwilach czasu
    - hn - ostatni stan ukryty
    - Stan ukryty przepuszczamy dodatkowo przez sieć gęstą
    - Loss tylko na podstawie ostantiego wyjścia

- LSTM
  - nn.LSTM, api +/- jak w rekurencyjnej (główna różnica - mamy dwa stany zamiast jednego, stan ukryty i stan komórki (ta sama wymiarowość)
  - opakowanie w regresor tak samo jak w RNN (ofc zamiast `hidden` mamy tuplę dwóch stanów)

- Sequence to sequence
  - proj_size w LSTM - dodatkowa warstwa gęsta która przetwarza stan ukryty w dodatkowe wyjście o zadanym wymiarze
  - W ten sposób z każdego "obrotu" bloku LSTM dostajemy dodatkowe wyjście
  - Jeśli rozmiar okna jest mniejszy niż dłiugość docelowej sekwencji, inicjalizować stan raz na całą sekwencję, nie raz na okno

- Klasyfikacja szeregów czasowych
  - Zostawione jako ćwiczenie dla czytelnika

- Dane o różnej długości
  - Utrzymanie stałego rozmiaru danych - dodatnie paddingu
  - `collate_fn` w dataloaderze - funkcja przetwarzająca batche przed zwróceniem przez dataloader (może np dodawać padding)
  - Implementacja do skopiowania z notebooka
    - `batch_first` na true w `pad_sequence` - dataloader defaultowo ma zwracać batch na pierwszy wymiarze
  - maska - liczymy loss tylko na tych wartościach, które nie są paddingiem (dlatego do paddingu trzeba wykrorzystywać wartości, których nie ma w datasecieSS)
  - packed sequence - podobno szybsze
