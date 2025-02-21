---
title: Angi datoer og klokkeslett i Business Central
description: 'Finn ut hvordan du angir datoer og klokkeslett, inkludert ulike produktivitetstips som snarveier, uttrykk og områder.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'dates, reporting, filter, calendar, shorthand, range'
ms.search.form: '9020, 9022, 9026, 9027, 9030, 9000, 9009, 9004, 9005, 9024, 9006, 9007, 9010, 9016, 9017'
ms.date: 06/23/2021
ms.author: edupont
---

# <a name="work-with-calendar-dates-and-times" />Arbeid med datoer og klokkeslett i kalenderen

Du kan angi datoer og klokkeslett på flere måter. [!INCLUDE[prod_short](includes/prod_long.md)] omfatter avanserte funksjoner som fremskynder dataregistrering eller hjelper deg med å skrive sammensatte kalenderuttrykk. Det finnes ulike steder i programmet der du kan angi dato og klokkeslett i feltene. Du kan for eksempel angi leveringsdatoen på en ordre. Når du filtrerer lister eller rapportdata, kan du angi datoer og klokkeslett for å finne dataene du er interessert i.

[!INCLUDE [about-ui-learn](includes/about-ui-learn.md)]

## <a name="check-your-region-and-language-settings" />Kontrollere innstillinger for region og språk

Siden **Mine innstillinger** angir **Område** og **Språk** du bruker i programmet. Disse innstillingene påvirker hvordan du angir dato og klokkeslett.

- **Område**-innstillingen bestemmer hvordan datoer, klokkeslett, numre og valutaer vises eller formateres.

- For datomønstre som involverer ord, må ordene du bruker, samsvare med **Språk**-innstillingen.

> [!NOTE]
> [!INCLUDE[prod_short](includes/prod_long.md)] bruker det gregorianske kalendersystemet.

<!--
The following sections describe how you can enter dates, times, datetimes, durations, date ranges, and how you use date formulas.
-->

## <a name="entering-dates" />Sette inn datoer

I et datofelt kan du angi en dato med standardformatet for regionsinnstillingen. Ulike regioner kan bruke ulike skilletegn mellom dager, måneder og år. Enkelte regioner bruker for eksempel streker (mm-dd-åååå) og andre bruker skråstreker (mm/dd/åååå).  

> [!TIP]
> Du kan bruke alle skilletegn, også mellomrom, og datoen endres automatisk til skilletegnene som samsvarer med din region.

> [!NOTE]
> Formatet for å vise datoer i trykte rapporter eller dokumenter sendt via e-post, påvirkes ikke av ditt personlige valg av regioninnstilling.

Hvis du vil arbeide mer effektivt med datoer og klokkeslett, kan du bruke metodene eller formatene som er beskrevet nedenfor.

### <a name="picking-dates-from-the-calendar" />Plukke datoer fra kalenderen

Alle felt som viser et kalenderikonet, kan angis ved hjelp kalenderdatovelgeren. Aktiver kalenderikonet for å vise kalenderdatovelgeren, eller velg <kbd>Ctrl</kbd>+<kbd>Hjem</kbd> i feltet.

![Datofelter.](media/ui-date-field.png "Eksempel på et datofelt")

