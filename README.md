# Uplatko

Slika uplatnice, fakture ili predračuna → NBS IPS QR kôd za plaćanje m-bankingom.

Cela aplikacija je jedan fajl, `index.html`, bez build koraka i bez servera.

## Kako se koristi

1. Slikaj, prevuci ili nalepi (Ctrl+V) uplatnicu, screenshot ili tekst sa podacima za plaćanje.
2. Proveri polja: primalac, račun, iznos, šifra plaćanja, poziv na broj.
3. Skeniraj QR kôd aplikacijom banke. „Preko celog ekrana" daje najveći kôd za skeniranje sa monitora.

## Napomene

- U Claude verziji sliku i tekst čita Claude (najtačnije). Na običnom hostingu (Netlify) radi besplatan OCR u browseru (Tesseract.js): račun, iznos, šifru, poziv na broj i svrhu uglavnom pročita, a primaoca i uplatioca često treba dopuniti ručno.
- Proverava se kontrolni broj računa (mod 97) i poziva na broj kod modela 97.
- Primalac i uplatilac smeju imati najviše 70 znakova (NBS pravilo); duži naziv blokira QR.
- Podrazumevana šifra plaćanja je 289; gotovinske šifre 1xx se pri čitanju prebacuju u 2xx.
- Pre potvrde uplate uvek proveri račun i iznos u banci.

QR biblioteka: qrcode-generator 1.4.4 (MIT, Kazuhiko Arase), ugrađena u `index.html`.
