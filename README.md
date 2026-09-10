# The statutory withdrawal-button wording, in all 24 official EU languages

Article 11a of the Consumer Rights Directive (2011/83/EU, inserted by Directive (EU) 2023/2673)
does not only require that an online shop **have** a withdrawal function. It prescribes **how its
buttons are labelled** — and the label differs in every official language, because every language
version of the directive is equally authentic.

If you are building a withdrawal button for WooCommerce, Magento, Shopware, PrestaShop, PlentyShop,
Shopify, Wix or your own checkout, you need these 24 rows. Assembling them otherwise means
opening 24 EUR-Lex pages and copying by hand, and copying by hand is exactly where the
errors come from.

**Take it. It is free, including commercially. All we ask is a credit with a link, so corrections
find their way back to one place.**

```
curl -O https://cooloffapp.com/data/eu-withdrawal-button-wording.json
```

## What is in the file

`eu-withdrawal-button-wording.json` — one entry per language:

| field | meaning |
|---|---|
| `withdraw_button` | the label on the button that opens the withdrawal — Art. 11a(1)(a) |
| `confirm_button` | the label on the confirmation button at the end of the form — Art. 11a(3) |
| `field_name` · `field_contract` · `field_email` | the three form fields — Art. 11a(2)(a)–(c) |
| `carries_deictic` | whether the official label names a place (“here”, “ici”, “hier”) |

Plus `national_provisions` for Germany (§ 356a BGB, in force 19 June 2026) and Austria
(§ 13a FAGG, in force 1 October 2026), because the two diverge in a way that matters — see below.

## The detail that gets lost in transcription

The English reads “Withdraw from contract **here**” and the French “Renoncer au contrat **ici****”,
so the deictic looks universal. It is not. **6 language versions have no “here” at
all**: Danish, German, Estonian, Croatian, Hungarian, Latvian.

That is not a transcription slip in the Official Journal — it is what the official texts say.
18 versions carry a place word, 6 do not. “Completing”
one of those 6 departs from the statutory wording. The `carries_deictic` flag is
computed from the labels themselves, never copied from a comment — that test already disproved a
hand-written note in our own source once.

## Germany and Austria diverge, and not in the way you would guess

Both allow a different formulation, but **not the same latitude**:

- **Germany**, § 356a BGB: „oder einer anderen **gleichbedeutenden** eindeutigen Formulierung“.
- **Austria**, § 13a FAGG: „oder einer **entsprechenden** eindeutigen Formulierung“ — and Abs. 4
  puts **„ausschließlich“** in front of the confirmation label. The German Abs. 3 has no such word.

Austria also applies only to contracts concluded **after 30 September 2026** (§ 20 Abs. 5 FAGG),
and is enacted by BGBl. I Nr. 59/2026 — RIS document `NOR40279256`, transitional rule
`NOR40279262`.

## Where the rows come from, and how they stay right

Source: `CELEX:32023L2673` on EUR-Lex — Art. 11a(1)(a) and (3) for the buttons, (2)(a)–(c) for the
fields. **A script refetches all 24 official language versions and asserts that every
label appears verbatim in its own version.** The run recorded in `verification` returned
**24/24** on 2026-09-10.

Found a row that is wrong? Open an issue. We will fix it, say what was wrong, and the fix reaches
every copy from here.

## The table

| code | language | withdrawal button | confirmation button |
|---|---|---|---|
| `bg` | Bulgarian | Откажете се от договора тук | Потвърждавам отказа |
| `hr` | Croatian | Odustati od ugovora | Potvrditi odustajanje |
| `cs` | Czech | Zde odstoupit od smlouvy | Potvrdit odstoupení od smlouvy |
| `da` | Danish | Fortryd aftale | Bekræft fortrydelse |
| `nl` | Dutch | Hier de overeenkomst herroepen | Herroeping bevestigen |
| `en` | English | Withdraw from contract here | Confirm withdrawal |
| `et` | Estonian | Taganen lepingust | Kinnitan taganemise |
| `fi` | Finnish | Peruuta sopimus tästä | Vahvista peruuttaminen |
| `fr` | French | Renoncer au contrat ici | Confirmer la rétractation |
| `de` | German | Vertrag widerrufen | Widerruf bestätigen |
| `el` | Greek | Πατήστε εδώ για υπαναχώρηση | Επιβεβαίωση υπαναχώρησης |
| `hu` | Hungarian | Elállás a szerződéstől | Elállás megerősítése |
| `ga` | Irish | Tarraing siar ón gconradh anseo | Dearbhaigh an tarraingt siar |
| `it` | Italian | Recedere dal contratto qui | Conferma recesso |
| `lv` | Latvian | Atteikties no līguma | Apstiprināt atteikumu |
| `lt` | Lithuanian | Atsisakyti sutarties čia | Patvirtinti sutarties atsisakymą |
| `mt` | Maltese | Irtira mill-kuntratt hawnhekk | Ikkonferma r-reċess |
| `pl` | Polish | Odstąp od umowy tutaj | Potwierdź odstąpienie od umowy |
| `pt` | Portuguese | Retrate-se do contrato aqui | Confirmar retratação |
| `ro` | Romanian | Retrageți-vă din contract aici | Confirmați retragerea |
| `sk` | Slovak | Odstúpiť od zmluvy tu | Potvrdiť odstúpenie od zmluvy |
| `sl` | Slovenian | Kliknite tukaj za odstop od pogodbe | Potrdi odstop od pogodbe |
| `es` | Spanish | Desistir del contrato aquí | Confirmar desistimiento |
| `sv` | Swedish | Ångra avtalet här | Bekräfta frånträde |

## Licence

**CC BY 4.0** — see `LICENSE`. The underlying statutory text is from official EU sources; the
compilation, the derived fields and the national notes are the part this licence covers.

Attribute as: *Cooloff — https://cooloffapp.com/en/eu-withdrawal-button-wording/*

## Who publishes this

Assembled while building [Cooloff](https://cooloffapp.com/), a free withdrawal-button app for Wix.
The app uses exactly these rows. **The table stands on its own** — it is just as useful if your shop
does not run on Wix and you are building the function yourself, which is why it is published
separately and under a licence that lets you do that.

Human-readable versions: [English](https://cooloffapp.com/en/eu-withdrawal-button-wording/) · [Deutsch](https://cooloffapp.com/de/eu-widerrufsbutton-wortlaut/).

---

This reproduces the wording of official texts and situates it. **It is not legal advice.** Whether
a particular contract carries a right of withdrawal is a separate question — in Germany, see
§ 312g(2) BGB.
