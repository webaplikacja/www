# www
Landing Page WebAplikacja

## Cel projektu

Zamysł WebAplikacji polega na tworzeniu aplikacji:
+ prostych w budowie
+ z wykorzystaniem już raz napisanego kodu
+ a przy okazji tworzenie ogromnej bazy mediów do ponownego użycia w kolejnych projektach
+ dane są zapisywane w zewnętrznych serwisach dostępnych po autoryzacji użytkownika

## Webaplikacja to implementacja 3 narzędzi:
+ jLoads do ładowania aplikacji do przeglądarki, działa po stronie klienta i korzysta z jRuns oraz jBodys
+ jRuns do ładowania powyższego kodu na serwer
+ jBodys do przechowywania aplikacji na zdalnych serwerach do wielokrotnego użycia w modularyzowanych aplikacjach w oparciu o jLoads


## Zasada działania

Każda WebAplikacji posiada definicję, która określa użyte w niej moduły
definicja jest napisana w formacie JSON

Definicja jest budowana w prostym standardzie JSON:
Adres docelowy  <-  zasób

    {[
      "XPATH" : "URL/STRING/JSON",
      ....
    ]}
    
Za parsowanie tej deifinicji odpowiedzialna jest bibliotek: jLoads.com

Każda definicja odnosi się do biblioteki mediów: jBodys.com
Dane prywatne są zapisywane na zewnętrznych bazach danych/usługach, również tych definiowanych przez jLoads

Uruchamianie Kodu po stronie backendu są odpowiedzialne skrypty jRuns umieszone na serwerze
do którego odnosi się definicja.

Skrypty jRuns można uruchomić na serwerze lokalnym, zdalnie, lub obu, aby komunikowały się ze sobą i dbały o automatyzację procesów


## przykład backend

zapisz tę stronę na serwerze poprzez ftp



      {            
        "ftp": {        
            "/var/www": "https://github.com/webaplikacja/www" ,
        }
      }
      

moduł zapisywania poprzez git clone:

      {            
        "git_clone": {        
            "/var/www" : "https://github.com/webaplikacja/www",
        }
      }      
      

http, input data: json

      {            
        "http_post_json": {        
            "https://github.com/index.php" : {
                "name" "Tom",
            }
        }
      }       
      
 
http with post data from response

      {            
        "http_post_response": {        
            "https://github.com/index.php": "https://translate.com/output?something"
        }
      }   


http with file as parameter

      {            
        "http_file_response": {        
            "https://github.com/index.php": "https://file.com/type?mimetype=png"
        }
      }   


http with file as parameter

      {            
        "http_file_response_json": {        
            "https://github.com/index.php": {
                "https://file.com/type": {
                    "mimetype": "png"
                }
            }
         }
      }  