Se også [Hurtigtaster i kalenderdatovelgeren](keyboard-shortcuts.md#calendarshortcuts)

### <a name="day-week-year-pattern" />Mønsteret dag\-uke\-årn

Du kan angi en dato som en ukedag etterfulgt av et ukenummer og eventyelt et år. For eksempel Man25 eller man25 betyr mandag i uke 25. Hvis du ikke angir et år, brukes året i arbeidsdatoen.

I stedet for å angi hele ordet for ukedagen, kan du angi en del av ord fra begynnelsen. Hvis det oppstod konflikter (som med t som kan være tirsdag eller torsdag), evalueres dagene i henhold til regioninnstillingen. Inndataene vurderes først mot arbeidsdato samt i dag, som du må huske dette når du forkorter. For eksempel _t_ betyr allerede dagens, og kan dermed ikke bety tirsdag eller torsdag.

Ukenummererplanen er alltid ISO 8601, der uke 1 er uken med 4 januar i seg, eller uken med den første torsdagen i året.

### <a name="digit-patterns" />Tallmønstre

I et datofelt kan du angi to, fire, seks eller åtte tall:

- Hvis du bare skriver inn to tall, tolkes disse som dagen, og måneden og året for arbeidsdatoen legges til.

- Hvis du skriver inn fire tall, tolkes disse som dagen og måneden, og året for arbeidsdatoen legges til. Rekkefølgen på dag og måned avhenger av regioninnstillingene. Selv om dine regioninnstillingene dine har året før dag og måned, tolkes fire sifre som dagen og måneden.

- Hvis datoen du vil angi ligger i intervallet 01.01.1950 til og med 31.12.2049, kan du angi året med to eller fire sifre.

  > [!NOTE]
  > Hvis du bruker [!INCLUDE[prod_short](includes/prod_short.md)] lokalt, kan årstallsområdet med to sifre være forskjellige. Administratorer kan endre området ved å endre innstillingen **CalendarTwoDigitYearMax** på [!INCLUDE[prod_short](includes/prod_short.md)]-serveren. Hvis du vil ha mer informasjon, kan du se [Konfigurere Business Central Server](/dynamics365/business-central/dev-itpro/administration/configure-server-instance#General).
 
### <a name="today" />I dag

Skriv inn ordet for _i dag_, på språket som er angitt på **Mine innstillinger**-siden, for å angi datoen for en post til dagens dato. I stedet for å angi hele ordet, kan du angi en del av ord fra begynnelsen. På engelsk kan du for eksempel skrive inn _t_ eller _tod_, så lenge det ikke også er starten på et annet ord.

### <a name="period" />Periode

For å filtrere på en bestemt regnskapsperiode, angi bokstaven p eller ordet periode i datofeltet, etterfulgt av et nummer som identifiserer regnskapsperioden, som p2 eller periode4. Regnskapsperioden er relativ til regnskapsåret for gjeldende arbeidsdato som er angitt i ditt rollesenter. Hvis arbeidsdatoen for eksempel er **21.03.22**, filtreres _p1_ eller bare _p_ på den første regnskapsperioden i regnskapsåret 2022 (for eksempel 01.01.22–31.01/22). _p15_ filtrerer på den 15. regnskapsperioden fra starten av regnskapsåret 2022 (for eksempel 01.03.23–31.03.23).

Regnskapsperioden er definert på **Regnskapsperioder**-siden. Hvis du vil vise eller endre regnskapsperiodene, åpner du siden [her](https://businesscentral.dynamics.com/?page=100).

### <a name="work-date" />Arbeidsdato

Bruk en arbeidsdato til å angi en dato som ikke er dagens dato for poster. En arbeidsdato er for eksempel nyttig når du må angi en bestemt dato for flere poster. Du angir arbeidsdatoen på **Mine innstillinger**-siden. 

En rask måte å skrive inn arbeidsdatoen på poster på, er å skrive inn noe av eller hele ordet _arbeid_, fra begynnelsen av ordet, på språket du bruker [!INCLUDE[prod_short](includes/prod_long.md)]. På engelsk kan du for eksempel skrive inn _w_ eller _work_. Språket er også angitt på **Mine innstillinger**-siden.

Hvis du ikke har angitt en arbeidsdato, brukes dagens dato. Se også [Endre grunnleggende innstillinger, for eksempel arbeidsdatoen](ui-change-basic-settings.md#work-date) for mer informasjon.

### <a name="closing-date" />Avslutningsdato

Når du avslutter et regnskapsår, kan du bruke avslutningsdatoer til å indikere at en post er en avslutningspost. En avslutningsdato ligger teknisk sett mellom to datoer, for eksempel mellom 31. desember og 1. januar.

Hvis en dato skal være en avslutningsdato, setter du U rett foran datoen, for eksempel U123101. Bruk dette formatet sammen med alle datomønstre.

### <a name="examples" />Eksempler

Tabellen nedenfor inneholder eksempler på datoer som bruker alle formater. Det antar regioninnstillinger som formaterer datoer i henhold til: **år.måned.dag.**, en uke som starter på mandag, og engelsk språk.

|**Angivelse**      |**Tolkning**      |
|---------------|------------------------|
|2022.12.31.|2022.12.31.|
|221231|2022.12.31.|
|22.12.31.|2022.12.31.|
|22.12.31.|2022.12.31.|
|20221231|2022.12.31.|
|22/12,31|2022.12.31.|
|11|11.arbeidsdato måned.arbeidsdato år.|
|1112|12.11.arbeidsdato år.|
|d eller i dag|dagens dato|
|p4|datointervall som inneholder den fjerde regnskapsperioden, for eksempel 01.04.20–30.04.20|
|a eller arbeidsdag|arbeidsdatoen|
|m eller mandag|Mandag i arbeidsdatouken|
|ti eller tirsdag|Tirsdag i arbeidsdatouken|
|l eller lørdag|Lørdag i arbeidsdatouken|
|s eller søndag|Søndag i arbeidsdatouken|
|t23|Tirsdag i uke 23 i arbeidsdatoåret|
|t 23|Tirsdag i uke 23 i arbeidsdatoåret|
|t-1|Tirsdag i uke 1 i arbeidsdatoåret|

## <a name="a-namebkmksettingdaterangesa-setting-ranges" /><a name="BKMK_SettingDateRanges"></a> Angi intervaller

I lister, totaler eller rapporter kan du definere filtre på datoer, klokkeslett og datoer og klokkeslett som inneholder en startverdi og eventuelt en sluttverdi, for å vise bare dataene i dette intervallet. Standardreglene gjelder for angivelse av datointervaller.

|**Betyr**|**Eksempeluttrykk (dato)**|**Data som er inkludert i filteret**|
|-----------|---------------------|--------------------|
|Intervall|15.12.00..15.01.01<br /><br />..15.12.00<br /><br />p1..p4|Poster med dato fra og med 15.12.00 til og med 15.01.01.<br /><br />Poster med datoer 15.12.00 eller tidligere.<br /><br />Datointervall som inneholder den andre, tredje eller fjerde regnskapsperioden, for eksempel 01.01.20–30.04.20.|
|Enten/eller|12 15 00\|12 16 00|Poster med datoer enten 15.12.00 eller 16.12.00. Hvis det er poster med begge datoer på begge dager, blir alle vist.|
|Kombinasjon|12 15 00\|12 01 00..12 10 00  <br /><br />..12 14 00\|12 30 00..|Poster med datoer 15.12.00 eller fra og med 01.12.00 til og med 10.12.00.  <br /><br />Poster med datoer 14.12.00 eller tidligere, eller datoer 30.12.00 eller senere, det vil si alle poster unntatt poster med datoer mellom og 15.12.00 og 29.12.00.|

Du kan bruke ethvert gyldig format i datointervallfiltre. For eksempel man14 3..t 4p brukt på en dato- og klokkeslettfelt resulterer i et filter fra 03:00 mandag i uke 14 i det gjeldende arbeidsdatoåret, inkludert til dagens dato klokken 16:00.

## <a name="use-date-formulas" />Bruk datoformler

En datoformel er en kort, forkortet kombinasjon av bokstaver og tall som angir hvordan det skal beregne datoer. Du kan angi datoformler i forskjellige datoberegningsfelt eller filtre.

> [!NOTE]
> Én dag tas med automatisk i alle datoformelfelt for å angi at perioden starter i dag. Hvis du for eksempel angir 1U, blir perioden på samme måte faktisk åtte dager fordi dagens dato er inkludert. Hvis du vil angi en periode på sju dager \(én sann uke\), inkludert periodens startdato, må du angi 6D eller 1U-1D.

Her kommer det noen eksempler på hvordan datoformler kan brukes:

- Datoformelen i det gjentakende intervallfeltet i gjentakende kladder bestemmer hvor ofte posten på kladdelinjen skal bokføres.

- Datoformelen i feltet **Respittid** for en bestemt purringsgrad angir hvor lang tid som må gå fra forfallsdatoen \(eller fra forrige purringsdato\) før det kan opprettes en purring.

- Datoformelen i feltet **Beregning av forfallsdato** angir hvordan forfallsdatoen i purringen beregnes.

Datoformelen kan inneholde opptil 20 tegn, både tall og bokstaver. Du kan bruke følgende bokstaver, som er forkortelser for kalenderenheter:

|  Bokstav  |  Betyr  |
|----------|----------------------|
|L|Løpende|
|D|Dag\(er\)|
|U|Uke\(r\)|
|M|Måned\(er\)|
|K|Kvartal\(er\)|
|Å|År\(\)|

Du kan opprette datoformler på tre måter.

Eksempelet nedenfor viser hvordan L brukes, for løpende, og en tidsangivelse.

|  Uttrykk  |  Betyr  |
|--------------|-----------|
|LU|Løpende uke|
|LM|Løpende måned|

Eksempelet nedenfor viser hvordan et tall og en tidsangivelse brukes. Et tall kan ikke være større enn 9999.

|  Uttrykk  |  Betyr  |
|--------------|-----------|
|10D|10 dager fra i dag|
|2U|2 uker fra i dag|

Eksempelet nedenfor viser hvordan et en tidsangivelse og et tall brukes.

|  Uttrykk  |  Betyr  |
|--------------|-----------|
|D10|Den neste 10. dag av en måned|
|UD4|Neste 4. dag av en uke \(torsdag\)|

Eksempelet nedenfor viser hvordan du kan kombinere disse tre formlene hvis du trenger det.

|  Uttrykk  |  Betyr  |
|--------------|-----------|
|LM+10D|Løpende måned \+10 dager|

Følgende eksempel viser hvordan du kan bruke minus-tegn til å indikere en dato i fortiden.

|  Uttrykk  |  Betyr  |
|--------------|-----------|
|-1Å|1 år siden fra i dag|

> [!IMPORTANT]
> Hvis plasseringen bruker en hovedkalender, tolkes datoformelen du angir, for eksempel i feltet **Leveringstid**, i henhold til arbeidsdager fra kalenderen. For eksempel betyr 1U sju virkedager.
<!--
# <a name="entering-date-ranges" />Entering Date Ranges
You can set filters containing a start date and an end date to display only the data contained in that date range or time interval. Special rules apply to the way you set date ranges. Let's take the **Customer Top 10** as an example:

![Setting a date range in the request page for the Customer Top 10 list.](./media/ui-enter-date-ranges/customer-top10-list.png)

Here you can limit the report to a date range such as the past 2 weeks, or a total of 6 weeks, or whatever range you want. To set date ranges, you enter dates and then use either **..** or **|** to set the range. In our example, to show the top 10 customers for the first two weeks of May, you would set the date filter to *05 01 17..05 14 17*.
Here are a couple of other examples:

| Meaning | Example | Entries included |
|---|---|---|
|Equal to| 12 15 16 |Only those posted on December 15 2016.|
|Interval| 12 15 16..01 15 17<br /><br />..12 15 16|Those posted on dates between and including December 15 2016 and January 15 2017.<br /><br />Those posted on December 15 2016 or earlier.|
|Either/or|12 15 16&#124;12 16 16|Those posted on either December 15 or December 16 2016. If there are entries posted on both days, they will all be displayed.|

You can also combine the various format types.

| Example | Entries included |
|---|---|
|12 15 16&#124;12 01 16..05 31 17 | Entries posted either on December 15 2016 or on dates between and including December 01 2016 and May 31 2017. |
|..12 14 16&#124;12 30 16.. | Entries posted on December 14 or earlier, or entries posted on December 30 or later - that is, all entries except those posted on dates between and including December 15 and 29. |

Note that we have used the US date format MMDDYY here. As [!INCLUDE[prod_short](includes/prod_short.md)] becomes available in other markets, you'll be able to use the formats that you are used to.

## <a name="use-date-formulas" />Use Date Formulas
A date formula is a short, abbreviated combination of letters and numbers that specifies how to calculate dates. You can enter date formulas in various date calculation fields and in recurring frequency fields in recurring journals.

> [!NOTE]
> In all data formula fields, one day is automatically included to cover today as the day when the period starts. Accordingly, for example, if you enter **1W**, then the period is actually eight days because today is included. To specify a period of seven days (one true week) including the period starting date, then you must enter **6D** or **1W\-1D**.

Here are some examples of how date formulas can be used:

- The date formula in the recurring frequency field in recurring journals determines how often the entry on the journal line will be posted.

- The date formula in the **Grace Period** field for a specified reminder level determines the period of time that must pass from the due date (or from the due date of the previous reminder) before a reminder will be created.

- The date formula in the **Due Date Calculation** field determines how to calculate the due date on the reminder.

The date calculation formula can contain a maximum of 20 characters, both numbers and letters. You can use the following letters, which are abbreviations for time specifications.

|  Letter  |  Time specification  |
|----------|----------------------|
|C|Current|
|D|Day\(s\)|
|W|Week\(s\)|
|M|Month\(s\)|
|Q|Quarter\(s\)|
|Y|Year\(s\)|

You can construct a date formula in three ways.

The following example shows how to use **C**, for current, and a time unit.

|  Expression  |  Meaning  |
|--------------|-----------|
|CW|Current week|
|CM|Current month|

The following example shows how to use a number and a time unit. A number cannot be larger than 9999.

|  Expression  |  Meaning  |
|--------------|-----------|
|10D|10 days from today|
|2W|2 weeks from today|

The following example shows how to use a time unit and a number.

|  Expression  |  Meaning  |
|--------------|-----------|
|D10|The next 10th day of a month|
|WD4|The next 4th day of a week \(Thursday\)|

The following example shows how you can combine these three forms as needed.

|  Expression  |  Meaning  |
|--------------|-----------|
|CM\+10D|Current month \+ 10 days|

The following example shows how you can use a minus sign to indicate a date in the past.

|  Expression  |  Meaning  |
|--------------|-----------|
|-1Y|1 year ago from today|

> [!IMPORTANT]
> If the location uses a base calendar, then the date formula that you enter in, for example, the **Shipping Time** field is interpreted according to the calendar working days. For example, **1W**  means seven working days.

-->

## <a name="entering-times" />Angi klokkeslett

Når du angir klokkeslett, kan du sette i et skilletegn som ikke er mellomrom, som du ønsker mellom enhetene. Hvis du bruker doble sifre for hver enhet opptil millisekunder, er det ikke nødvendig.

Du trenger bare skrive de største enheter som du vil ha; resten settes til null. Du kan eventuelt utelate AM-PM-indikatoren.

Tabellen nedenfor viser forskjellige måter som klokkeslett kan angis på, og hvordan de tolkes. Det antar regioninnstillinger som formaterer tidspunkt i henhold til: **Timer:Minutter:Sekunder.Millisekunder.** og bruker AM- og PM-indikatorer for henholdsvis "AM" og "PM".

|**Angivelse**      |**Tolkning**      |
|---------------|------------------------|
|05:23:17|05:23:17|
|5|05:00:00|
|5AM|05:00:00|
|5P|17:00:00|
|12|12:00:00|
|12A|00:00:00|
|12P|12:00:00|
|17|17:00:00|
|5:30|05:30:00|
|0530|05:30:00|
|5:30:5|05:30:05|
|053005|05:30:05|
|5:30:5,50|05:30:05.5|
|053005050|05:30:05.05|

> [!NOTE]
> Millisekunder tolkes som desimalformat. Derfor betyr både 3, 30 og 300 altså 300 millisekunder, mens 03 betyr 30 og 003 betyr 3 millisekunder.

> [!IMPORTANT]
> Du kan ikke bruke 24:00 til å angi midnatt eller bruke en verdi som er større enn 24:00.

Ordet for tidspunkt på språket som brukes av [!INCLUDE[prod_short](includes/prod_long.md)], evalueres etter gjeldende dato og klokkeslett på datamaskinen eller mobilenheten. Du kan angi en del av ordet, fra begynnelsen, som for eksempel t eller TIM.

## <a name="entering-combined-dates-and-times" />Angi kombinerte datoer og klokkeslett

[!INCLUDE [datetimes](includes/datetimes.md)]

## <a name="entering-duration" />Angi varighet

Noen av feltene i programmet representerer en varighet eller mengden som er gått, i stedet for en bestemt dato eller klokkeslett. Du angir en varighet som et tall etterfulgt av enheten.

Her er noen eksempler.

|**Varighet**|**Enhet**|
|------------|-------------------|
|2t|2 timer|
|6t 30 m|6 timer 30 min|
|6,5t|6 timer 30 min|
|90m|1 t 30 min|
|2d 6t 30m|2 dager 6 timer 30 min|
|2d 6t 30m 56s 600ms|2 dager 6 timer 30 min 56 sek 600 msek|

Du kan også angi et tall, som blir automatisk konvertert til et tidsintervall. Tallet du angir, konverteres i henhold til standardenheten som er angitt for feltet Varighet.

Hvis du vil se hvilken enhet som brukes i et varighetsfelt, skriver du inn et tall. Deretter kan du se hvilken enhet det konverteres til.

Tallet 5 konverteres for eksempel til 5 timer hvis enheten er timer.

## <a name="see-related-microsoft-trainingtrainingmodulesexplore-modify-info-dynamics-365-business-central" />Se relatert [Microsoft-opplæring](/training/modules/explore-modify-info-dynamics-365-business-central/)

## <a name="see-also" />Se også

[Arbeid med [!INCLUDE[prod_short](includes/prod_long.md)]](ui-work-product.md)  
[Beregne dato for kjøp](purchasing-date-calculation-for-purchases.md)  
[Angi vilkår i filtre](ui-enter-criteria-filters.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
