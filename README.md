# Lucrarea de laborator nr. 5. Securitatea WordPress

## Scopul lucrării

Consolidarea celor mai importante practici de securitate în WordPress: gestionarea rolurilor și parolelor, actualizări, hardening de bază (wp-config.php, permisiuni, dezactivarea editorului), 
backup, monitorizarea activității și configurarea pas cu pas a All In One WP Security & Firewall (AIOS) pentru protecție împotriva atacurilor de tip brute-force, WAF de bază și controlul 
permisiunilor.

## Condiții

Creează un plugin educațional numit USM Notes, care adaugă pe site o secțiune „Notițe” cu priorități și o dată de reamintire.

###  Pasul 1. Pregătirea mediului

1.În instalarea locală WordPress, accesează panoul de administrare.

2.Asigură-te că ai acces de administrator.

<img width="1450" height="89" alt="image" src="https://github.com/user-attachments/assets/5470ecd7-c0cb-447b-9463-1c74bd7757b6" />

3.Activează modul de depanare în wp-config.php, adăugând define('WP_DEBUG', true);

<img width="705" height="252" alt="image" src="https://github.com/user-attachments/assets/721a6fae-cd2f-43da-9718-0ab9fb02bbea" />

### Pasul 2. Gestionarea rolurilor și parolelor

1.Creează un utilizator de test cu rolul Autor (pentru verificări ulterioare).

<img width="788" height="725" alt="image" src="https://github.com/user-attachments/assets/40c292ea-084e-46de-8ab6-22d805a2ae3b" />

<img width="1443" height="57" alt="image" src="https://github.com/user-attachments/assets/89509a00-3a60-48c1-92f5-4fdb3f8ed2d6" />

2.Verifică dacă fiecare administrator are parole complexe activate (minimum 8 caractere, litere/cifre/simboluri).

<img width="768" height="176" alt="image" src="https://github.com/user-attachments/assets/25880fe6-77d1-4acc-af20-a84749344626" />

### Pasul 3. Actualizări ale nucleului, temelor și pluginurilor

1.Verifică existența actualizărilor pentru WordPress, teme și pluginuri.

<img width="157" height="104" alt="image" src="https://github.com/user-attachments/assets/a082a247-1bc6-49dd-944b-3b0987dd983a" />

2.Actualizează toate componentele la ultimele versiuni disponibile.

<img width="1736" height="384" alt="image" src="https://github.com/user-attachments/assets/73901b0f-50cf-4a91-b10d-f9ec97cb90f9" />

<img width="1761" height="296" alt="image" src="https://github.com/user-attachments/assets/510b9291-75f4-4f62-b470-570934851710" />

3.Configurează actualizările automate pentru teme și pluginuri.

Pentru Teme:

<img width="159" height="68" alt="image" src="https://github.com/user-attachments/assets/dd4dc355-2a84-45b0-b5e3-9b4f05bf16b6" />

<img width="1442" height="804" alt="image" src="https://github.com/user-attachments/assets/88e6f5f3-997b-4b77-8e29-b713b9d253e5" />

Pentru Pluginuri:

<img width="158" height="65" alt="image" src="https://github.com/user-attachments/assets/ea0e98f1-5040-45be-b9a7-ddccbff54e50" />

<img width="165" height="217" alt="image" src="https://github.com/user-attachments/assets/88eabb8c-e5cb-4c07-8b97-3074609e8539" />

4.Asigură-te că toate actualizările s-au aplicat cu succes și că site-ul funcționează corect.

Teme:

Observam ca butonul si-a schimbat denumirea,deci actualizarile automate au fost setate cu succes 

<img width="1445" height="810" alt="image" src="https://github.com/user-attachments/assets/7b9d8436-43e2-44d3-b667-661c0bc4ec2d" />

Pluginuri:

Selectam toate,dam click pe Apply si vedem un mesaj de succes

<img width="284" height="89" alt="image" src="https://github.com/user-attachments/assets/770d9c01-2efd-46f5-9ed6-bea5a9e09986" />

<img width="368" height="86" alt="image" src="https://github.com/user-attachments/assets/1bd3474e-06a5-496e-bf10-81481eee2d63" />

Vedem ca siteul functioneaza si toate editarile sunt permise 

<img width="915" height="326" alt="image" src="https://github.com/user-attachments/assets/692ca10a-fa1a-4dc7-a513-22f4ce71cb88" />

### Pasul 4. Hardening de bază

1.Dezactivează editarea fișierelor din panoul de administrare, adăugând în wp-config.php:

Dam scroll pana jos si punem sectiunea de cod 

```
define('DISALLOW_FILE_EDIT', true);
```

<img width="300" height="34" alt="image" src="https://github.com/user-attachments/assets/11af9616-2879-4ca8-bf37-d6c4c4946ef7" />


3.Protejează fișierul wp-config.php, adăugând în .htaccess:

