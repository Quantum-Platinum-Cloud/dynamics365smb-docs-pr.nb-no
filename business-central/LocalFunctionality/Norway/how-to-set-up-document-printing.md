---
title: Definere dokumentutskrift
description: 'I Business Central kan du skrive ut salgsrapportene som bruker de nødvendige girospesifikasjonene, ved bruk av forskjellige papirtyper og -skuffer.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.date: 04/01/2021
ms.author: edupont
---
# <a name="set-up-document-printing" />Definere dokumentutskrift
I [!INCLUDE[prod_short](../../includes/prod_short.md)] kan du skrive ut salgsrapportene som bruker de nødvendige girospesifikasjonene, ved bruk av forskjellige papirtyper og -skuffer.  

Du må vurdere hvordan skriveren og skriverdriveren tolker denne informasjonen når du bruker skuffnumre og papirkilder for norske salgsdokumenter. Du må kanskje angi andre skuffnumre for din spesifikke skriver.  

> [!NOTE]  
>  KID-informasjon skrives også ut der giroopplysningene skrives ut.  

Følgende dokumenter krever en utskrevet giro:  

- Fakturaer  
- Kreditnotaer  
- Rentenotaer  
- Purringer  

Den norske versjonen av [!INCLUDE[prod_short](../../includes/prod_short.md)] inneholder følgende sett med salgsdokumenter.  

|**Valg**|Description|  
|-------------|---------------------------------------|  
|1|Standard [!INCLUDE[prod_short](../../includes/prod_short.md)]-dokumenter. Ingen giroinformasjon skrives ut.|  
|2|Giroen skrives ut på hver side. Den siste siden skriver ut girosummen.|  

## <a name="to-set-up-paper-trays" />Slik definerer du papirskuffer:

1.  Velg ikonet ![Lyspære som åpner funksjonen Fortell meg.](../../media/ui-search/search_small.png "Fortell hva du vil gjøre") og skriv inn **Skrivervalg**, og velg deretter den relaterte koblingen.  
2.  Velg rapporten.  
3.  Velg handlingen **Salgsdok.arkskuff - oppsett**.  
4.  Velg en papirkilde i **Første side - papirkilde**-feltet.  
5.  Feltet **Første side - skuffnr.** viser automatisk den valgte papirkilden. Du kan også angi et skuffnummer manuelt.  

    > [!IMPORTANT]  
    >  Ikke alle skrivere har samme papirkildenavn. Du kan angi et nummer i feltet **Skuffnr.**. Nummeret kan tilsvare en papirkilde. Du finner nummeret som en bestemt skriver bruker, i den tekniske dokumentasjonen for skriveren.  

    Feltet **Andre sider** og **Giroside** defineres på samme måte.  

6.  Velg **OK**.  

## <a name="see-also" />Se også
  [Norsk giro og OCR-B-skrift](norwegian-giro-and-ocr-b-font.md)   
 [Opprette KID-numre på salgsdokumenter](how-to-set-up-kid-numbers-on-sales-documents.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
