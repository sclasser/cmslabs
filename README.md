# Lucrarea de laborator nr. 4. Dezvoltarea unui plugin pentru WordPress

## Scopul lucrării

Să înveți modelul extensibil de date al WordPress: crearea unui CPT (Custom Post Type), a unei taxonomii personalizate, a metadatelor cu metabox în panoul de administrare, precum și implementarea unui widget pentru afișarea datelor pe site.

## Condiții

Creează un plugin educațional numit USM Notes, care adaugă pe site o secțiune „Notițe” cu priorități și o dată de reamintire.

###  Pasul 1. Pregătirea mediului

1.În instalarea locală WordPress, accesează folderul wp-content/pugins

<img width="317" height="97" alt="image" src="https://github.com/user-attachments/assets/5f09989a-f3ad-4b4e-8dca-91289c245a48" />

2.Creează un director pentru pluginul tău, de exemplu usm-notes

<img width="228" height="124" alt="image" src="https://github.com/user-attachments/assets/e7dd9e8e-14ff-47a8-b6de-946e215fd767" />

3.Activează modul de depanare în wp-config.php, adăugând define('WP_DEBUG', true);

<img width="705" height="252" alt="image" src="https://github.com/user-attachments/assets/721a6fae-cd2f-43da-9718-0ab9fb02bbea" />

### Pasul 2. Crearea fișierelor obligatorii ale temei

1.În folderul pluginului, creează fișierul usm-notes.php

2.Adaugă în acesta metadatele pluginului (nume, descriere, versiune, autor).

<img width="595" height="182" alt="image" src="https://github.com/user-attachments/assets/31b61002-eea0-481b-9ca5-6fe632c044e4" />

3.Activează pluginul în panoul de administrare WordPress.

<img width="665" height="74" alt="image" src="https://github.com/user-attachments/assets/3d2d071d-1c03-4cf0-aeb8-c56eafbbf956" />

4.Asigură-te că pluginul este activ și că nu sunt erori.

### Pasul 3.  Înregistrarea Custom Post Type (CPT)

1.Adaugă o funcție pentru înregistrarea CPT „Notițe” (Notes) folosind register_post_type().

<img width="340" height="25" alt="image" src="https://github.com/user-attachments/assets/02ec8f3b-e904-45b2-bb6e-57ce0a8b978d" />

2.Setează parametrii CPT:

2.1 public,

2.2 suport pentru titlu, editor, autor, miniatură,

2.3 pagină de arhivă,

2.4 pictogramă în admin,

2.5 etichete (labels) pentru utilizare facilă.

<img width="522" height="198" alt="image" src="https://github.com/user-attachments/assets/b2731e36-7ae2-4996-bb0d-00d3810932e8" />

3.Înregistrează CPT-ul la inițializarea WordPress folosind hook-ul init

Adaugam deasupra la functia noastra portiunea de cod:

```
add_action('init', 'usmnote_create_post_type');
```

### Pasul 4. Înregistrarea taxonomiei personalizate

1.Adaugă o funcție pentru înregistrarea taxonomiei „Prioritate” (Priority) folosind register_taxonomy().

2.Leagă taxonomia de CPT-ul „Notițe”.

<img width="532" height="42" alt="image" src="https://github.com/user-attachments/assets/8fab5221-f1a2-453a-992d-3de594efb101" />

3.Setează parametrii taxonomiei:

3.1 ierarhică (precum categoriile),

3.2 publică,

3.3 etichete (labels) pentru utilizare facilă.

<img width="290" height="75" alt="image" src="https://github.com/user-attachments/assets/2d723f47-0b71-49e1-8cd3-e52710c70a28" />

4.Înregistrează taxonomia la inițializarea WordPress folosind hook-ul init

<img width="375" height="21" alt="image" src="https://github.com/user-attachments/assets/741cf8d7-24eb-4b25-9d39-0c54479521aa" />

### Pasul 5. Adăugarea unui metabox pentru data de reamintire

1.Creează o funcție pentru adăugarea unui metabox în editorul CPT „Notițe” folosind add_meta_box().

2.În metabox, adaugă un câmp pentru selectarea datei de reamintire (utilizează HTML5 input type="date").

3.Creează o funcție pentru salvarea valorii datei la salvarea postării folosind hook-ul save_post.

4.Asigură-te că data este salvată corect și că este afișată la editarea postării.

5.Adaugă verificarea nonce pentru securitate la salvarea metadatelor.

6.Fă câmpul pentru dată obligatoriu.

7.Adaugă validare pentru dată (de exemplu, data nu poate fi în trecut). În caz de eroare la salvare, afișează un mesaj corespunzător.

