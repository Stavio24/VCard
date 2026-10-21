# Carte de vizită digitală configurabilă

Șablon static, fără instalare, framework, fonturi externe sau servicii de urmărire. Datele demonstrative trebuie înlocuite înainte de publicare. HTML, CSS și JavaScript originale pot fi reutilizate și modificate liber.

## Fișiere
- index.html: structura paginii.
- style.css: aspect și adaptare la mobil.
- app.js: încărcarea configurației și interacțiuni.
- config.json: toate datele profilului și principalele opțiuni vizuale.
- assets/: pune aici fotografia și CV-ul.

## Personalizare
Editează config.json în Notepad, VS Code sau alt editor de text, păstrând formatul UTF-8. Nu folosi Word. JSON cere ghilimele duble, fără comentarii și fără virgulă după ultimul element. Pentru un rând nou în text folosește secvența \n.

| Câmp | Conținut |
|---|---|
| name | Numele afișat (obligatoriu) |
| firstName / lastName | Prenume / nume de familie, folosite în contactul vCard |
| role / organization | Titulatură / organizație |
| location | Localitate și țară |
| intro / about | Prezentare scurtă / descriere detaliată |
| brand / availability / footer | Antet / mesaj disponibilitate / final |
| photo | De exemplu assets/portret.jpg |
| photoAlt | Descriere accesibilă a fotografiei |
| email | Adresa fără prefixul mailto: |
| phone | Telefon, preferabil cu prefix internațional |
| whatsapp | Număr internațional, de exemplu +407xxxxxxxx |
| website | Adresă completă, începând cu https:// |
| cv | De exemplu assets/cv.pdf |
| skills | Listă de competențe |
| projects | Listă de obiecte cu title, description și url |
| social | Listă de obiecte cu label și url |
| theme.accent | Culoarea principală în format #136b61 |
| theme.background | Culoarea fundalului în format #f2f0e9 |
| language | ro sau en, pentru limba documentului |
| labels | Textele butoanelor și titlurile secțiunilor |

Pentru a ascunde un câmp, lasă șirul gol: "phone": "". Pentru a elimina o secțiune cu liste, folosește []. Fără fotografie sunt afișate inițialele. O fotografie inaccesibilă este înlocuită automat cu inițialele.

Exemplu social:
"social": [{"label": "LinkedIn", "url": "https://www.linkedin.com/in/profilul-tau/"}]

Poți traduce textele profilului și labels pentru a crea o versiune în altă limbă. Nu există comutator bilingv automat. Modificarea culorilor cere verificarea lizibilității textului alb de pe butoane.

## Testare locală
Dezarhivează întregul pachet. Deschide index.html prin dublu clic și selectează config.json în pagina afișată. Browserul citește JSON-ul local; nu îl trimite unui server. Fotografiile relative sunt căutate lângă index.html, nu lângă JSON-ul selectat. Reîncarcă pagina pentru a selecta altă configurație.

Alternativ, dacă ai Python: deschide terminalul în acest folder și rulează `python -m http.server 8000 --bind 127.0.0.1`, apoi deschide http://127.0.0.1:8000. Configurația se încarcă automat.

## GitHub Pages
1. Creează un repository public pentru găzduirea gratuită GitHub Pages.
2. Încarcă fișierele DIN acest folder la rădăcina repository-ului, nu arhiva ZIP.
3. În Settings → Pages alege Deploy from a branch, main, / (root), Save.
4. După publicare, deschide https://UTILIZATOR.github.io/REPOSITORY/.
5. Pentru actualizare editează config.json și salvează modificarea (Commit changes). Așteaptă republicarea.

Căile sunt relative, deci funcționează și pentru un site de proiect în subdirector. Păstrează numele config.json exact, cu litere mici. Păstrează aceeași adresă când o imprimi ca QR sau o scrii pe NFC.

## Distribuire altor persoane
Trimite această arhivă sau oferă repository-ul ca șablon. Fiecare persoană păstrează propria copie, editează config.json, adaugă propriile imagini și o publică separat. Nu este necesară modificarea HTML-ului.

## Funcționalități și limite
- Contactul .vcf este generat local din datele JSON. Importul depinde de aplicația de contacte a telefonului.
- Telefonul, e-mailul și WhatsApp deschid aplicația/serviciul corespunzător; nu trimit automat mesaje.
- Distribuirea folosește meniul sistemului dacă este disponibil sau copiază linkul. Nu se afișează la deschiderea prin file://.
- Nu include formular de trimitere, chatbot IA, autentificare, PIN sau generator QR.
- Tot conținutul publicat, inclusiv config.json, fotografia și CV-ul, este public. Nu introduce parole, chei API sau documente confidențiale.
- Este un șablon cu date demonstrative, fără fotografii personale incluse.
- Verificare efectuată: sintaxă JavaScript, structură JSON, căi și conținut arhivă. Randarea vizuală în browser nu a fost verificată în această livrare.
