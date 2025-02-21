---
title: Definer flere rentesatser for forsinket betaling
description: Dette emnet forklarer hvordan du kan beregne rentebelastning med flere rentesatser for en bestemt periode.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: '6, 431, 432, 572'
ms.date: 06/16/2021
ms.author: edupont
---
# <a name="set-up-multiple-interest-rates-for-delayed-payment" />Definer flere rentesatser for forsinket betaling

Du kan bruke ulike rentesatser for forskjellige perioder for forsinkede betalinger handelstransaksjoner. [!INCLUDE [multiple-interest-rates-def](includes/multiple-interest-rates-def.md)]

For eksempel angir en offentlig myndighet maksimal rente som kan pålegges for en kunde. Denne rentesatsen kan endres to ganger i året, 1. januar og 1. juli. Rentesatsen mellom bedrifter (B2B) avtales av partene, og det er ingen begrensning for denne kundegruppen. Annonsert sats er vanligvis 4 % mer enn vanlig bankrente.

Når du oppretter rentenotabetingelser og purrebetingelser for straff for forsinket betaling, kan du angi flere rentesatser slik at straffegebyret beregnes fra forskjellige renter i forskjellige perioder.  

## <a name="to-set-up-multiple-interest-rates" />Angi flere rentesatser

1. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Rentenotabetingelser**, og velg deretter den relaterte koblingen.  
2. På siden **Rentenotabetingelser** velger du den nødvendige rentebetingelsen, og deretter handlingen **Rentesatser**.  
3. Fyll ut feltene etter behov. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Velg **OK**-knappen.  
5. Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](media/ui-search/search_small.png "Fortell hva du vil gjøre") og angi **Purrebetingelser**, og velg deretter den relaterte koblingen.  
6. På siden **Purrebetingelser** velger du den nødvendige purrebetingelsen, og deretter handlingen **Nivåer**.  
7. På siden **Purregrader** velger du **Beregn renter**-feltet for de aktuelle purregradene.  

Når du utsteder en rentenota, viser den rentebelastningene med flere rentesatser for en bestemt tidsperiode. Notaen inneholder også kontaktdetaljer for kunden, selskapet som utsteder notaen, tilleggsbeløpet og det totale beløpet. Åpningsposten på rentenotaen vises med fet skrift. Rentebelastningen beregnes med flere rentesatser for en bestemt tidsperiode, og skrives ut etter åpningsposten for rentenotaen.  

## <a name="see-also" />Se også

[Innkreve utestående saldi](receivables-collect-outstanding-balances.md)  
[Konfigurere finans](finance-setup-finance.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