```
<files wp-config.php>
   order allow,deny
   deny from all
</files>
```

<img width="221" height="80" alt="image" src="https://github.com/user-attachments/assets/c6b82d5a-f803-4ec7-98be-a45e34daf4d4" />

### Pasul 5. Instalarea și configurarea inițială a All In One WP Security & Firewall (AIOS)

1.Instalează și activează pluginul All In One WP Security & Firewall.

<img width="160" height="96" alt="image" src="https://github.com/user-attachments/assets/35b37b69-1d03-43b1-91bb-720475eab411" />

<img width="563" height="240" alt="image" src="https://github.com/user-attachments/assets/43b4b90b-3769-408b-887b-ffb8ca37a92f" />

<img width="554" height="237" alt="image" src="https://github.com/user-attachments/assets/ecb11baa-3c13-4615-9a41-e97d767f05c0" />

2.Accesează secțiunea pluginului din panoul de administrare.

<img width="158" height="525" alt="image" src="https://github.com/user-attachments/assets/bb1d86bd-e656-4352-91dc-5b0293b11355" />

3.Configurează următorii parametri:

User Login:

Activează Login Lockdown. Parametri recomandați pentru testare: Max Login Attempts: 5, Login Retry Time Period: 15 min, Lockout Time: 30 min.

<img width="1230" height="567" alt="image" src="https://github.com/user-attachments/assets/dfd2a69c-8027-457a-9307-aa2cbc2f48c3" />

Activează Force Logout (de exemplu, 24h) pentru a limita sesiunile „eterne”.

<img width="930" height="299" alt="image" src="https://github.com/user-attachments/assets/9f3ce3ce-2091-42f8-bf32-d09f5788d249" />

User Accounts:

Verifică dacă există un utilizator cu loginul admin. Dacă da — redenumește-l prin AIOS cu un nume de utilizator sigur.

<img width="246" height="99" alt="image" src="https://github.com/user-attachments/assets/5ef39624-fffb-4d60-a44a-47b8536ab15f" />

User Registration:

Dezactivează auto-aprobarea sau activează aprobarea manuală a utilizatorilor noi dacă înregistrarea este activată.

<img width="1370" height="416" alt="image" src="https://github.com/user-attachments/assets/315c5e6b-e615-4f5a-a014-481092ace23b" />

Filesystem Security:

Rulează verificarea File Permissions și aplică corecturile recomandate (nu seta permisiuni scriere globale).

<img width="1727" height="242" alt="image" src="https://github.com/user-attachments/assets/e97a47a0-0832-4e1d-9611-672ce1331ea3" />

Apasam butonul Set up now si vedem mesajul dee succes

Firewall:

Activează Basic Firewall (începe cu nivelul de bază).

Activează protecția împotriva Bad Query Strings, XSS, directory browsing.

<img width="1352" height="296" alt="image" src="https://github.com/user-attachments/assets/173d6de1-9769-41a7-8e6d-d3e78662654c" />

<img width="1360" height="488" alt="image" src="https://github.com/user-attachments/assets/7e25ac1c-ec39-431b-8989-bfb818aecbca" />

<img width="1358" height="500" alt="image" src="https://github.com/user-attachments/assets/0086e203-16b0-43ed-9e9f-9840d9f1ba3b" />

<img width="1354" height="492" alt="image" src="https://github.com/user-attachments/assets/96825d2f-73e2-43ef-8145-208b4a129665" />

Brute Force:

Activează Rename Login Page (schimbă URL-ul de autentificare de la /wp-login.php la ceva unic, de ex. /login-<slug>).

<img width="1702" height="411" alt="image" src="https://github.com/user-attachments/assets/331ad32b-2411-48b7-8dcd-095b85aea064" />

Salvează noul URL într-un manager de parole!

Scanner / Malware:

Configurează file change detection (notificări pe email).

<img width="767" height="230" alt="image" src="https://github.com/user-attachments/assets/8c55af67-a855-4103-96ef-04080a0f640f" />

Backup:

În secțiunea Database, creează o copie de rezervă a BD (stocheaz-o în afara rădăcinii web). Configurează un program de backup, dacă este disponibil.

<img width="679" height="190" alt="image" src="https://github.com/user-attachments/assets/530e1f09-4381-49ac-8291-960bc9338481" />

<img width="1524" height="217" alt="image" src="https://github.com/user-attachments/assets/287d14f7-1040-4ea8-8c21-bd450851b164" />

<img width="607" height="462" alt="image" src="https://github.com/user-attachments/assets/807d5474-ff80-4332-b9c9-b9445bc0b821" />

<img width="455" height="236" alt="image" src="https://github.com/user-attachments/assets/ba54aa68-d8a8-4e94-b3da-eabc5b221042" />

<img width="586" height="371" alt="image" src="https://github.com/user-attachments/assets/e4d46e90-56b7-4e8e-8447-a992f2635252" />

Notifications:

