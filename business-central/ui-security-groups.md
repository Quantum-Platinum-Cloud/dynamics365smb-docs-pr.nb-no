---
title: Styr tilgang ved hjelp av sikkerhetsgrupper
description: Denne artikkelen beskriver hvordan du bruker sikkerhetsgrupper til å definere brukertillatelser.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 'access, right, security, permissions'
ms.search.form: '1, 119, 8930, 9800, 9807, 9808, 9830, 9831, 9802, 9855, 9862'
ms.date: 02/08/2023
---

# Styr tilgang til Business Central ved å bruke sikkerhetsgrupper

Sikkerhetsgrupper gjør det enklere for administratorer å håndtere brukertillatelser. For nettversjonen av [!INCLUDE [prod_short](includes/prod_short.md)] kan de for eksempel brukes på nytt på tvers av Dynamics 365-programmer, som SharePoint Online, CRM Online og [!INCLUDE [prod_short](includes/prod_short.md)]. Administratorer legger til tillatelser i [!INCLUDE [prod_short](includes/prod_short.md)]-sikkerhetsgruppene, og når de legger til brukere i gruppen, gjelder tillatelsene for alle medlemmer. En administrator kan for eksempel opprette en [!INCLUDE [prod_short](includes/prod_short.md)]-sikkerhetsgruppe som gir selgere muligheten til å opprette og bokføre ordrer. Eller du kan la innkjøpere gjøre det samme for bestillinger.

## Business Central Online og lokal

Du kan bruke sikkerhetsgrupper for nettversjonene og de lokale versjonene av [!INCLUDE [prod_short](includes/prod_short.md)]. Opprett grupper på en av følgende måter, avhengig av versjonen:

* For nettversjonen bruker du Azure Active Directory-sikkerhetsgrupper. Hvis du vil ha mer informasjon om hvordan du oppretter gruppen, kan du gå til [Opprett, rediger eller slett en sikkerhetsgruppe i administrasjonssenteret for Microsoft 365](/microsoft-365/admin/email/create-edit-or-delete-a-security-group).
* For lokal versjoner bruker du Windows Active Directory-grupper. Hvis du vil lære mer, kan du gå til [Opprett en gruppekonto i Active Directory](/windows/security/operating-system-security/network-security/windows-firewall/create-a-group-account-in-active-directory).

