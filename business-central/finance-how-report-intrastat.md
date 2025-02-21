---
title: Arbeide med Intrastat-rapportering
description: Lær hvordan du rapportere handel med selskaper i andre EU-land ved hjelp av Intrastat-systemet.
author: altotovi
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'electronic document, Intrastat, trade, EU, European Union'
ms.search.form: '308, 309, 310, 311, 325, 326, 327, 328, 405, 406, 4810, 4811, 8451, 12202, 31077'
ms.date: 09/02/2022
ms.author: altotovi
---
# <a name="work-with-intrastat-reporting" />Arbeide med Intrastat-rapportering

Alle selskaper i EU må rapportere handel med andre EU-land/-regioner. Varebevegelsen må hver måned rapporteres til statistikkmyndighetene i landet/regionen du bor i, og rapporten må leveres til skattemyndighetene. Intrastat er et system for innsamling av handelsstatistikk for varer i disse landene/regionene. Du bruker **Intrastat-rapport** til å fylle ut periodisk Intrastat-rapportering (vanligvis månedlig), samle inn, registrere og rapportere varer i henhold til lokal statlig lovgivning.

Intrastat-rapportering er basert på standard EU-bestemmelser som gjelder for alle land. Det er imidlertid noen forskjeller innen de enkelte landene i praksis. Hvert land har regler for hva som er nøyaktig og hvordan de rapporterer.

