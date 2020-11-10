# Rozdział1

## Serwis usprawniający proces produkcyjny.

### *Serwis do wyliczania kosztów produkcji według podanych kryteriów.*



Ogólny opis z książki :

Urządzenia składają się z 1,2,3,4 modułów w zależności od typu urządzenia. Każdy moduł ma swoją z góry określoną cenę oraz ile czasu trwa jego montaż. Firma pracuje w 5 miastach w Polsce (Dowolnie wybrane) w których stawki pracownika są różne. Koszt transportu urządzenia (czy modułu?) jest różny w zależności od lokalizacji fabryki. Dodatkowe koszty to 30% sumy wyżej wymienionych kosztów. 

Moduł powinien posiadać informacje odnoście wagi elementu oraz krótki opis. 

Jednostki cena: dolar waga w kilogramach.



**Koszt = (Cena transportu + zsumowana cena modułów dla typu urządzenia + zsumowana liczba godzin montażu * koszt pracy za godzinę pracy dla danego miasta) * 130%**



Chcemy mieć możliwość dodawania, edytowania, pobierania, usuwania informacji o modułach. 

Dodatkowo zapytania odnośnie wyszukiwanych urządzeń (kombinacji powyższych) będą odkładane w bazie danych. (bezsens bo co jeżeli cena transportu lub cena godziny pracy wzrośnie lub zmaleje i zmieni się koszt? i tak trzeba na nowo obliczać i aktualizować wpis dla danego urządzenia :D ) 

**Ogólny opis Mój:**

Tworzymy aplikacje do obliczania kosztów produkcji autonomicznych czołgów bezzałogowych.

**Czołg** może składać się z 1-7 **modułów**. Każdy **moduł** ma swoją z góry określoną cenę oraz czas trwania montażu. **Fabryki** produkujące te czołgi znajdują się w 5 miastach w Polsce, w których stawki pracownika na stanowisku montażysty są różne. Dla każdego miasta, **koszt transportu** modułu z **zewnętrznej fabryki** w innym mieście (każdy moduł może pochodzić z innej fabryki w innym mieście i kraju) jest inny. Dodatkowo do kosztów produkcji dodawane jest 30% sumy wszystkich wymienionych kosztów.

**Moduł** powinien posiadać następujące informacje:

- WAGA w kilogramach
- CENA w dolarach
- OPIS 
- KOD
- ZDJĘCIE

**Czołg**:

- Nazwa
- Kod
- Opis
- Moduły

Elementy zaznaczone pogrubieniem to encje które powinny posiadać wszystkie operacje CRUD.



**IMPROWIZACJA:** Dodatkowo  system ma umożliwiać autoryzację.

Będa istniał 3 role: Administrator, Manager oraz Pracownik produkcji

Administrator ma dostęp do całego systemu. SUPERADMIN.

Manager ma dostęp do danych danej fabryki lub linii produkcyjnej. Powiedzmy, że dana fabryka ma 1-3 linii produkcyjnych, gdzie każda linia może produkować 1 rodzaj czołgu. Manager zarządza daną linią produkcyjną. Ma dostęp do danych związanych z produkcją danego czołgu na tej linii produkcyjnej, pracowników produkcji itd.

Pracownicy produkcji mają dostęp do dokumentacji technicznej związanej z montażem danego modułu do danego czołgu.

FUNKCJONALNOŚĆ DO DALSZEJ GŁĘBSZEJ ANALIZY... Teraz mi sie nie chce... pora na coś z tech lub UI/UX





Stack technologiczny:

- .NET Core Wep Api
- Angular 
- Swagger
- CQRS & DDD
- nUnit
- Code First IDK if EF or nHibernate
- Logger