Etterpå oppretter du en tilsvarende sikkerhetsgruppe i [!INCLUDE [prod_short](includes/prod_short.md)] og kobler den til gruppen du opprettet. Hvis du vil finne ut mer, går du til [Legg til en sikkerhetsgruppe i Business Central](#add-a-security-group-in-business-central).

> [!NOTE]
> Hvis du har definert en spesiell type bruker med en Windows-gruppelisenstype i en lokal versjon av [!INCLUDE [prod_short](includes/prod_short.md)] som er eldre enn lanseringsbølge 1 i 2023, konverterer [!INCLUDE [prod_short](includes/prod_short.md)] brukeren til en sikkerhetsgruppe når du oppgraderer. Den nye sikkerhetsgruppen har samme navn som navnet på Windows-gruppen. Sikkerhetsgruppen gir deg bedre oversikt over gruppemedlemmene og de effektive tillatelsene.

## Legg til en sikkerhetsgruppe i Business Central

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg 1.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Sikkerhetsgrupper**, og velg deretter den relaterte koblingen.
1. Velg **Opprett** for å opprette en gruppe.
1. Opprett koblingen til gruppen på følgende måte:

    * For nettversjonen av [!INCLUDE [prod_short](includes/prod_short.md)] velger du gruppen i feltet **Navn på AAD-sikkerhetsgruppe**.
    * For lokal versjon av [!INCLUDE [prod_short](includes/prod_short.md)] velger du gruppen i feltet **Navn på feltet Windows-gruppe**.

> [!NOTE]
> Brukerne vises bare på **Medlemmer**-kortet i faktaboksen eller siden **Sikkerhetsgruppemedlemmer** hvis de er lagt til som brukere i [!INCLUDE [prod_short](includes/prod_short.md)]. Hvis du vil finne ut mer om å legge til brukere, går du til [Slik legger du til brukere eller oppdaterer brukerinformasjon og lisenstildelinger i Business Central](ui-how-users-permissions.md#adduser).  

### Tildel tillatelser til en sikkerhetsgruppe

1. På siden **Sikkerhetsgrupper** velger du gruppen og deretter handlingen **Tillatelser**.
1. Tildel tillatelser på følgende måter:

    * Hvis du vil tildele tillatelsessett enkeltvis, velger du tillatelsene som skal tildeles, i feltet **Tillatelsessett**.
    * Hvis du vil tildele flere tillatelsessett, velger du handlingen **Velg tillatelsessett**, og deretter velger du settene som skal tildeles.

## Gå gjennom tillatelsene i en sikkerhetsgruppe

På siden **Sikkerhetsgrupper** viser faktaboksen **tillatelsessettene** som er tildelt gruppen. Alle brukerne som er oppført på **Medlemmer**-kortet, har disse tillatelsene. Handlingen **Tillatelsessett etter sikkerhetsgruppe** gir en mer detaljert visning. Der kan du også utforske de enkelte tillatelsene i hver sikkerhetsgruppe.

Tillatelser er også tilgjengelige på **Brukere**-siden. Faktaboksen viser kortene **Tillatelsessett fra sikkerhetsgrupper** og **Medlemskap** for den valgte brukeren.

## Sikkerhetsgrupper og brukergrupper

> [!NOTE]
> Brukergrupper vil ikke lenger være tilgjengelige i en fremtidig versjon.

Sikkerhetsgrupper ligner veldig på brukergruppene som for øyeblikket er tilgjengelige. Brukergrupper er imidlertid bare relevante for [!INCLUDE [prod_short](includes/prod_short.md)]. Sikkerhetsgrupper er basert på grupper i Azure Active Directory eller Windows Active Directory, avhengig av om du bruker nettversjonen eller den lokale versjonen av [!INCLUDE [prod_short](includes/prod_short.md)]. Grupper er nyttige for administratorer fordi de kan bruke dem med andre Dynamics 365-apper. Hvis selgere for eksempel bruker [!INCLUDE [prod_short](includes/prod_short.md)]og SharePoint, trenger ikke administratorer å opprette gruppen og medlemmene på nytt.

### Valgfritt: Konverter brukergrupper til tillatelsessett

I lanseringsbølge 1 i 2023 og nyere kan du konvertere brukergrupper til tillatelsessett i leieren. Tillatelsessettene har samme funksjonalitet som brukergrupper. Her er noen eksempler:

* Du kan bruke faktaboksen **Brukere** til å administrere tillatelser for brukere.
* Du kan drille ned på tillatelsessettnavnet for å legge til andre tillatelsessett i settet du arbeider med. Hvis du vil ha mer informasjon, kan du gå til [Slik legger du til andre tillatelsessett](ui-define-granular-permissions.md#to-add-other-permission-sets).

Bruk den assisterte oppsettsveiledningen **Brukergruppeoverføring** til å konvertere gruppene. Når du skal starte veiledningen, finner du **Funksjon: Konverter brukergruppetillatelser** på siden **Funksjonsstyring**, og deretter velger du **Alle brukere** i feltet **Aktivert for**. Veiledningen for assistert oppsett inneholder følgende alternativer for konverteringen.

|Alternativ  |Beskrivelse  |
|---------|---------|
|Tildel til bruker     | Tildel tillatelsene i brukergrupper direkte til brukerne som ble tildelt til gruppen, og fjern brukergruppetildelingene.        |
|Konverter til et tillatelsessett     | Opprett en ny tillatelse for tillatelsene i hver brukergruppe. Det nye tillatelsessettet tildeles alle medlemmene i hver brukergruppe.          |

## Se også

[Opprette brukere i henhold til lisenser](ui-how-users-permissions.md)  
[Konfigurer Business Central-tilgang i Teams med Microsoft 365-lisenser](admin-access-with-m365-license-setup.md)  
[Finn ut mer grupper og tilgangsrettigheter i Azure Active Directory](/azure/active-directory/fundamentals/concept-learn-about-groups)  
[Sikkerhetsgrupper for Active Directory](/windows-server/identity/ad-ds/manage/understand-security-groups)  