---
title: Betale med AMC Banking (USA) eller SEPA-kredittoverføring (EU)
description: Behandle betalinger til leverandører ved å eksportere en fil (EFT) sammen med betalingsinformasjonen fra kladdelinjene.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.search.form: '256, 1205, 1206, 1209, 10810, 10811'
ms.date: 07/06/2021
ms.author: bholtorf
---
# <a name="make-payments-with-the-amc-banking-365-fundamentals-extension-or-sepa-credit-transfer" />Betale med AMC Banking 365 Fundamentals-utvidelsen eller SEPA-kredittoverføring

Nå kan du behandle betalinger til leverandører på siden **Betalingskladd** ved å eksportere en fil sammen med betalingsinformasjonen fra kladdelinjene. Du kan deretter laste opp filen til nettbanken der de relaterte pengeoverføringene behandles. [!INCLUDE[prod_short](includes/prod_short.md)] støtter formatet for SEPA-kreidttoverføring, men andre formater for elektroniske betalinger kan være tilgjengelige i ditt land/region.

> [!NOTE]
> I den generelle versjonen av [!INCLUDE[prod_short](includes/prod_short.md)] er det konfigurert og koblet til en global tjenesteleverandør for å konvertere bankdata til hvilket som helst format banken krever. I versjonene for Nord-Amerika kan den samme servicen brukes til å sende betalingsfiler som elektronisk pengeoverføring (EFT), for eksempel det ofte brukte ACH-nettverket (Automated Clearing House), men med en litt annerledes prosess. Se trinn 6 i [Slik eksporterer du betalinger til en bankfil](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#to-export-payments-to-a-bank-file).  

 Hvis du vil gjøre det mulig å foreta SEPA-kredittoverføringer, må du først opprette en bankkonto, en leverandør og finanskladden som utbetalingskladden er basert på. Deretter gjør du klar betalinger til leverandører ved å fylle ut siden **Betalingskladd** med forfalte betalinger som har angitte bokføringsdatoer.  

> [!NOTE]  
> Når du har bekreftet at betalingene er behandlet av banken, kan du begynne å bokføre utbetalingskladdelinjene.  

## <a name="setting-up-the-amc-banking-365-fundamentals-extension" />Konfigurere AMC Banking 365 Fundamentals-utvidelsen

Aktiver utvidelsen AMC Banking 365 Fundamentals for å konvertere en kontoutdragsfil til et format du kan importere, eller konvertere den eksporterte betalingsfilen til formatet som banken krever. Hvis du vil ha mer informasjon, kan du se [Bruk AMC Banking 365 Fundamentals-utvidelsen](ui-extensions-amc-banking.md).

## <a name="setting-up-sepa-credit-transfer" />Definere SEPA-kredittoverføring

Fra siden **Utbetalingskladd** kan du eksportere betalinger til en fil for opplasting til den elektroniske banken for behandling av relaterte pengeoverføringer. [!INCLUDE[prod_short](includes/prod_short.md)] støtter formatet for SEPA-kreidttoverføring, men andre formater for elektroniske betalinger kan være tilgjengelige i ditt land/region.  

Du kan gjøre det mulig å eksportere et bankfilformat som ikke støttes som standard i [!INCLUDE[prod_short](includes/prod_short.md)], ved å definere en datautvekslingsdefinisjon ved hjelp av rammeverket for datautveksling. Hvis du vil ha mer informasjon, kan du se [Definere datautvekslingsdefinisjoner](across-how-to-set-up-data-exchange-definitions.md)  

Før du kan behandle betalingen elektronisk ved å eksportere betalingsfiler i formatet for SEPA-kredittoverføring, må du utføre følgende konfigureringstrinn:  

* Definer den aktuelle bankkontoen slik at den kan håndtere SEPA-kredittoverføringsformatet.  
* Definer leverandørkort slik at betalinger behandles ved å eksportere filer i SEPA-kredittoverføringsformatet.  
* Definer den tilknyttede finanskladden slik at betalingseksport kan utføres fra siden **Utbetalingskladd**.  
* Knytt datautvekslingsdefinisjon for én eller flere betalingstyper til de(n) aktuelle betalingsmåten(e):  

> [!TIP]
> Denne artikkelen gjelder den generelle versjonen av [!INCLUDE [prod_short](includes/prod_short.md)]. I ditt land eller din region kan flere nødvendige felt ha blitt lagt til på de ulike sidene. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

### <a name="to-set-up-a-bank-account-for-sepa-credit-transfer" />Slik oppretter du en bankkonto for SEPA-kredittoverføring:

1. Skriv inn **Bankkontoer** i **Søk**-boksen, og velg deretter den relaterte koblingen.  
2. Åpne kortet for bankkontoen som du vil eksportere betalingsfiler fra, i formatet for SEPA-kredittoverføring.  
3. I hurtigfanen **Overfør** i feltet **Betalingseksportformat** velger du **SEPACT**.  
4. I hurtigfanen **Generelt** i feltet **Numre på kredittoverføringsmeldinger**, velger du en nummerserie som tilordnes til SEPA-kreditoverføringer.  
5. Kontroller at **IBAN**-feltet er utfylt.  

    > [!NOTE]  
    > **EUR** må angis i **Valutakode**-feltet fordi SEPA-kredittoverføringer bare kan foretas i euro.  

### <a name="to-set-up-a-vendor-card-for-sepa-credit-transfer" />Slik oppretter du et leverandørkort for SEPA-kredittoverføring:

1. Skriv inn **Leverandører** i **Søk**-boksen, og velg deretter den relaterte koblingen.  
2. Åpne kortet for leverandøren som du vil betale elektronisk, ved å eksportere betalingsfiler i formatet for SEPA-kredittoverføring.  
3. Velg **BANK** i hurtigfanen **Betaling** i feltet **Betalingsmåte - kode**.  
4. I feltet **Foretrukket bankkonto** velger du banken som pengene skal overføres til når den behandles av den elektroniske banken.  

    Hvis du ennå ikke har definert en bank for denne leverandøren, kan du gjøre det nå. Hvis du vil ha mer informasjon, kan du se [Definere bankkonti for eksport av bankfiler](bank-how-setup-bank-accounts.md#to-set-up-vendor-bank-accounts-for-export-of-bank-files). Verdien i feltet **Foretrukket bankkonto** overføres til feltet **Mottakerbankkonto** på siden **Utbetalingskladd**.  

### <a name="to-set-the-payment-journal-up-to-export-payment-files" />Slik definerer du utbetalingskladden for eksport av betalingsfiler:

1. Skriv inn **Utbetalingskladder** i **Søk**-boksen, og velg deretter den relaterte koblingen.  
2. Velg rulle\-gardinknappen i **Bunkenavn**-feltet.  
3. På siden **Finanskladder** velger du handlingen **Rediger liste**.  
4. På linjen for utbetalingskladden du vil bruke til å eksportere betalinger, merker du av for **Tillat betalingseksport**.  

### <a name="to-connect-the-data-exchange-definition-for-one-or-more-payment-types-with-the-relevant-payment-method-or-methods" />Slik knytter du datautvekslingsdefinisjon for én eller flere betalingstyper til de(n) aktuelle betalingsmåten(e):

1. Skriv inn **Betalingsmåter** i **Søk**-boksen, og velg deretter den relaterte koblingen.  
2. På siden **Betalingsmåter** velger du betalingsmåten som brukes til å eksportere betalinger fra, og deretter velger du feltet **Definisjon av betalingseksportlinje**.  
3. På siden **Definisjoner av betalingseksportlinje** velger du koden du angav i **Kode**-feltet på hurtigfanen **Linjedefinisjoner** i trinn 4 i delen "Slik beskriver du formateringen av linjer og kolonner i filen" i fremgangsmåten [Definere datautvekslingsdefinisjoner](across-how-to-set-up-data-exchange-definitions.md).  

## <a name="preparing-the-payment-journal" />Klargjøre utbetalingskladden

Fylle ut utbetalingskladden med linjer for utestående leverandørfordringer, med mulighet til å sette inn bokføringsdatoer basert på forfallsdatoen til de relaterte kjøpsdokumentene. Hvis du vil ha mer informasjon, kan du se [Administrere skyldige beløp](payables-manage-payables.md).

## <a name="exporting-payments-to-a-bank-file" />Eksportere betalinger til en bankfil

Når du er klar til å utføre betalinger til leverandører eller refusjoner til de ansatte, kan du eksportere en fil med betalingsinformasjonen for linjene på siden **Betalingskladd**. Du kan deretter laste opp filen til banken for å behandle de relaterte pengeoverføringene.

AMC Banking 365 Fundamentals-utvidelsen er tilgjengelig i den generelle versjonen av [!INCLUDE[prod_short](includes/prod_short.md)]. I Nord-Amerika-versjoner kan den samme utvidelsen brukes til å sende betalingsfiler som elektronisk pengeoverføring (EFT), men med en litt annen prosess. Se trinn 6 i [Slik eksporterer du betalinger til en bankfil](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#to-export-payments-to-a-bank-file).

> [!NOTE]  
> Før du kan eksportere betalingsfiler fra betalingsjournalen, må du angi det elektroniske formatet for bankkontoen som er involvert, og du må aktivere AMC Banking 365 Fundamentals-utvidelsen. Hvis du vil ha mer informasjon, kan du se [Konfigurere bankkontoer](bank-how-setup-bank-accounts.md) og [Bruk AMC Banking 365 Fundamentals-utvidelsen](ui-extensions-amc-banking.md). I tillegg må du merke av for **Tillat betalingseksport** på siden **Finanskladder**. Hvis du vil ha mer informasjon, kan du se [Arbeide med finanskladder](ui-work-general-journals.md).  

Du bruker siden **Kredittoverføringsregistre** til å vise betalingsfilene som er eksportert fra betalingskladden. Fra denne siden kan du også eksportere betalingsfiler på nytt ved tekniske feil eller endringer. Vær oppmerksom på at eksporterte EFT-filer vises ikke på denne siden, og kan ikke være eksportert på nytt.  

### <a name="to-export-payments-to-a-bank-file" />Slik eksporterer du betalinger til en bankfil:

Nedenfor beskrives hvordan du betaler en leverandør med sjekk. Fremgangsmåten er lik refusjon til kunde med sjekk.

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Utbetalingskladder** og velg den relaterte koblingen.
2. Fyll ut utbetalingskladdelinjene. Hvis du vil ha mer informasjon, kan du se [Registrere betalinger og refusjoner](payables-how-post-payments-refunds.md).

    > [!NOTE]
    > Hvis du bruker EFT, må du velge enten **Elektronisk betaling** eller **Elektronisk betaling-IAT** i feltet **Bankbetalingstype**. Andre fileksporttjenester og formater krever ulike oppsettsverdier på siden **Bankkort** og **Leverandørs bankkort**. Du blir informert om feil eller manglende oppsettsverdier når du prøver å eksportere filen.
    >
    > EFT-funksjonen kan bare brukes for bankkonti i lokal valuta. Den kan ikke brukes med utenlandsk valuta, angitt med en verdi i feltet **Valutakode**. (Tom feltverdi betyr lokal valuta.)

3. Når du har fullført alle betalingskladdlinjene, velger du **Eksporter**.
4. På siden **Eksporter elektroniske betalinger** fyller du ut feltene etter behov.

    Eventuelle feilmeldinger vises i faktaboksen **Feil i betalingsfil**, der du også kan velge en feilmelding hvis du vil ha mer informasjon. Du må løse alle feil før betalingsfilen kan eksporteres.

    > [!TIP]  
    > Når du bruker AMC Banking 365 Fundamentals-utvidelsen, kan du få en vanlig feilmelding om at bankkontonummeret ikke har lengden som banken krever. Du kan unngå eller løse feilen ved å fjerne verdien i **IBAN**-feltet på siden **Bankkort** og deretter angi et bankkontonummer i formatet som banken krever, i feltet **Bankkontonr.**

5. På siden **Lagre som** angir du plasseringen som filen som blir eksportert til, og deretter velger du **Lagre**.

    > [!NOTE]  
    > Hvis du bruker EFT, lagrer du det resulterende remitteringsskjemaet for leverandører som et Word-dokument, eller du velger at det skal sendes direkte til leverandøren via e-post. Betalingene er nå lagt til på siden **Generer EFT-fil**, og derfra kan du generere flere betalingsordrer sammen for å spare overføringskostnader. Hvis du vil ha mer informasjon, kan du se følgende trinn.
6. På siden **Utbetalingskladd** velger du **GenerereEFT-fil**.

    På siden **Generer EFT-fil** vises alle betalinger som er definert for EFT som du har eksportert fra utbetalingskladden for en bestemt bankkonto, men som ennå ikke er generert på hurtigfanen **Linjer**.
7. Velg **Generer EFT-fil** for å eksportere en fil for alle EFT-betalinger.
8. På siden **Lagre som** angir du plasseringen som filen som blir eksportert til, og deretter velger du **Lagre**.

Bankbetalingsfilen eksporteres til plasseringen du angir, og du kan deretter laste den opp til nettbankkontoen og foreta de faktiske betalingene. Deretter kan du bokføre den eksporterte betalingen journallinjer.

### <a name="to-plan-when-to-post-exported-payments" />Planlegge når du bokfører eksporterte betalinger

Hvis du ikke vil bokføre en utbetalingskladdelinje for en eksportert betaling, for eksempel fordi du venter på bekreftelse på at transaksjonen er behandlet av banken, kan du bare slette kladdelinjen. Når du senere oppretter en utbetalingskladdelinje for å betale restbeløpet på fakturaen, viser feltet **Totalt eksportert beløp** hvor mye av betalingsbeløpet som allerede er eksportert. Du kan også finne detaljert informasjon om det eksporterte totalbeløpet ved å velge knappen **Poster i kredittoverføringsreg.** for å vise mer informasjon om eksporterte betalingsfiler.

Hvis du følger en prosess der du ikke bokfører betalinger før du har fått bekreftelse på at de har blitt behandlet i banken, kan du kontrollere dette på to måter.

* I en betalingskladd med foreslåtte betalingslinjer kan du sortere etter kolonnen **Lest ut til betalingsfil** eller **Totalt eksportert beløp**, og deretter slette betalingsforslag for åpne fakturaer som allerede er betalt og du ikke ønsker å betale.
* Du kan merke av for **Hopp over eksporterte betalinger** på siden **Betalingsforslag - leverandør**, der du angir hvilke betalinger som skal settes inn i utbetalingskladden, hvis du ikke vil sette inn kladdelinjer for betalinger som allerede er eksportert.

Du kan vise informasjon om eksporterte betalinger ved å velge handlingen **Historikk for betalingseksport**.

### <a name="to-re-export-payments-to-a-bank-file" />Eksportere betalinger til en bankfil på nytt

Du kan eksportere betalingsfiler på nytt fra siden **Kredittoverføringsregistre**. Før du sletter eller bokfører utbetalingskladdelinjer, kan du også eksportere betalingsfilen på nytt fra siden **Betalingskladd**. Hvis du har slettet eller bokført utbetalingskladdelinjer etter at du har eksportert dem, kan du eksportere samme betalingsfil på nytt fra siden **Kredittoverføringsregistre**. Velg linjen for bunken med kredittoverføringer du vil eksportere på nytt, og bruk handlingen **Eksporter betalinger til fil på nytt**.

> [!NOTE]  
> Eksporterte EFT-filer vises ikke på siden **Kredittoverføringsregistre** og kan ikke eksporteres på nytt.

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Kredittoverføringsregistre**, og velg deretter den relaterte koblingen.
2. Velg en betalingseksport som du vil eksportere på nytt, og velg deretter **Eksporter betaling til fil på nytt**.

## <a name="posting-the-payments" />Bokføring av betalinger

Bokfør betalingene når den elektroniske betalingen er behandlet av banken. Hvis du vil ha mer informasjon, kan du se [Utføre betalinger](payables-make-payments.md).

## <a name="see-also" />Se også

[Bruk utvidelsen AMC Banking 365 Fundamentals](ui-extensions-amc-banking.md)  
[Administrere skyldige beløp](payables-manage-payables.md)  
[Arbeid med finanskladder](ui-work-general-journals.md)  
[Innkrev betalinger med SEPA direct debit](finance-collect-payments-with-sepa-direct-debit.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