> [!IMPORTANT]
> Denne artikkelen beskriver den nye Intrastat-opplevelsen som er tilgjengelig i [!INCLUDE[prod_short](includes/prod_short.md)] med oppstart i lanseringsbølge 2 i 2022, som inkluderer utvidede funksjoner og [må slås på for eksisterende selskaper](finance-how-setup-report-intrastat.md#enable-the-new-intrastat-experience). Kontakt systemansvarlig for å slå på og konfigurere den nye funksjonen.
>
> Les den forrige versjonens Intrastat-oppsett og bruksartikkel på [Konfigurere og rapportere Intrastat](finance-how-setup-report-intrastat-v20.md).

> [!NOTE]
> Intrastat-informasjon gjelder ikke flytting av tjenester mellom land, men bare varer (varer og aktiva). Hvis den lokale regjeringen krever at du må registrere flytting av tjenester mellom land, kan du gjøre det ved å bruke funksjonen for **Tjenestedeklarasjon**.
>
> Vi forventer at denne funksjonen er tilgjengelig fra november 2022 som en app på [AppSource](https://go.microsoft.com/fwlink/?linkid=2081646). Når du skal bruke det, må du først installere det på siden **Administrasjon av utvidelse**.

## <a name="fill-in-the-intrastat-report" />Fyll ut rapporten Intrastat

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angir **Intrastat-liste** og velger den relaterte koblingen.
2. Velg **Ny** for å opprette en ny **Intrastat-rapport**.
3. Hvis du må angi noen interne opplysninger om **Intrastat-rapporten**, fyller du ut disse opplysningene i feltet **Beskrivelse**.
4. Angi hvilken måned du vil rapportere data for, i feltet **Statistisk periode**. Angi perioden som et firesifret tall uten mellomrom eller symboler. Avhengig av landet, angir du enten måneden først og deretter året, eller omvendt. Angi for eksempel *2206* eller *0622* for juni 2022.
5. Velg handlingen **Foreslå linjer**. Feltene **Startdato** og **Sluttdato** inneholder allerede datoene som er angitt for statistikkperioden på Intrastat-rapporthodet.
6. I feltet **Kostregulerings-%** kan du angi en prosentandel som skal dekke transport og forsikring. Hvis du angir en prosent, blir innholdet i feltet **Statistikkverdi** i kladden proporsjonalt høyere. Men hvis du vil bruke denne funksjonen, må du endre feltet **Beløp inkl. varegebyr** til **Ja**.
7. Du kan til slutt definere ekstra konfigurasjoner i den **Tillegg**-hurtigfanen:
   1. **Hopp over omberegning for nullbeløp** for å angi at linjer uten beløp skal beregnes på nytt i løpet av kjørselen.
   2. **Hopp over nullbeløp** for å angi at vareposter uten beløp ikke blir inkludert i kjørselen.
   3. **Vis varegebyrposter** for å angi om du vil vise direkte kostnader som selskapet har tilordnet og bokført som varegebyrer.
   4. **Hopp over ikke-fakturerte poster** for å angi om vareposter som er levert eller mottatt, men ennå ikke fakturert, må ekskluderes fra prosessen.
8. Velg **OK** når du vil starte den satsvise jobben.

Kjørselen henter alle varepostene i statistikkperioden og setter dem inn som linjer i **Intrastat-rapport**-linjene. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## <a name="modify-the-intrastat-report" />Endre rapporten Intrastat

Om nødvendig kan du endre linjene, men når du endrer en verdi på linjen i Intrastat-rapporten, vil feltet **Korreksjon** automatisk merkes som **Ja**. Til slutt kan du legge til en ny linje manuelt hvis det er en årsak til det. Slik legger du til en ny linje manuelt:

1. På siden **Intrastat-rapport** velger du **Ny linje**-handlingen i hurtigfanen **Linjer**.
2. Velg **Mottak** eller **Forsendelse** i feltet **Type**.
3. I feltet **Kildetype** velger du én eller flere kilder: **Varepost**, **Aktivapost** eller **Prosjektpost**.
4. Basert på **Kildetype** i **Varenr.** -feltet kan du velge en **Vare** (i begge tilfeller **Varepost** eller **Prosjektpost**) eller **Aktiva**.
5. Fyll ut andre felt når du har behov for Intrastat-rapportering.

> [!NOTE]
> Når du manuelt legger til en ny linje i Intrastat-rapporten, må **Dato**-feltet på linjen være innenfor **Statistisk periode**-området du la til i hodet.

## <a name="validate-intrastat-lines" />Validere Intrastat-linjer

Når du har fylt ut **Intrastatkladden**, kan du kjøre handlingen **Sjekklisterapport** for å være sikker på at at all informasjon i **Intrastat-rapport** er riktig. Obligatoriske felt du har angitt på siden **Sjekkliste for Intrastat-rapport** som mangler verdier, vises i faktaboksen **Feil og advarsler** på siden **Intrastatkladd**.

Kjør rapporten **Sjekkliste for Intrastat-rapport** for å kontrollere Intrastat-linjer før de eksporteres til det nødvendige formatet. Sjekken kjøres i **Intrastat-rapport**.

## <a name="recalculating-weight-or-supplementary-unit-of-measure" />Omberegne vekt eller supplerende enhet

Hvis du fikk feilmeldingen *"Total vekt" i Intrastat-rapportens linje kan ikke være tom*, er det sannsynlig at du ikke har satt feltet **Nettovekt** i den brukte kilden, varen eller aktivaet. I dette tilfellet kan du søke etter vare- eller aktivakortet og legge til den nødvendige verdien. Deretter trenger du bare å åpne **Intrastat-rapporten** på nytt og følge disse trinnene:

1. Velg **Beregn vekt/tilleggsenhet på nytt**-handlingen for å omberegne **Total vekt** og/eller **Tilleggsantall**.
2. Velg ett av alternativene:

    1. **Vekt** – for å beregne bare **Total vekt** på nytt basert på gjeldende informasjon om **Nettovekt** på varen og aktivakortet.
    2. **Antall tilleggsenheter** – for å omberegne bare **Tilleggsantall** på **Intrastat-rapport**-linjen hvis det finnes, basert på gjeldende informasjon om **Tilleggsenhet** på vare- og aktivakortet.
    3. **Begge** – for å beregne både **Total vekt** og **Tilleggsantall** basert på gjeldende informasjon om vare- og aktivakortet.
3. Velg **OK** når du vil starte den satsvise jobben.

## <a name="report-intrastat-in-a-file" />Rapportere Intrastat i en fil

Du kan sende Intrastat-rapporten som en fil basert på kravene til lokale myndigheter. Før du oppretter filen, må du kjøre **Sjekklisterapport** for å kontrollere om alle linjene inneholder alle nødvendige og gyldige opplysninger. Slik oppretter du en fil:

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angir **Intrastat-liste** og velger den relaterte koblingen.
2. Velg **Intrastat-rapport** du vil rapportere som en fil.
3. Hvis du ikke allerede har gjort dette, fyller du ut **Intrastat-rapport** manuelt eller velger **Foreslå linjer**.
4. Velg handlingen **Opprett fil**.
5. Intrastat-filen lagre i påkrevd format.

Når du har opprettet filen, vil [!INCLUDE[prod_short](includes/prod_short.md)] automatisk fylle ut følgende detaljer om rapportering:

* **Eksportdato** for å angi datoen da rapporten ble eksportert.
* **Eksporttidspunkt** for å angi tiden da rapporten ble eksportert.

> [!NOTE]
> Neste gang du oppretter en fil, vil feltene **Eksportdato** og **Eksporttidspunkt** bare vise informasjon om den siste filen du opprettet.

## <a name="intrastat-rules" />Intrastat-regler

### <a name="grouping-lines" />Grupperingslinjer

I **Intrastat-rapport**-linger kan det ikke grupperes etter noen felt. Alle postene kopieres fra den opprinnelige kilden, slik at du raskt kan finne dem basert på kombinasjonen av **Kildetype** og **Kildeløpenr**.

Gruppering som kreves av myndighetene, vil bli oppgitt i den eksporterte filen. Du må konfigurere denne i **Datautvekslingsdefinisjonen**, som kan konfigureres fullstendig. Finn ut mer under [Definere datautvekslingsdefinisjoner](across-how-to-set-up-data-exchange-definitions.md).

### <a name="fixed-assets-reporting" />Aktivarapportering

Aktiva vil bare bli vist på Intrastat-linjene hvis:

* **Aktivabokf.type** i **Mva-post** -feltet er **Anskaffelseskost** og hvis **Dokumenttype** er **Faktura** ved kjøp og
* **Aktivabokf.type** i **Mva-post** -feltet er **Overskudd ved salg** og hvis **Dokumenttype** er **Faktura** ved salg.

### <a name="intrastat-report-statuses" />Status for Intrastat-rapport

Når du arbeider med **Intrastat-rapporten**, vil du se **Status**-felt i dokumenthodet. Du kan finne følgende status sammen med tilknyttede regler:

* *Åpne*: Denne statusen opprettes automatisk når du oppretter en ny Intrastat-rapport, og du kan utføre alle operasjoner i denne statusen.
* *Utgitt*: [!INCLUDE[prod_short](includes/prod_short.md)] endrer automatisk statusen til *Frigitt* når du oppretter en fil. Fra dette tidspunktet kan du ikke endre **Intrastat-rapporten**. Hvis du må endre noe og en rapport på nytt, kan du bruke handlingen **Åpne på nytt** til å åpne Intrastat-rapporten på nytt. Når dokumentet er åpnet på nytt, kan du bruke **Frigi**-handlingen til å frigi dokumentet.
* **Rapportert**: Angir om posten allerede er rapportert til skattemyndighetene. Dette er ikke en vanlig status, men et selvstendig felt, og selv om du åpnet Intrastat-rapporten på nytt, ville den fortsatt vise at filen allerede er opprettet for denne rapporten.

## <a name="see-related-training-at-microsoft-learnlearnmodulesprocess-intrastat-dynamics-365-business-centralindex" />Se relatert opplæring på [Microsoft Learn](/learn/modules/process-intrastat-dynamics-365-business-central/index).

## <a name="see-also" />Se også

[Definer Intrastat-rapportering](finance-how-setup-report-intrastat.md)  
[Økonomistyring](finance.md)  
[Arbeid med [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