8.Afișează data de reamintire în lista postărilor CPT „Notițe” din admin.

<img width="928" height="330" alt="image" src="https://github.com/user-attachments/assets/32eff878-9d93-44d7-987b-1e31b768eabf" />

### Pasul 6. Crearea unui shortcode pentru afișarea notițelor

1.Creează o funcție pentru procesarea shortcode-ului [usm_notes priority="X" before_date="YYYY-MM-DD"], unde priority este filtrul după prioritate, iar before_date – filtrul după data de reamintire.

2.În funcție, obține și afișează lista notițelor care corespund filtrelor.

3.Înregistrează shortcode-ul folosind add_shortcode().

4.Adaugă stiluri pentru afișarea listei de notițe.

5.Gestionează cazurile în care nu există notițe pentru filtrele respective și afișează mesajul: „Nu există notițe cu parametrii specificați”.

6.Dacă priority sau before_date nu sunt specificate, shortcode-ul trebuie să afișeze toate notițele.

<img width="681" height="646" alt="image" src="https://github.com/user-attachments/assets/8e581fa8-eedc-4b17-ba7c-8686f00229dc" />

<img width="1159" height="892" alt="image" src="https://github.com/user-attachments/assets/d399fe4e-3fbc-45df-b926-98d493de870e" />

### Pasul 7. Testarea pluginului  

1.Adaugă 5–6 notițe cu priorități și date de reamintire diferite.

1.1 Adaugam nivelele de prioritate 

<img width="1139" height="268" alt="image" src="https://github.com/user-attachments/assets/4e32bc5c-11cb-4949-813b-bd2fc13b4cff" />

2.Atribuie fiecăreia o prioritate (High/Medium/Low) și completează câmpul „Due Date”.

<img width="1746" height="718" alt="image" src="https://github.com/user-attachments/assets/ba9dd2dc-b840-4fd3-af83-8e6a016b05e9" />

<img width="1076" height="343" alt="image" src="https://github.com/user-attachments/assets/52447f76-2ca6-443a-b1d6-f15f81ff82f6" />

3.Creează pagina „All Notes” și inserează următoarele shortcode-uri:

3.1 [usm_notes] – pentru afișarea tuturor notițelor.

<img width="774" height="890" alt="image" src="https://github.com/user-attachments/assets/091ad8df-cffb-4c71-bb37-5ff437a75640" />


3.2 [usm_notes priority="Inalt"] – pentru notițele cu prioritate mare.

<img width="731" height="502" alt="image" src="https://github.com/user-attachments/assets/ee3d5482-2bc4-4811-abef-faf523809ffd" />

3.3 [usm_notes before_date="2026-04-15"] – pentru notițele cu dată de reamintire anterioară zilei de 15 aprilie 2026.

<img width="740" height="711" alt="image" src="https://github.com/user-attachments/assets/96b45523-ae3a-4495-9df5-9bb4363ad83e" />

Dupa cum vedem amintirea despre Examene a disparut caci a este pe data de 20 aprilie

## Întrebări de control

Care este diferența esențială dintre o taxonomie personalizată și un metacâmp? Oferă un exemplu când este mai potrivit să folosești taxonomie și când metadate.

Diferența majoră este că taxonomia servește la clasificarea mai multor postări sub un numitor comun, în timp ce metacâmpul stochează o proprietate unică a unei postări. De exemplu, folosești o taxonomie pentru "Prioritate" deoarece vrei să filtrezi toate notele "High" într-o listă, dar folosești un metacâmp pentru "Data de reamintire" fiindcă este o informație specifică acelei note, care nu trebuie să grupeze alte postări.

De ce este necesar nonce la salvarea metacâmpurilor și ce se întâmplă dacă nu este verificat?

Un nonce funcționează ca un cod de verificare unic care atestă că solicitarea de salvare este legitimă și provine din interfața ta de admin. Fără această verificare, site-ul este expus atacurilor de tip CSRF, unde un utilizator rău intenționat poate păcăli browserul unui administrator să modifice sau să șteargă date din baza de date fără ca acesta să știe.

Care sunt cei mai importanți parametri ai register_post_type() și register_taxonomy() pentru frontend și UX (numește cel puțin trei și explică de ce)?

Parametrul public este vital pentru ca postările să fie accesibile vizitatorilor pe site, nu doar în panoul de control. Has_archive îmbunătățește experiența utilizatorului permițând vizualizarea automată a tuturor postărilor pe o pagină de tip listă, iar hierarchical (pentru taxonomii) oferă o interfață intuitivă cu bife (ca la categorii), fiind mult mai ușor de utilizat decât introducerea manuală a tag-urilor.
