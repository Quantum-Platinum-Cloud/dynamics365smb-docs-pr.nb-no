---
title: Registrere forbruk eller forbruk av prosjektressurser og -varer
description: Denne artikkelen beskriver hvordan du registrerer forbruket av varer eller ressurser på prosjekter i prosjektstyring.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics365-business-central
ms.topic: how-to
ms.date: 12/20/2022
ms.custom: bap-template
---
# <a name="record-consumption-or-usage-for-jobs" />Registrere forbruk eller forbruk for prosjekter

På siden **Prosjektkort** kan du åpne siden **Prosjektplanleggingslinjer** for å se gjennom og registrere bruk på forskjellige deler av prosjektet. Denne informasjonen oppdateres automatisk når du endrer og overfører informasjon mellom prosjekter og prosjektkladder eller prosjektfakturaer. Dette krever at du har slår på **Bruk forbrukskobling som standard** på siden **Prosjektoppsett**. Finn ut mer under [Definer prosjekter](projects-how-setup-jobs.md).  

<!-- Not really sure what this paragraph is saying, or why we start with it. Why do you transfer information between jobs and job journals or job invoices? I get the use of resources and items, but what about G/L account and Text?

On the Jobs Setup page there's an Apply Usage Link by Default toggle. Guessing that's what we're referring to -->

For planleggingslinjer av typen **Budsjett** kan du for eksempel angi antallet for en ressurs og antallet som skal overføres til prosjektkladden. Hvis planleggingslinjetypen er **Fakturerbar**, kan du angi antallet for ressursen og angi antallet som skal overføres til en faktura. Gå til [Fakturer prosjekter](projects-how-invoice-jobs.md) hvis du vil ha mer informasjon om hvordan du fakturerer kunder. Når du sammenligner det opprinnelige antallet, restantallet eller det bokførte antallet, kan du raskt se gjennom bruksinformasjon. Hvis du vil ha informasjon om hvordan du estimerer budsjetterte verdier under planleggingen, kan gå til [Administrer prosjektbudsjetter](projects-how-manage-budgets.md).  

De følgende fremgangsmåtene viser hvordan du registrerer faktiske (budsjetterte) antall og kostnader i en prosjektkladd. Du kan alternativt bruke kjøpsdokumenter til å registrere kjøp for et prosjekt. Finn ut mer under [Administrer prosjektforsyninger](projects-how-manage-project-supplies.md).

## <a name="to-record-usage-for-a-job-planning-line-of-type-budget" />Slik registrerer du forbruk for en prosjektplanleggingslinje av typen Budsjett

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Prosjekter** og velg den relaterte koblingen.  
2. Velg prosjektet, og velg deretter handlingen **Prosjektplanleggingslinjer**. 
3. Velg en prosjektplanleggingslinje av typen **Budsjett** eller **Både Budsjett og fakturerbar** som du vil registrere forbruk for.   

    > [!NOTE]
    > Du kan også registrere forbruk for en prosjektplanleggingslinje av typen **Fakturerbar**. Du bruker vanligvis disse linjene til å opprette fakturaer, men du kan også overføre informasjonen en kladd. Finn ut mer under [Fakturer prosjekter](projects-how-invoice-jobs.md) <!--However, when you do that, a job planning line of type **Budget** is created to match the billable line. For more information, see [Manage Job Budgets](projects-how-manage-budgets.md).-->

4. Angi antallet du vil overføre til fakturaen, i feltet **Ant. som skal overføres til kladd**. Standardantallet er verdien du angir i feltet **Antall**.

    Feltet **Restantall** viser antallet som gjenstår for å fullføre prosjektet og overføres til kladden. <!--Should we mention that this field is not shown by default, and that if they want to use it they must add it?--> 
5. Velg handlingen **Opprett prosjektkladdelinjer**.

    > [!TIP]
    > Hvis du vil legge til flere planleggingslinjer for prosjektet, venter du med dette trinnet til du har lagt til alle prosjektplanleggingslinjer.
6. På siden **Prosjekt – overfør til prosjektplanleggingslinje** fyller du ut feltene etter behov, og deretter velger du **OK**-knappen. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
7. Velg handlingen **Åpne prosjektkladd**.  
8. På siden **Prosjektkladd** velger du den relevante linjen, og deretter velger du handlingen **Bokfør**.
9. På siden **Prosjektplanleggingslinjer** går du gjennom det registrerte forbruket ved å kontrollere feltene **Antall**, **Restantall** og **Ant. som skal overføres til kladd**.  
10. Gjenta trinn 3 til 8 for å registrere ekstra forbruk.  

## <a name="to-create-job-journal-lines-manually" />Slik oppretter du prosjektkladdelinjer manuelt:

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Prosjektkladder**, og velg deretter den relaterte koblingen.  
2. Velg et navn for den relevante prosjektkladden i feltet **Bunkenavn**.  
3. Angi bilagsnummer, prosjektnummer, prosjektoppgavenummer, type og antall for typen som forbrukes, på en ny linje.  
4. Når prosjektkladdelinjene er fullført, kan du velge handlingen **Bokfør**.  

