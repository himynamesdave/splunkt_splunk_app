# Splunkt App for Splunk
## A Splunk App to manage data for Splunkt iOS app

Currently in beta.

### Functionality

* data visualisation layer to track event metrics (i.e tshirts sizes / slogans given away, use-cases discussed, competition, and more...)
* admin control panel allowing users to add or amend the variables that populate the app (events, tshirt slogans, tshirt sizes, use cases, competition, & roducts)

### Architecture

![Splunkt App for Splunk Architecture](https://raw.githubusercontent.com/himynamesdave/splunkt_splunk_app/master/static/archdiagram.png)

*Note, SFDC integration is not currently configured.*

### Splunk components

#### Indexes

This app contains one index. Data arrives in index as a JSON document on port 8089.

1. **[splunkevents]** - This stores lead data collected from mobile app data by Splunk event staff. 

#### KV Collections

This app contains five KV Collections all used to set variables for Splunkt iOS app.

Data entered into KV Collections on "Admin Control Panel" in GUI by Splunk marketing staff.

Data queried by Splunkt iOS app on port 8191.

1. **[eventcollection]** - stores event data: _key, addEventName, addEventId, addEventCity, addEventCountry, addEventClass, addEventOrganiserEmail, addEventStartDay, addEventStartMonth, addEventStartYear, addEventEndDay, addEventEndMonth, addEventEndYear
2. **[shirtslogancollection]** - stores shirt slogan data: _key, addShirtSlogan
3. **[shirtsizecollection]** - stores shirt size data: _key, addShirtSize
4. **[usecasecollection]** - stores use case data: _key, addUseCase
5. **[competitioncollection]** - stores competition data: _key, addCompetition

#### Users

There are who types of Splunk users set in app:

1. **marketingteam** - should be granter "admin" permissions. Able to add / delete from KV store and run all searches.
2. **api** - should be granted "admin" permissions. Used only for mobile app authentication. Able to read and write index or KV Collections.
3. **staffteam** - should be granted "user" persmission. Able to view searches.

#### Views

**Admin control panel**

Accessed by "marketingteam" users. The admin control panel gives the ability for user to add or delete:

1. Events
2. Shirt Slogans
3. Shirt Sizes
4. Use Cases
5. Competitors

*Data visualisation*

Accessed by "staffteam" users.

TODO