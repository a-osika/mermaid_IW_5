``` mermaid
graph LR
  subgraph SYS["System rezerwacji sal"]
    UC1["Przejrzyj dostepnosc sal"]
    UC2["Zarezerwuj sale"]
    UC3["Anuluj rezerwacje"]
    UC4["Zatwierdz rezerwacje"]
    UC5["Odrzuc rezerwacje"]
    UC6["Zaloguj sie"]
    UC7["Zarzadzaj salami"]
    UC8["Generuj raport"]
    UC9["Zglos usterke"]
    UC10["Wyslij powiadomienie"]
    UC11["Zarzadzaj kontami"]
    UC12["Sprawdz harmonogram"]
  end
 
  N["Niezalogowany"]   --> UC12
  P["Pracownik"]       --> UC1 & UC2 & UC3 & UC9
  M["Menedzer"]        --> UC4 & UC5 & UC8
  A["Administrator"]   --> UC7 & UC11
  E["Sys. e-mail"]     --> UC10
 
  M -->|generalizacja| P
 
  UC2 -->|include| UC6
  UC3 -->|include| UC6
  UC4 -->|include| UC6
  UC5 -->|include| UC6
  UC2 -.->|extend| UC10
  UC4 -.->|extend| UC10
  UC5 -.->|extend| UC10
  UC3 -.->|extend| UC10
```