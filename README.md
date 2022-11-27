# Tumour Detection App
Projekt wykonany w ramach przedmiotu Wprowadzenie do aplikacji i rozwiązań opartych o Sztuczną Inteligencję i Microsoft Azure. 

# Opis 
Niewątpliwie każdy wie jak ważna dziedziną jest medycyna. Wspieranie jej stałego rozwoju to troska o zdrowie każdego człowieka. Z tą myślą podjęliśmy próbę 
storzenia apliacjkacji pomocnej wykrywającej guzy. Aplikacja ma usprawnić ten proces oraz zapewniać jego niezawodność.

# Autorzy: 
* Lidia Łachman
* Piotr Klepacki
* Mateusz Smoliński

# Architektura aplikacji w Azure

## Diagram przypadków użycia

![Image](images/use_case_diagram.png)

Użytkownik wchodzi na stronę internetową. Następnie wgrywa obraz, który podlega klasyfikacji. Wynik klasyfikacji zwrócony zostaje na stronie internetowej w postaci 
stwierdzenia nowotowru lub jego braku.

## Wybrany stos technologiczny

### Azure Machine Learning 
Praca z Azure Machine Learning była prowadzona przy pomocy portalu Azure ML studio oraz Azure python sdk.
Bazę zdjęć nowotworów używaną w aplikacji można znaleźć na stronie: https://www.kaggle.com/datasets/navoneel/brain-mri-images-for-brain-tumor-detection .



### Strona internetowa
Strona internetowa powstała z wykorzystaniem frameworka Flask - implementacja wykonana została w języku Python. Pełen kod do implementacji znajduje się
w tym repozytorium pod nazwą tumor_detection_web_app. Podjęta została próba uruchomienia aplikacji w Web App. Z powodu braku uprawnień nie udało utworzyć Web App
w zasobach grupy. Z tego względu przetestowano podejście lokalne zakończone powodzeniem. Do podejścia lokalnego wykorzystano rozszerzenie Azure w Visual Studio oraz 
połączenie z Github. Istnieje również możliwość uruchomienia aplikacji na utworzonej wcześcniej maszynei wirtualnej. Z racji braku możliwości utworzenia jakichkolwiek zasobów 
nie zostało to przetestowane.

### Azure Active Directory
Przyznanie ról pozostałym członkom zespołu i autoryzacja dostępu do utworzonego endpointa.

### Blob storage
Przechowywanie plików potrzebnych do nauczenia modelu oraz wszystkich plików związanych z działaniem backendu (Azure Machine Learning).

# Schemat działania rozwiązania

