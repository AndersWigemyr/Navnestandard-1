# Spørsmål før ferdigstilling av dokument
- Hvor mange subscriptions tenker man å ha i miljøet? Skal det være en del så bør man ha Management Groups.
- Hvor mange avdelinger skal inn å bruke miljøet?

#  Forslag til navnekonvensjon for Azure/Microsoft 365 miljø
Dette dokumentet beskriver et **forslag** til navnestandarder som skal brukes i Azure og Microsoft 365 (M365) miljøer. Konsistente navnestandarder er avgjørende for enkel administrasjon, feilsøking, sikkerhet, og for å sikre at ressursene er lett gjenkjennelige.

## Generelle retningslinjer
1. **Lesbarhet:** Navn skal være lett lesbare og meningsfulle.
2. **Korthet**: Hold navn så korte som mulig, men lange nok til å være beskrivende.
3. **Konsistens:** Bruk enhetlige konvensjoner for å sikre konsistens på tvers av alle ressurser.
4. **Unikhet:** Navn må være unike for å unngå konflikter.
5. **Unngå Spesialtegn:** Bruk ikke spesialtegn, mellomrom, eller store bokstaver. Bruk bindestrek (-) og understrek (_).
6. **Alfanumerisk:** Når man lager navn på diverse grupper/ressurser og annet i miljøet skal man bruke alfanumeriske tegn (a-z og 0-9). Dette vil si at: Æ -> AE, Ø -> O og Å -> A

## Hvordan opprettholde "Best Practice" for navnestandard
1. **Dokumentasjon:** Dokumenter alle navnestandarder i en sentral guide som er tilgjengelig for alle administratorer.
2. **Automatisering:** Bruk automatiserte verktøy for å håndheve navnekonvensjoner *(eksempel Tagging Policy og andre regler for navn ved opprettelse)*
3. **Revisjon:** Gjennomfør regelmessige revisjoner for å sikre at navnestandarder følges.
4. **Opplæring:** Gi opplæring til alle relevante medarbeidere om viktigheten av og retningslinjene for navnestandarder.

## Navnestandard for Subscriptions
Et Azure Subscription er en konto som gir tilgang til Azure-tjenester og fungerer som en container for ressurser som virtuelle maskiner, databaser, lagringskontoer og mye mer. Hver subscription har en unik ID og kan være assosiert med en spesifikk organisasjon eller avdeling.
  
### Forslag til navnestandard for Subscriptions
Under er et forslag til navnestandard for alle subscriptions som blir opprettet i Azure miljøet. 

Navnestruktur: 
`{selskap}-{avdeling eller prosjekt (valgfritt)}-{miljo}-sub` skrives med små bokstaver.

Tabellen under viser et eksempel på hvordan navnestrukturen for subscriptions kan se ut.

| Selskap | Avdeling eller Prosjekt (valgfritt) | Miljø | Subscription Navn           |
|---------|-------------------------------------|-------|-----------------------------|
| Contoso | TSS                                 | utv   | contoso-tss-utv-sub         |
| Contoso | TIKT                                | prod  | contoso-tikt-prod-sub       |
| Contoso | TMA                                 | utv   | contoso-tma-utv-sub         |
| Contoso | B024 *(eksempel på prosjekt)*       | utv   | contoso-b024-utv-sub        |

## Navnestandard for Tags
Tags i Azure brukes til å organisere og kategorisere ressurser, noe som gjør administrasjon og rapportering enklere og mer effektivt.

### Noen vanlige brukstilfeller for tagging inkluderer:

- **Fakturering:** Gruppe ressurser og assosiere dem med fakturering eller kostnadskoder.
- **Tjenestekontekstidentifikasjon:** Identifisere grupper av ressurser på tvers av ressursgrupper for felles operasjoner og gruppering.
- **Forvalter eller kontaktperson:** Gjøre det enkelt for personer som ikke har kjennskap til ressursene å finne kontaktpersoner.

For Tags bruker vi **camelCase** som er en skrivemåte der hvert ord i en sammensatt ordsekvens starter med en stor bokstav, unntatt det første ordet, og det er ingen mellomrom eller spesialtegn mellom ordene (f.eks. forvaltesAv eller prosjektNavn).

