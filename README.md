# RSC-Project1
Repository made for Project1 in Recommender Systems Class

Celem projektu było stworzenie systemu rekomendacyjnego, który dla danych dotyczących rezerwacji hotelowych byłby skuteczniejszy od rekomendera Amazona, tzn. lepiej przewidywałby prawdopodobieństwo interakcji pomiędzy użytkownikiem a przedmiotem (usługą hotelową).
Pierwszym zadaniem było wykonanie wstępnej obróbki danych. W jej ramach udało się:
- napisać metodę odfiltrowującą klientów będących firmami (filter_out_company_clients)
- napisać metodę odfiltrowującą rezerwacje dłuższe niż 3 tygodnie (filter_out_long_stays)
- napisać metodę odflitrowującą dane z opłatą za pobyt mniejszą niż 50 (filter_out_low_prices)
- napisać metodę wyliczającą długość rezerwacji na podstawie istniejących kolumn i zapisującą ją w nowej kolumnie (add_length_of_stay)
- napisać metodę wyliczającą czas od dokonania rezerwacji do daty rozpoczęcia pobytu, zapisującą go w nowej kolumnie (add_book_to_arrival)
- napisać metodę zwracającą informację, czy w czasie planowanego pobytu wypada weekend definiowany jako piątek lub sobota (add_weekend_stay)
- napisać metodę obliczającą cenę za noc jako iloraz opłaty za pobyt przez iloczyn długości pobytu i liczby pokoi (add_night_price)
- napisać metodę wyliczającą całkowitą liczbę gości w ramach rezerwacji (sum_npeople)
- napisać metodę dzielącą dostępne pokoje na kategorie (buckety) w zależności od średniej ceny za noc

Nie udało się niestety napisać do końca poprawnie działającej metody agregującej rezerwacje grupowe. Jej poszczególne składowe wydają się działać poprawnie, jednak na etapie ponownego scalania danych zagregowanych według różnych kryteriów pojawia się problem. Powstały DataFrame wygląda poprawnie, jednak zarówno opisane powyżej metody, jak i część metod predefiniowanych nie działają, przyjmując go jako argument. Z tego względu, nie udało się do końca obrobić danych, zaliczyć wszystkich assertów i stworzyć działającego rekomendera.
W pliku "project_1_data_preparation" zakomentowana została przy przetwarzaniu danych linijka wywołująca agregację dla rezerwacji grupowych oraz te asserty, które przez jej brak nie były spełnione. Ma to na celu pokazanie, że pozostałe metody działają poprawnie. Jednocześnie, dodana została prezentacja DataFrame'a powstałego w wyniku zastosowania metody agregującej.

W pliku głównym "project_1_recommender_and_evaluation" wykonano następujące działania:
- podzadanie z dodaniem negatywnych interakcji

Zasadnicze składowe projektu:
Dwa pliki typu Jupyter Notebook:
- project_1_data_preparation.ipynb,
- project_1_recommender_and_evaluation.ipynb,

Pliki do wstępnego przetworzenia danych:
- data_preprocessing/data_preprocessing_toolkit.py,
- data_preprocessing/dataset_specification.py.py,
- data_preprocessing/people_identifier.py.py,

Plik z danymi:
data/hotel_data/hotel_data_original.csv.

Dodatkowo załączone są również pliki zapożyczone z repozytorium zajęć z systemów rekomendacyjnych oraz wersje HTML obydwu notebooków.

Wymagane pakiety (instalowane poprzez wpisanie w wierszu poleceń "pip install <nazwa_pakietu>"):
- numpy
- pandas
- matplotlib.pyplot
- seaborn
- notebook

Aby uruchomić projekt, w wierszu poleceń, w folderze, w którym znajduje się projekt, wpisujemy komendę "jupyter notebook". Jupyter uruchomi się w przeglądarce i będziemy mieli możliwość otwarcia interesującego nas pliku.
