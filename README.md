# Lucrarea de laborator nr. 3. Dezvoltarea unei teme WordPress simple

## Scopul lucrării

Să înveți cum să creezi o temă WordPress personalizată, să înțelegi structura sa minimă și principiile de funcționare ale șabloanelor.

## Condiții

###  Pasul 1. Pregătirea mediului

1.În instalarea locală WordPress, accesează folderul wp-content/themes

<img width="412" height="37" alt="image" src="https://github.com/user-attachments/assets/8ae8fc95-d397-4c44-b43b-a307205bba22" />

2.Creează un director pentru tema ta, de exemplu Lab3-theme

<img width="128" height="32" alt="image" src="https://github.com/user-attachments/assets/bd782f4a-38f6-42d1-9562-3cde461aa843" />

3.Activează modul de depanare în wp-config.php, adăugând define('WP_DEBUG', true);

<img width="705" height="252" alt="image" src="https://github.com/user-attachments/assets/721a6fae-cd2f-43da-9718-0ab9fb02bbea" />

### Pasul 2. Crearea fișierelor obligatorii ale temei

1.În folderul temei, creează fișierul style.css cu metadatele temei.

2.După metadate, poți adăuga reguli CSS de bază.

<img width="702" height="237" alt="image" src="https://github.com/user-attachments/assets/e0db2137-577a-41ba-9eb0-fc30bcd68b40" />

3.Creează fișierul index.php – șablonul principal al temei. Pentru început, adaugă o structură HTML de bază.

<img width="667" height="512" alt="image" src="https://github.com/user-attachments/assets/557a415e-86ca-4e43-a2ae-a9177c58d7d1" />

### Pasul 3. Componente comune ale șabloanelor

### Pasul 3. Setările inițiale ale site-ului

1.Creează fișierul header.php și mută acolo codul antetului site-ului (până la începutul conținutului principal).

<img width="974" height="293" alt="image" src="https://github.com/user-attachments/assets/379be50f-67b2-4632-ad8b-b979df2381ef" />

2.Creează fișierul footer.php și mută acolo codul subsolului site-ului (după conținutul principal)

<img width="1003" height="210" alt="image" src="https://github.com/user-attachments/assets/cb23884c-0582-4504-9579-5b87f78a275e" />

3.În index.php, include header.php și footer.php folosind funcțiile get_header() și get_footer()

4.Pe pagina principală, afișează o listă cu ultimele 5 postări folosind bucla WordPress.

<img width="1039" height="426" alt="image" src="https://github.com/user-attachments/assets/714daaf8-72a8-4255-b7e5-0e5ab0673c71" />

### Pasul 4. Fișierul de funcții

1.Creează fișierul functions.php în directorul temei.

2.În functions.php, adaugă o funcție pentru încărcarea stilurilor temei folosind wp_enqueue_style().

<img width="672" height="169" alt="image" src="https://github.com/user-attachments/assets/b4ef120d-df68-42f6-baf1-86f8b19e159d" />

### Pasul 5. Șabloane suplimentare

1.Creează fișierul single.php pentru afișarea unei postări individuale.

<img width="1194" height="349" alt="image" src="https://github.com/user-attachments/assets/8a7dd7aa-e55b-422e-a4a9-bebadd449211" />

2.Creează fișierul page.php pentru afișarea paginilor.

<img width="775" height="223" alt="image" src="https://github.com/user-attachments/assets/5876eff0-073c-4306-ac09-0ea8e73708f4" />

3.Creează fișierul sidebar.php pentru bara laterală și include-l în șabloanele relevante cu get_sidebar().

<img width="523" height="62" alt="image" src="https://github.com/user-attachments/assets/6172095b-daae-43f6-9c61-4f81e3e0ad87" />

4.Creează fișierul comments.php pentru afișarea comentariilor și include-l în single.php și page.php.

<img width="505" height="51" alt="image" src="https://github.com/user-attachments/assets/0db2d643-ea4b-4624-9677-af22b2e781d8" />

5.Creează fișierul archive.php pentru afișarea arhivelor postărilor.

<img width="985" height="910" alt="image" src="https://github.com/user-attachments/assets/c4c59c1c-1bbb-4026-bd83-f5618bd0eed3" />

### Pasul 6. Stilizarea temei

Adaugă stiluri pentru elementele principale ale temei (antet, subsol, conținut, bara laterală).

<img width="523" height="866" alt="image" src="https://github.com/user-attachments/assets/29f2d003-9d4a-4d07-80ef-b2f75b86227e" />

<img width="689" height="897" alt="image" src="https://github.com/user-attachments/assets/61c1dc60-5977-406b-a2f2-f2c2077bc236" />

<img width="373" height="910" alt="image" src="https://github.com/user-attachments/assets/6b3ed701-9607-4a0e-8ec3-22014cb00958" />

### Pasul 7. Captura de ecran a temei

Adaugă în folderul temei fișierul screenshot.png – o imagine de previzualizare a temei (dimensiune 1200x900px).

### Pasul 8. Activarea temei

1.În panoul de administrare WordPress, accesează secțiunea Appearance → Themes.

2.Găsește tema ta și activeaz-o.

<img width="386" height="336" alt="image" src="https://github.com/user-attachments/assets/a663c102-a55e-4fd2-965a-ea732dd4b55c" />

3.Verifică modul în care site-ul este afișat cu tema ta.

<img width="1559" height="590" alt="image" src="https://github.com/user-attachments/assets/42e643be-0bf2-4ef0-a7a7-589c9b7c28c7" />

## Întrebări de control

1.Care sunt cele două fișiere obligatorii pentru orice temă WordPress?

Cele două fișiere obligatorii pentru orice temă sunt style.css, care conține metadatele și designul, și index.php, care servește drept șablon de rezervă pentru afișarea conținutului.

2.Cum se includ părțile comune ale șabloanelor (header, footer, sidebar)?

Părțile comune ale șabloanelor se includ folosind funcțiile native get_header(), get_footer() și get_sidebar(), care apelează automat fișierele corespunzătoare din folderul temei.

3.Care este diferența dintre index.php, single.php și page.php?

Diferența dintre cele trei șabloane principale este destul de clară: index.php este fișierul universal care afișează de obicei lista de postări, single.php 

se ocupă exclusiv de afișarea unui singur articol de blog, iar page.php este dedicat paginilor statice precum pagina de contact sau despre noi.

4.Care este rolul fișierului functions.php într-o temă?

Fișierul functions.php acționează ca un creier al temei, având rolul de a activa funcționalități precum imaginile reprezentative sau meniurile și de a încărca corect 

fișierele CSS și JavaScript prin sistemul de cozi al WordPress-ului.