Tabellen under viser et eksempel på hvordan navnestrukturen for tags kan se ut.  

| Tagg Navn                                 | Nøkkel           | Eksempel                        | Kommentar                                  |
|-------------------------------------------|------------------|---------------------------------|--------------------------------------------|
| Faktureres Til / Intern Kostnads-ID       | fakturaTil       | `TSS` eller `Intern Kostnads-ID`| Avdeling eller Intern Kostnads-ID          |
| Forvalter eller kontaktperson             | forvaltesAv      | `joe@contoso.com`               | Alias eller e-postadresse                  |
| Prosjektnavn (valgfritt)                  | prosjektNavn     | `B024`                          | Navn på prosjektet eller prosjekt ID       |
| Prosjektversjon (valgfritt)               | prosjektVersjon  | `1.0`                           | Versjon av prosjektet                      |
| Miljø                                     | miljo            | `<prod eller utv>`              | Miljøidentifikator (prod eller utv)        |
| Avdeling                                  | avdeling         | `TSS`                           | Navn på avdeling                           |

### Policy for Tags
En tagging policy i Azure er en regel eller et sett med regler som automatisk sørger for at ressurser blir merket med spesifikke tagger når de opprettes eller oppdateres. Disse reglene hjelper med å sikre at alle ressurser følger samme standard for tagging, noe som gjør det lettere å organisere, finne og administrere dem på tvers av organisasjonen. Når en ressurs opprettes i Azure kan man kreve at diverse tagger er lagt på denne ressursen *(eksempel at det må kreve en forvaltesAv- eller miljø-tag)*.


## Navnestandard for Azure Ressurser
Ressurser i Azure refererer til de ulike komponentene som kan opprettes, administreres og brukes innenfor Azure-plattformen, som virtuelle maskiner, databaser, lagringskontoer, nettverk, og app-tjenester.

## Forslag til navnestandard for Azure Ressursgrupper

Navnestruktur: 
`{selskap}-{miljø}-{applikajon, prosjekt eller funksjon}-rg` skrives med små bokstaver.

Tabellen under viser et eksempel på hvordan navnestrukturen for ressursgrupper kan se ut.  

| Selskap | Miljø | Applikasjon, prosjekt eller funksjon | Navn på ressursgruppe                 |
|---------|-------|--------------------------------------|---------------------------------------|
| Contoso | utv   | hrsystem                             | contoso-hrsystem-utv-rg               |
| Contoso | prod  | analyseapplikasjon                   | contoso-analyseapplikasjon-prod-rg    |
| Contoso | utv   | teamsbestilling                      | contoso-teamsbestilling-utv-rg        |
| Contoso | utv   | B024 *(eksempel på prosjekt)*        | contoso-b024-utv-rg                   |


# Forslag til navnestandard for Ressurser i Azure
Hver ressurstype eller tjenestetype i Azure innebærer et sett med navnerestriksjoner og omfang; enhver navnekonvensjon eller mønster må overholde de nødvendige navnerestriksjonene og omfanget. For eksempel, mens navnet på en VM knyttes til et DNS-navn (og derfor må være unikt over hele Azure), er navnet på et VNET (virtuelt nettverk) begrenset til Ressursgruppen det er opprettet i, og kan derfor ha et samme navn i en annen ressursgruppe.

Navnestruktur: 
`<applikasjon, prosjekt eller funksjon>-<miljø>-<ressurs-forkortelse><0-99>` skrives med små bokstaver.

