#  Forslag til navnekonvensjon for Azure/Microsoft 365 miljø
Dette dokumentet beskriver et **forslag** til navnestandarder som skal brukes i Azure og Microsoft 365 (M365) miljøer. Konsistente navnestandarder er avgjørende for enkel administrasjon, feilsøking, sikkerhet, og for å sikre at ressursene er lett gjenkjennelige.

## Generelle retningslinjer
1. **Lesbarhet:** Navn skal være lett lesbare og meningsfulle.
2. **Korthet**: Hold navn så korte som mulig, men lange nok til å være beskrivende.
3. **Konsistens:** Bruk enhetlige konvensjoner for å sikre konsistens på tvers av alle ressurser.
4. **Unikhet:** Navn må være unike for å unngå konflikter.
5. **Unngå Spesialtegn:** Bruk ikke spesialtegn, mellomrom, eller store bokstaver. Bruk bindestrek (-) og understrek (_).

## Hvordan opprettholde "Best Practice" for navnestandard
1. **Dokumentasjon:** Dokumenter alle navnestandarder i en sentral guide som er tilgjengelig for alle administratorer.
2. **Automatisering:** Bruk automatiserte verktøy for å håndheve navnekonvensjoner *(eksempel Tagging Policy og andre regler for navn ved opprettelse)*
3. **Revisjon:** Gjennomfør regelmessige revisjoner for å sikre at navnestandarder følges.
4. **Opplæring:** Gi opplæring til alle relevante medarbeidere om viktigheten av og retningslinjene for navnestandarder.

## Navnestandard for Subscriptions
Et Azure Subscription er en konto som gir tilgang til Azure-tjenester og fungerer som en container for ressurser som virtuelle maskiner, databaser, lagringskontoer og mye mer. Hver subscription har en unik ID og kan være assosiert med en spesifikk organisasjon eller avdeling.

### Forslag til navnestandard for Subscriptions
Under er et forslag til navnestandard for alle Subscriptions som blir opprettet i Azure miljøet. 

Navnestruktur: 
`{selskap}-{avdeling eller prosjekt (valgfritt)}-{miljø}-sub` skrives med små bokstaver.

Tabellen under viser et eksempel på hvordan navnestrukturen kan se ut.

| Selskap | Avdeling eller Prosjekt (valgfritt) | Miljø | Subscription Navn           |
|---------|-------------------------------------|-------|-----------------------------|
| Contoso | TSS                                 | utv   | contoso-tss-utv-sub         |
| Contoso | TIKT                                | prod  | contoso-tikt-prod-sub       |
| Contoso | TMA                                 | utv   | contoso-tma-utv-sub         |
| Contoso | B024 *(eksempel på prosjekt)*       | utv   | contoso-b024-utv-sub        |


## Navnestandard for Tags

### Noen vanlige brukstilfeller for tagging inkluderer:

Fakturering: Gruppe ressurser og assosiere dem med fakturering eller kostnadskoder.
Tjenestekontekstidentifikasjon: Identifisere grupper av ressurser på tvers av ressursgrupper for felles operasjoner og gruppering.
Tilgangskontroll og sikkerhetskontekst: Administrativ rolleidentifikasjon basert på portefølje, system, tjeneste, app, instans, etc.