## <a name="to-view-job-usage-estimates-and-post-updates" />Slik viser du prosjektforbruksestimater og bokfører oppdateringer

Du kan vise prosjektforbruk i ett trinn helt frem til et prosjekt er fullført. Det gjør du ved å bruke kjørselen **Beregn gjenstående forbruk for prosjekt** for alle oppgavene til og med avslutningen av prosjektet.  

Dermed kan du spore og sammenligne opprinnelige estimater med faktiske resultater og om nødvendig gjøre endringer eller opprette nye poster. Tenk deg at du har estimert at et prosjekt tar 10 timer, men frem til nå har det tatt 15 timer. Du kan da legge til de fem ekstra timene på den eksisterende kladdelinjen, eller du kan opprette en ny kladdelinje for å rapportere disse fem timene som overtid, som er en annen arbeidstype. Riktig kost og pris beregnes, og du kan deretter bokføre i kladden.  

> [!NOTE]  
> Vareposter oppretter vareposter og reduserer lagerantallet. Kjørselen **Bokfør lagerkost i Finans** overfører kosten fra lager til Finans. For ressurser opprettes ressursposter.  

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Prosjektkladder**, og velg deretter den relaterte koblingen.  
2. Velg en journal for det aktuelle prosjektet, og velg deretter handlingen **Beregn gjenstående forbruk**.  
3. På siden **Beregn gjenstående forbruk for prosjekt** skriver du inn dokumentnummeret og bokføringsdatoen som skal settes inn i kladden, og deretter velger du **OK**-knappen.  
4. Oppdater journalen med eventuelle endringer som kreves.  
5. Velg **Bokfør**.

## <a name="create-inventory-and-warehouse-pick-documents-for-a-job" />Opprett lager- og lagerplukkdokumenter for et prosjekt

Hvis du vil opprette lager- og lagerplukkdokumenter for prosjekter, må administratoren aktivere **Funksjonsoppdatering: Aktiver lager og lagerplugg fra prosjekter** på **Funksjonsstyring**-siden.

Funksjonen legger til handlingene **Opprett lagerplukk** og **Opprett lagerplukk** i **prosjektkortet**. Når du skal opprette eller registrere et plukkdokument, bruker du handlingene **Plassering/plukklinjer/flyttingslinjer** eller **Registrerte plukklinjer**. Finn ut mer under [Flyter for produksjon, montering og prosjekter](design-details-internal-warehouse-flows.md).

Du kan bruke handlingene under følgende betingelser:

* **Statusen** for jobben er **åpen**.
* **Linjetypen** på prosjektplanleggingslinjen er **Budsjettert** eller både **Budsjettert og fakturerbart**.
* **Typen** prosjektplanleggingslinje er **vare**.
* **Plukk nødv.** må være aktivert for den tilknyttede lokasjonen.
* **Bruk Lagerstyring** er deaktivert.

> [!NOTE] 
> Selv om innstillingen er kalt **Plukk nødv.**, kan du likevel bokføre forbruk direkte fra prosjektkladdelinjen for lokasjonen. Hvis lokasjonen er definert for å kreve plukkbehandling, men ikke leveringsbehandling, bruker du siden **Lagerplukk** til å organisere og skrive ut plukkinformasjonen. Du kan også bruke siden til å angi og bokføre resultatet av plukkingen, som igjen bokfører forbruket av varene. 
> 
> Hvis du har definert lokasjonen til å kreve både plukk- og leveringsbehandling, det vil si at du har valgt både feltene **Plukk nødv.** og **Levering nødv.** på siden **Lokasjonskort**, bruker du siden **Plukk** til å håndtere plukkingen. Plukkinger ligner på lager lagerplukk. Forskjellen er at i stedet for å bokføre plukkinformasjonen, registrerer du plukkingen. Denne registreringen bruker ikke forbruk, den bare gjør varene tilgjengelige for bokføring. Som lagerleder kan du bruke plukkforslag til å organisere opplysninger om plukking før du oppretter de enkelte plukkinstruksjonene

## <a name="to-review-planning-lines-for-a-job-ledger-entry" />Slik går du gjennom planleggingslinjene for en prosjektpost

Etter at du har bokført prosjektkladdelinjer kan du vise planleggingslinjene som er knyttet til prosjektpostene som er bokført.

> [!NOTE]  
> Dette krever at det er merket av for **Bruk forbrukskobling** for prosjektet. Hvis du vil ha mer informasjon, kan du se [Konfigurere prosjekter](projects-how-setup-jobs.md).  

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Prosjektkladder**, og velg deretter den relaterte koblingen.  
2. Velg en kladd for det aktuelle prosjektet, og velg deretter handlingen **Poster**.  
3. På siden **Prosjektposter** velger du handlingen **Vis koblede prosjektplanleggingslinjer**.

## <a name="see-related-microsoft-trainingtrainingpathspost-job-usage-sales" />Se relatert [Microsoft-opplæring](/training/paths/post-job-usage-sales/)

## <a name="see-also" />Se også

[Prosjektstyring](projects-manage-projects.md)  
[Finans](finance.md)  
[Innkjøp](purchasing-manage-purchasing.md)  
[Salg](sales-manage-sales.md)  
[Arbeid med [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
