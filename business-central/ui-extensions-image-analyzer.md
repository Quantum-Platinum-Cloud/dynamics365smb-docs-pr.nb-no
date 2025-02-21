---
title: Image Analyzer-utvidelsen
description: 'Du kan bruke denne utvidelsen til å analysere bilder av kontaktpersoner og varer for å finne attributter, slik at du kan raskt tilordne dem i Business Central.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'API, extension, Cognitive Services, image, computer vision, attribute, tag, recognition'
ms.search.form: '2026, 2027, 2029,'
ms.date: 05/19/2021
ms.author: bholtorf
---

# <a name="the-image-analyzer-extension" />Image Analyzer-utvidelsen

Image Analyzer-utvidelsen bruker kraftig bildeanalyse fra API-et for visuelt innhold for Azure Cognitive Services til å registrere attributter på bilder du importerer for varer og kontaktpersoner, slik at du enkelt kan gå gjennom og tilordne dem. Når det gjelder varer, kan attributter angi om varen er et bord eller en bil og om den er rød eller blå. Når det gjelder kontaktpersoner, kan attributter være kjønn eller alder.

Image Analyzer foreslår attributter basert på koder som API-et for visuelt innhold finner, og et konfidensnivå. Den foreslår som standard attributter bare hvis det er minst 80 % sannsynlighet for at attributtet er riktig. Du kan om nødvendig angi et annet konfidensnivå. Hvis du vil vite mer om hvordan kodene og konfidensnivået fastsettes, kan du se [API for visuelt innhold](https://go.microsoft.com/fwlink/?linkid=851476).  

Image Analyzer er gratis i [!INCLUDE[prod_short](includes/prod_short.md)], men det er en grense for hvor mange varer du kan analysere i en bestemt tidsperiode. Du kan som standard analysere 100 bilder per måned.

Når du har aktivert utvidelsen, kjører Image Analyzer hver gang du importerer et bilde til en vare eller kontaktperson. Attributter, konfidensnivå og detaljer vises med en gang, og du bestemmer hva du vil gjøre med hvert attributt. Hvis du importerte bilder før du aktiverte Image Analyzer-utvidelsen, må du gå til vare- eller kontaktkortene og velge handlingen **Analyser bilde**.  

## <a name="privacy-notice" />Personvernerklæring

Denne utvidelsen bruker API-en for visuelt innhold fra Azure Cognitive Services, som kan ha andre typer samsvarsforpliktelser enn [!INCLUDE[prod_short](includes/prod_short.md)]. Når du aktiverer Image Analyzer-utvidelsen, sendes kundedata, for eksempel kontaktbilde eller varebilde, til API-en for visuelt innhold. Ved å installere denne utvidelsen godtar du at dette begrensede settet med data sendes til API-en for visuelt innhold. Vær oppmerksom på at du kan deaktivere og avinstallere, Image Analyzer-utvidelsen når som helst for å slutte å bruke denne funksjonen. Hvis du vil ha mer informasjon, kan du se [Microsoft Klareringssenter](https://go.microsoft.com/fwlink/?linkid=851463).

## <a name="requirements" />Krav

Noen få krav er gjeldende for bildene:

* Bildeformater: JPEG, PNG, GIF, BMP  
* Maksimum filstørrelse: mindre enn 4 MB  
* Bildedimensjoner: større enn 50 x 50 piksler  

## <a name="switch-on-the-image-analyzer-extension" />Bryter på Image Analyzer-utvidelsen

Image Analyzer-utvidelsen er bygd inn i [!INCLUDE[prod_short](includes/prod_short.md)]. Du trenger bare å slå den på.

> [!NOTE]  
> Du må være en administrator for å kunne aktivere Image Analyzer-utvidelsen. Kontroller at du er tilordnet brukertillatelsessettet **SUPER**. Hvis du vil ha mer informasjon, kan du se [Tilordne tillatelser til brukere og grupper](ui-define-granular-permissions.md).

Gjør en av følgende handlinger for å aktivere Image Analyzer-utvidelsen:

* Åpne et vare- eller kontaktkort. Velg **Analyser bilde** på varslingslinjen, og følge deretter fremgangsmåten i den assisterte oppsettsveiledningen.  
* Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Servicetilkoblinger**, og deretter velger du **Oppsett for bildeanalyse**. Merk av for **Aktiver Image Analyzer**, og fullfør deretter fremgangsmåten i den assisterte oppsettsveiledningen.  

    > [!TIP]  
    > På siden **Oppsett for bildeanalyse** kan du også endre graden av konfidens for attributtforslag. Hvis du for eksempel vil kreve en større grad av konfidens, kan du angi en høyere prosentsats.

## <a name="analyze-an-item-image" />Analyser et varbilde

Fremgangsmåten nedenfor beskriver hvordan du analyserer et bilde som ble importert før du aktiverte Image Analyzer-utvidelsen.  

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Varer** og velg den relaterte koblingen.  
2. Velg varen, og velg deretter handlingen **Analyser bilde**.  
3. Siden **Image Analyzer-attributter** viser de registrerte attributtene, konfidensnivået og annen informasjon om attributtet. Bruk alternativene **Handling som skal utføres** til å angi hva som skal gjøres med attributtet, eller velg **Legg til i varebeskrivelse** for å legge til navnet på attributtet i varebeskrivelsen. Denne handlingen kan for eksempel være nyttig for å legge til detaljer raskt.

Feltet **Handling som skal utføres** har følgende alternativer:

| Handling | Description |
| ------ | ----------- |
| *Ignorer* | Ingen handlinger utføres. |
| *Bruk som attributt* | Verdien legges til i vareattributtene. Finn ut mer under [Arbeid med vareattributter](inventory-how-work-item-attributes.md). |
| *Bruk som en kategori* | Den valgte verdien legges til som en kategori. Finn ut mer under [Kategoriser varer](inventory-how-categorize-items.md). |
| *Legg til i blokkeringslisten* | Hvis analysen foreslår et attributt du ikke vil se, kan du blokkere attributtet. Du må imidlertid være forsiktig. Blokkerte attributter blir heller ikke foreslått for andre varer. Hvis du angrer at du blokkerte et attributt, kan du velge **Vis blokkerte attributter** og deretter slette attributtet fra oversikten. |

> [!NOTE]  
> Som standard viser **Vareattributter** attributter der **Konfidensresultat** er over **Terskel-% for konfidensresultat** som er definert i **Oppsett for bildeanalyse**. Hvis du vil vise alle registrerte attributter, velger du handlingen **Vis alle attributter**.

## <a name="analyze-a-contact-person-picture" />Analyser et bilde av en kontaktperson

Fremgangsmåten nedenfor beskriver hvordan du analyserer et bilde som ble importert før du aktiverte Image Analyzer-utvidelsen.  

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Kontakter**, og velg deretter den relaterte koblingen.  
2. Velg kontaktpersonen, og velg deretter handlingen **Analyser bilde**.  
3. I hurtigfanen **Profilspørreskjema** går du gjennom forslagene og foretar korrigerer om nødvendig. Finn ut mer under [Bruk profilspørreskjemaer til å klassifisere forretningskontakter](marketing-create-contact-profile-questionnaire.md).  

    > [!NOTE]  
    >
    > API-en for visuelt innhold returnerer følgende attributter:
    >
    > * *alder*
    >
    >     En anslått «visuell alder» i år. Det er hvor gammel en person ser ut til å være sammenlignet med den faktiske biologiske alderen.
    > * *kjønn*
    >
    >    Mann eller kvinne.
    >
    > API-en for visuelt innhold returnerer ikke et konfidensnivå for attributtene alder og kjønn.
  
## <a name="use-your-own-computer-vision-api-account" />Bruk din egen konto for API-et for visuelt innhold

Du kan også bruke din egen konto for API-et for visuelt innhold, for eksempel hvis du vil analysere flere bilder enn standardintegreringen tilbyr.

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Oppsett for bildeanalyse** og velg den relaterte koblingen.
2. Angi **API-URI** og **API-nøkkel** som du har fått for API-et for visuelt innhold.  

    > [!NOTE]  
    > Du må legge til **/analyze** på slutten av API-URI-en, hvis det ikke allerede står der. Eksempel: ```https://cronus.api.cognitive.microsoft.com/vision/v2.0/analyze```.

## <a name="see-how-many-analyses-you-have-left-in-the-current-period" />Se hvor mange analyser har du igjen i den gjeldende perioden

Du kan vise hvor mange analyser du har gjort, og hvor mange du fortsatt kan gjøre, i den gjeldende perioden.  

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Oppsett for bildeanalyse** og velg den relaterte koblingen.
2. Feltene **Grensetype**, **Grenseverdi** og **Utførte analyser** gir bruksinformasjonen.  

## <a name="stop-using-the-image-analyzer-extension" />Slutt å bruke Image Analyzer-utvidelsen

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Servicetilkoblinger**, og deretter velger du **Oppsett for bildeanalyse**.  
2. Fjern feltet **Aktiver Image Analyzer**.  

Du kan eventuelt avinstallere utvidelsen fullstendig. Du kan alltids hente den tilbake fra AppSource. Hvis du vil ha mer informasjon, kan du se [Installere og avinstallere utvidelser i Business Central](ui-extensions-install-uninstall.md#uninstall-an-app).  

## <a name="see-also" />Se også

[Arbeid med vareattributter](inventory-how-work-item-attributes.md)  
[Kategorisere varer](inventory-how-categorize-items.md)  
[Bruk profilspørreskjemaer til å klassifisere forretningskontakter](marketing-create-contact-profile-questionnaire.md)  
[Tilpasse [!INCLUDE[prod_short](includes/prod_short.md)] ved hjelp av utvidelser](ui-extensions.md)  
[Bli klar til å gjøre forretninger](ui-get-ready-business.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
