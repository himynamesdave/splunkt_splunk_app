# Splunkt App for Splunk
## A Splunk App to manage data for Splunkt iOS app

Currently in beta.

### Functionality

-data visualisation layer to track event metrics (i.e tshirts sizes / slogans given away, use-cases discussed, competition, and more...)
-admin control panel allowing users to add or amend the variables that populate the app (events, tshirt slogans, tshirt sizes, use cases, competition, & roducts)

### Architecture

![Splunkt App for Splunk Architecture](https://raw.githubusercontent.com/himynamesdave/splunkt_splunk_app/master/static/archdiagram.png)

*Note, SFDC integration is not currently configured.*


Indexes
*[splunkevents] - This stores lead data collected from mobile app data entry. Data entered in app by Splunk staff at events and sent via port 8089 in JSON document.

KV Collections (all collection data entered in Splunk App for Splunkt by marketing staff. Queried on port 8191.)
*[eventcollection] - This collection stores event data (_key, addEventName, addEventId, addEventCity, addEventCountry, addEventClass, addEventOrganiserEmail, addEventStartDay, addEventStartMonth, addEventStartYear, addEventEndDay, addEventEndMonth, addEventEndYear).
*[shirtslogancollection] - This collection stores shirt slogan data (_key, addShirtSlogan).
*shirtsizecollection - This collection stores shirt size data (_key, addShirtSize).
*usecasecollection - This collection stores use case data (_key, addUseCase).
*competitioncollection - This collection stores competition data (_key, addCompetition).

### Data viz

TODO

### Admin control panel

TODO
