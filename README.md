# amendo-content

Conținutul public al aplicației **Amendo** - amenzi și legislație fiscală
explicate simplu, alături de textul oficial nemodificat.

**Aplicație independentă. Nu este afiliată ANAF sau altei instituții publice.**

## Ce conține

| Fișier | Rol |
|---|---|
| [`data.json`](data.json) | catalogul de legislație: acte normative, contravenții, termene, calendar fiscal |
| [`index.html`](https://abeducation.github.io/amendo-content/) | pagina de prezentare |
| [`confidentialitate.html`](https://abeducation.github.io/amendo-content/confidentialitate.html) | politica de confidențialitate |
| [`independenta.html`](https://abeducation.github.io/amendo-content/independenta.html) | declarația de independență |

## De ce este public

Legislația se schimbă. Aplicația verifică acest fișier cel mult o dată pe
săptămână și preia versiunea nouă fără să fie nevoie de o actualizare din
Google Play. Dacă fișierul nu poate fi descărcat, aplicația folosește copia
inclusă în ea - nu se blochează niciodată la pornire.

Fiind public, catalogul poate fi citit, verificat și contestat de oricine.
Pentru o aplicație despre lege, asta este o caracteristică, nu un compromis:
istoricul de commit-uri arată exact ce s-a schimbat, când și de ce.

Cererea pe care o face aplicația este un simplu `GET` către un fișier static:
nu conține nume de utilizator, cookie sau alt identificator și este identică
indiferent cine o face. Detalii complete în
[politica de confidențialitate](https://abeducation.github.io/amendo-content/confidentialitate.html).

## Structura pe scurt

```jsonc
{
  "schemaVersion": 2,     // versiunea formatului; aplicația refuză ce nu înțelege
  "version": 2,           // se incrementează la fiecare publicare de conținut
  "updatedAt": "2026-08-20",
  "acts": [ ... ],        // actele normative, cu explicații și articole-cheie
  "categories": [ ... ],
  "fines": [ ... ],       // contravențiile: text oficial + explicație simplă
  "rules": { ... },       // reguli de reducere, prescripție, termene
  "events": [ ... ],      // calendarul obligațiilor fiscale
  "contestReasons": [ ... ],
  "pvItems": [ ... ]      // mențiunile obligatorii ale procesului-verbal
}
```

Fiecare contravenție are **două fețe**: câmpul `oficial` conține textul legii
verbatim, nemodificat, cu elidările marcate `[...]`; câmpul `explica` este
explicația în limbaj simplu. Nimic nu este parafrazat în câmpul `oficial`.

## Ai găsit o greșeală?

Este cel mai util lucru pe care îl poți face pentru această aplicație.

Deschide un [issue](https://github.com/abeducation/amendo-content/issues) sau
scrie la <andreialgebo@gmail.com>. Dacă poți, include:

- ce fapt este greșit și unde apare (id-ul amenzii ajută);
- textul corect, cu actul, articolul și alineatul;
- forma consolidată din care l-ai luat, cu data afișată pe pagină
  ([legislatie.just.ro](https://legislatie.just.ro) sau Monitorul Oficial).

## Un ghid, nu consultanță juridică

Amendo este un ghid informativ. Nu oferă consultanță juridică; pentru situații
concrete, consultă un avocat. Textul oficial afișat este preluat din
legislație, dar rămâi responsabil să verifici varianta în vigoare la data
faptei - mai ales pentru prevederi care își pot schimba starea (în vigoare /
suspendat / abrogat) de la o dată la alta.
