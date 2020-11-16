# www
Landing Page WebAplikacja

## Cel projektu

Zamysł WebAplikacji polega na tworzeniu aplikacji:
+ prostych w budowie
+ z wykorzystaniem już raz napisanym kodzie
+ a przy okazji tworzenie ogromnej bazy mediów do ponownego użycia w kolejnych projektach

## Zasada działania

Każda WebAplikacji posiada definicję, która określa użyte w niej moduły
definicja jest napisana w formacie JSON

Definicja jest budowana w prostym standardzie JSON:

    {[
      "XPATH" : "URL",
      ....
    ]}
    
Za parsowanie tej deifinicji odpowiedzialna jest bibliotek: jLoads.com

Każda definicja odnosi się do biblioteki mediów: jBodys.com
Dane prywatne są zapisywane na zewnętrznych bazach danych/usługach, również tych definiowanych przez jLoads

Uruchamianie Kodu po stronie backendu są odpowiedzialne skrypty jRuns umieszone na serwerze
do którego odnosi się definicja.

Skrypty jRuns można uruchomić na serwerze lokalnym, zdalnie, lub obu, aby komunikowały się ze sobą i dbały o automatyzację procesów


## przykład
zapisz tę stronę na serwerze porpzez ftp

moduł zapisywania poprzez FTP:

      {            
        "ftp": {        
            "/var/www": "https://github.com/webaplikacja/www" ,
        }
      }
      
      
      {            
        "gitclone": {        
            "/var/www" : "https://github.com/webaplikacja/www",
        }
      }      