Når det gjelder <ressurs-forkortelse> tar man utgangspunkt i Microsoft sine anbefalinger. Les mer om disse her: [Abbreviation recommendations for Azure resources - Microsoft](https://learn.microsoft.com/nb-no/azure/cloud-adoption-framework/ready/azure-best-practices/resource-abbreviations)

Generelt bør du unngå å ha spesialtegn (- eller _) som første eller siste tegn i noe navn, da disse vil feile de fleste valideringsregler.
I tabellen under ser man en rekke ressurser som finnes i Azure, i tillegg til 

For å lese mer om restriksjoner og krav for navn for ressurser, se her: [Naming rules and restrictions for Azure resources - Microsoft](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/resource-name-rules)


| Kategori      | Tjeneste eller Enhet         | Omfang          | Lengde                    | Skriftform          | Gyldige Tegn                                | Foreslått Mønster                           |
|---------------|-----------------------------|------------------|---------------------------|---------------------|---------------------------------------------|--------------------------------------------|
| Ressursgruppe | Ressursgruppe               | Global           | 1-64                      | Ikke skille mellom store og små bokstaver | Alfanumerisk, understrek og bindestrek     | `<service short name>-<environment>-rg`     |
| Ressursgruppe | Tilgjengelighetssett        | Ressursgruppe    | 1-80                      | Ikke skille mellom store og små bokstaver | Alfanumerisk, understrek og bindestrek     | `<service-short-name>-<context>-as`         |
| Generelt      | Tag                         | Tilknyttet Enhet | 512 (navn), 256 (verdi)  | Ikke skille mellom store og små bokstaver | Alfanumerisk                              | `"key" : "value"`                           |
| Beregning     | Virtuell Maskin             | Ressursgruppe    | 1-15                      | Ikke skille mellom store og små bokstaver | Alfanumerisk, understrek og bindestrek     | `<name>-<role>-<instance>`                  |
| Lagring       | Lagringskontonavn (data)    | Global           | 3-24                      | Små bokstaver        | Alfanumerisk                              | `<service short name><type><number>`        |
| Lagring       | Lagringskontonavn (disker)  | Global           | 3-24                      | Små bokstaver        | Alfanumerisk                              | `<vm name without dashes>st<number>`        |
| Lagring       | Container navn              | Lagringskonto    | 3-63                      | Små bokstaver        | Alfanumerisk og bindestrek                | `<context>`                                 |
| Lagring       | Blob navn                   | Container        | 1-1024                    | Skille mellom store og små bokstaver | Alle URL-tegn                              | `<variable based on blob usage>`            |
| Lagring       | Kø navn                     | Lagringskonto    | 3-63                      | Små bokstaver        | Alfanumerisk og bindestrek                | `<service short name>-<context>-<num>`      |
| Lagring       | Tabell navn                 | Lagringskonto    | 3-63                      | Ikke skille mellom store og små bokstaver | Alfanumerisk                              | `<service short name>-<context>`            |
| Lagring       | Fil navn                    | Lagringskonto    | 3-63                      | Små bokstaver        | Alfanumerisk                              | `<variable based on blob usage>`            |
| Nettverk      | Virtuelt Nettverk (VNet)    | Ressursgruppe    | 2-80                      | Ikke skille mellom store og små bokstaver | Alfanumerisk, bindestrek, understrek og punktum | `<service short name>-[section]-vnet`       |
| Nettverk      | Subnett                     | Overordnet VNet  | 2-80                      | Ikke skille mellom store og små bokstaver | Alfanumerisk, understrek, bindestrek og punktum | `<role>-subnet`                            |
| Nettverk      | Nettverksgrensesnitt        | Ressursgruppe    | 1-80                      | Ikke skille mellom store og små bokstaver | Alfanumerisk, bindestrek, understrek og punktum | `<vmname>-<num>nic`                         |
| Nettverk      | Nettverkssikkerhetsgruppe   | Ressursgruppe    | 1-80                      | Ikke skille mellom store og små bokstaver | Alfanumerisk, bindestrek, understrek og punktum | `<service short name>-<context>-nsg`        |
| Nettverk      | Nettverkssikkerhetsgrupperegel | Ressursgruppe   | 1-80                   | Ikke skille mellom store og små bokstaver | Alfanumerisk, bindestrek, understrek og punktum | `<descriptive context>`                     |
| Nettverk      | Offentlig IP-adresse        | Ressursgruppe    | 1-80                      | Ikke skille mellom store og små bokstaver | Alfanumerisk, bindestrek, understrek og punktum | `<vm or service name>-pip`                  |
| Nettverk      | Lastbalanserer              | Ressursgruppe    | 1-80                      | Ikke skille mellom store og små bokstaver | Alfanumerisk, bindestrek, understrek og punktum | `<service or role>-lb`                      |
| Nettverk      | Lastbalanseringsregler      | Lastbalanserer   | 1-80                      | Ikke skille mellom store og små bokstaver | Alfanumerisk, bindestrek, understrek og punktum | `descriptive context`                       |

Tabellen under viser et eksempel på hvordan navnestrukturen for ressurser i Azure kan se ut.  

| Azure Ressurs      | Forkortelse   | Miljø         | Applikasjon, prosjekt eller funksjon    | Fullstendig navn for Ressurs                    |
|--------------------|---------------|---------------|-----------------------------------------|-------------------------------------------------|
| Virtul Machine     | vm            | utv           | analyseapplikasjon                      | analyseapplikasjon-utv-vm01                     |
| Load Balancer      | lb            | prod          | B024 (eksempel på prosjekt)             | b024-prod-lb01                                  |
| Piblic IP Address  | pip           | utv           | analyseapplikasjon                      | analyseapplikasjon-utv-pip01                    |
| Virtul Machine     | vm            | utv           | teamsbestilling                         | teamsbestilling-utv-vm01                        |
| Virtul Machine     | vm            | utv           | analyseapplikasjon                      | analyseapplikasjon-utv-vm02                     |


## Navnestandard for grupper i Entra ID (tidl. Azure Active Directory (AAD))

Entra ID, tidligere kjent som Azure Active Directory (AAD), er en skybasert identitets- og tilgangsstyringstjeneste som gir en rekke funksjoner for å administrere brukere og grupper i organisasjonen din. Grupper i Entra ID brukes til å administrere tilgang til ressurser ved å samle brukere som trenger lignende rettigheter. Hver gruppe kan ha en unik ID og kan være assosiert med spesifikke avdelinger, prosjekter eller funksjoner innen organisasjonen.

### Viktigheten rundt en konsekvent- og veldefinert navnestandard i Entra ID

En konsekvent og veldefinert navnestandard for grupper i Entra ID (tidligere Azure Active Directory) er avgjørende for flere grunner:

1. **Enklere Administrasjon**:
   - Klare og konsistente gruppenavn gjør det lettere for IT-administratorer å opprette, vedlikeholde og administrere grupper. Dette reduserer tiden og innsatsen som kreves for å håndtere brukertilgang og tillatelser.

2. **Forbedret Sikkerhet**:
   - Ved å bruke standardiserte navn kan du lettere identifisere og administrere sikkerhetsinnstillinger og tilgangskontroller. Dette bidrar til å redusere risikoen for feilkonfigurasjoner som kan føre til sikkerhetsbrudd.

3. **Bedre Oversikt og Organisering**:
   - Standardiserte navn gir en bedre oversikt over hvilke grupper som finnes, og deres tilhørende funksjoner eller avdelinger. Dette er spesielt nyttig i store organisasjoner med mange grupper.

4. **Effektiv Feilsøking**:
   - Når gruppenavnene klart indikerer deres formål og tilhørighet, blir det enklere å feilsøke problemer relatert til tilgang og rettigheter. Dette gjør det også lettere å gjennomføre revisjoner og kontrollere samsvar med retningslinjer.

5. **Skalerbarhet**:
   - En veldefinert navnestandard gjør det lettere å skalere IT-miljøet når organisasjonen vokser. Nye grupper kan enkelt opprettes og integreres i eksisterende systemer uten å skape forvirring eller konflikter.

6. **Redusert Risiko for Feil**:
   - En standardisert tilnærming minimerer risikoen for feil ved opprettelse og administrasjon av grupper. Dette bidrar til å sikre at riktige brukere har tilgang til riktige ressurser.

*Ved å implementere en standardisert navnekonvensjon for grupper i Entra ID, kan organisasjonen oppnå en mer effektiv og sikker administrasjon av brukerrettigheter og tilganger, samtidig som man sikrer samsvar med interne og eksterne retningslinjer og krav.*

## Forslag til navnestandard for grupper i Entra ID (tidl. Azure Active Directory (AAD))
























