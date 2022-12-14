# Tumour Detection App
Projekt wykonany w ramach przedmiotu Wprowadzenie do aplikacji i rozwiązań opartych o Sztuczną Inteligencję i Microsoft Azure. 

# Opis 
Niewątpliwie każdy wie jak ważna dziedziną jest medycyna. Wspieranie jej stałego rozwoju to troska o zdrowie każdego człowieka. Z tą myślą podjęliśmy próbę 
storzenia apliacjkacji pomocnej wykrywającej guzy. Aplikacja ma usprawnić ten proces oraz zapewniać jego niezawodność.

# Autorzy: 
* [Lidia Łachman](https://github.com/LidiaLachman)
* [Piotr Klepacki](https://github.com/Klepackp)
* [Mateusz Smoliński](https://github.com/Norsien)

# Architektura aplikacji w Azure

## Diagram przypadków użycia

![Image](images/use_case_diagram.png)

Użytkownik wchodzi na stronę internetową. Następnie wgrywa obraz, który podlega klasyfikacji. Wynik klasyfikacji zwrócony zostaje na stronie internetowej w postaci 
stwierdzenia nowotowru lub jego braku.

## Diagram architektury serwisów Azure

![Image](images/architecture_diagram.png)

## Wybrany stos technologiczny

### Azure Machine Learning 
Praca z Azure Machine Learning była prowadzona przy pomocy portalu Azure ML studio oraz Azure python sdk.
Bazę zdjęć nowotworów używaną w aplikacji można znaleźć na stronie: https://www.kaggle.com/datasets/navoneel/brain-mri-images-for-brain-tumor-detection .



### Strona internetowa
Strona internetowa powstała z wykorzystaniem frameworka Flask - implementacja wykonana została w języku Python. Pełen kod do implementacji znajduje się
w tym repozytorium pod nazwą tumor_detection_web_app. Podjęta została próba uruchomienia aplikacji w Web App. Z powodu braku uprawnień nie udało utworzyć Web App
w zasobach grupy. Została postawiona na podstawie forka kodu z githuba na innej subskrypcji. Jest dostęna pod adresem https://python-webapp-tumor-app-2.azurewebsites.net/.

### Azure Active Directory
Przyznanie ról pozostałym członkom zespołu i autoryzacja dostępu do utworzonego endpointa.

### Blob storage
Przechowywanie plików potrzebnych do nauczenia modelu oraz wszystkich plików związanych z działaniem backendu (Azure Machine Learning).

# Schemat działania rozwiązania
Użytkownik przechodzi do serwisu webowego hostowanego na Azure: https://python-webapp-tumor-app-2.azurewebsites.net/
![Image](images/webpage.png)
Za pomocą przycisku przeglądaj wybiera zdjęcie zapisane na swoim urządzeniu. Natępnie, po kliknięciu przycisku Submit zostaje ono przesłane w zakodowanej do json postaci na endpoint udostępniany przez wytrenowny model ML. Serwis otrzymuje przewidzony resultat i wyświetla go użytkownikowi na ekranie.


