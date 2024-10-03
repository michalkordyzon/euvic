# RAG4BPs is a enablement repository with simple watsonx RAG code and other scenarios.

<img width="513" alt="image" src="https://media.github.ibm.com/user/146934/files/0103b15a-326a-4a64-bcfc-46ab5c43c499">

instrukcja założenia projektu watsonx


1-Tworzymy projekt
docs:
https://dataplatform.cloud.ibm.com/docs/content/wsj/getting-started/projects.html?context=wx&audience=wdp

Początek: Home w watsonx
-watsonx -> hamburger -> Projects -> view all projects -> new project
-wpisujemy nazwę projektu
-Inicjujemy lub podłączamy instancję Cloud Object Storage

2-W projekcie inicjujemy lub podłączamy instancję Watson Machine Learning. Instancja WML to komputer/zasób,  gdzie będzie odbywać się nasze przetwarzanie: 
-inferencja transformeów
-wykonanie jupiter notebooków, 
-wykonanie algorytmów machine learning 

-watsonx -> hamburger -> Projects -> view all projects -> nasz_projekt -> Manage -> Services and Integration -> IBM Services
-Associate Service
-powinien być wyświetlony jeden serwis,  zaznaczamy go (nazwa np. itzml-270005ceaj-aj1pqsz5) 

3-Sprawdzenie w watsonx GUI, czy działa inferencja na foundation models.
watsonx -> hamburger
-watsonx -> hamburger -> Home -> Open Prompt Lab -> wpisujemy pytanie 
-powinna wygenerować się odpowiedź


4-Utworzenie api
Zrobiłem dla Was mp4 (niskiej jakości, żeby nie zaśmiecać planety)
https://ibm.box.com/s/t3em5ggufudm7gk97iu7vmg2z20p0ire


-watsonx -> hamburger -> IBM Cloud(lewy, dolny róg ekranu) -
przeszliśmy z wastonx do głównego dashboard'u konta IBM Cloud
-Manage -> Access(IAM) -> Api Keys -> Create 
-wpisujemy nazwę tworzonego klucza api 
-Download


5-utworzenie pliku .env
docs:
https://dataplatform.cloud.ibm.com/docs/content/wsj/analyze-data/fm-credentials.html?context=wx&audience=wdp

przykład pliku .env:
```
GENAI_KEY=XXXXXX
GENAI_ENDPOINT=https://workbench-api.res.ibm.com/v1
PROJECT_ID=XXXXX
```

GENAI_KEY to utworzony w kroku 4 klucz.
GENAI_ENDPOINT jest związany z regionem chmury, w którym znajduje się nasza instancja Watson Machine Learning. Jak to sprawdzić: dashboard ibm cloud -> hamburger -> resource list -> AI / Machine Learning -> instancja Watson Machine Learning -> Details
widzimy Location: Dallas (wpisujemy w .env us-south), London (wpisujemy eu-gb), Frankfurt (eu-de).

GENAI_ENDPOINT=https://{region}.ml.cloud.ibm.com
region= us-south; eu-gb; eu-de