Activează notificări pe email pentru evenimente importante (de ex. blocare, cont nou de admin, modificări de fișiere).

<img width="1080" height="305" alt="image" src="https://github.com/user-attachments/assets/85a03ebc-fa05-4a99-943e-c2bd4b794dad" />

<img width="837" height="234" alt="image" src="https://github.com/user-attachments/assets/5f433598-defd-4437-af0a-65b02f88f9df" />

<img width="284" height="32" alt="image" src="https://github.com/user-attachments/assets/ebc729b2-883c-4338-956b-aac825e2fb04" />

### Pasul 6. Testarea protecției brute-force (pe un utilizator de test)

1.Deconectează-te din admin (sau folosește o fereastră privată).

2.Accesează noul URL de autentificare, încearcă să introduci o parolă greșită de 5–6 ori.

http://localhost/wordpress/login-%3Cslug%3E/?loggedout=true&wp_lang=en_US

3.Asigură-te că Lockdown-ul s-a activat (blocare IP/utilizator).

<img width="969" height="395" alt="image" src="https://github.com/user-attachments/assets/15a82726-6402-4b6d-9ea6-f0fc7104a5ef" />

4.Verifică înregistrarea blocării în WP Security → Dashboard / Logs și (dacă este necesar) deblochează IP-ul de test.

<img width="397" height="108" alt="image" src="https://github.com/user-attachments/assets/5f83de55-9c05-4cc7-84b3-2c4f7a27676a" />

### Pasul 7. Restaurarea din backup

1.Șterge o postare de test și o imagine aleatorie.

Stergem o Postare

<img width="298" height="95" alt="image" src="https://github.com/user-attachments/assets/aef65ac0-99db-4f46-b7f8-6fdd79b8493b" />

2.Restaurează baza de date din backup (import SQL sau prin plugin).

<img width="303" height="89" alt="image" src="https://github.com/user-attachments/assets/f28073cd-f27f-4341-ab10-9efdb72e863b" />

<img width="302" height="63" alt="image" src="https://github.com/user-attachments/assets/370a985f-d94e-4bb7-9037-59d786121c1c" />

3.Verifică integritatea datelor (au fost restaurate imaginea și postarea șterse?).

<img width="324" height="95" alt="image" src="https://github.com/user-attachments/assets/5c7fd694-b873-4b48-a9e9-5562afd8d0d1" />

Postarea din nou a aparut 

###

1.De ce DISALLOW_FILE_EDIT și permisiunile corecte pe wp-config.php reduc semnificativ riscul post-exploit?

Am învățat că aceste măsuri sunt „ultima linie de apărare” în cazul în care cineva ne sparge parola de admin.

Prin DISALLOW_FILE_EDIT îi blocăm atacatorului posibilitatea de a scrie cod periculos direct în temele site-ului din browser, 

iar prin permisiunile stricte pe wp-config.php ne asigurăm că acesta nu poate vedea sau modifica datele secrete de conectare la baza de date, chiar dacă a reușit să intre în panoul de control.

2.Ce setări ai ales pentru Login Lockdown/Firewall și de ce (explică echilibrul între securitate și experiența utilizatorului)?

Pentru Lockdown am setat 5 încercări în 15 minute cu o blocare de 30 de minute, pentru că am vrut un echilibru între securitate și utilizatori uituci. 

E destul de restrictiv ca să oprească un robot care încearcă mii de parole, dar destul de permisiv ca un om real să nu fie blocat din prima greșeală de tastare. 

La Firewall am activat regulile de bază pentru a opri atacurile de tip XSS sau injectările în URL fără să încetinesc viteza de încărcare a site-ului local.

3.Cu ce se deosebesc măsurile de protecție la nivel WordPress (plugin/WAF) față de cele la nivelul serverului web și al sistemului de operare?

Măsurile din WordPress, cum e plugin-ul AIOS, se ocupă de logica internă a site-ului și de utilizatori, în timp ce protecția la nivel de server prin .htaccess acționează ca un scut exterior care oprește atacul înainte ca acesta să ajungă măcar la codul WordPress. 

Nivelul sistemului de operare (permisiunile 755/644) este cel mai de jos strat, care controlează fizic cine are voie să scrie sau să citească fișierele pe

hard disk-ul serverului, indiferent de ce spune aplicația.

4.Ce trebuie inclus neapărat într-un backup „complet” WordPress și cum verifici dacă restaurarea funcționează cu adevărat?

Un backup e complet doar dacă ai și baza de date SQL cu toate textele și setările, dar și folderul wp-content care conține toate pozele, temele și plugin-urile instalate.

Ca să fiu sigur că restaurarea a funcționat cu adevărat, nu m-am uitat doar la mesaje, ci am verificat manual dacă imaginile apar corect în bibliotecă și dacă

link-urile paginilor (Permalinks) nu dau eroare 404, semn că și .htaccess a fost restaurat bine.
