# From Previous Cohort

***

{% embed url="https://docs.google.com/spreadsheets/d/e/2PACX-1vQ1ISlI_L0znPcmXXn-43w0sk8ABr1M2WVq98D7DUOMFWRIHftsD65fT98OtJJN9kggUMA0b__bmtyM/pubhtml?widget=true&headers=false" %}

***

***

**Questions for the Family Promise Stakeholder**\\

***

**What/Is there a difference between an Employee and a Service Provider (and maybe a User)? Are some of them 3rd party providers? Would all of them get employee ID numbers? Any and all clarifications on the differences between them would be helpful.**\\

***

\*\*General purpose of the service tracker will be to track the services we (Family Promise of Spokane) provide outside of our shelter, so we could say that every employee will be a service provider, but not every service provider will be an employee. A service provider for the sake of our organization could be staff (employees, executive staff, etc), or interns, or volunteers. \*\*\\

***

\*\*It is first and foremost for our staff though, so we could start with MVP of every staff (whether it is employee or intern) being able to log services. \*\*\\

***

\*\*Long story short: we can assume that every 'service provider' will have an email account ending in 'familypromiseofspokane.org' \*\*\\

***

\*\*FOLLOW UP QUESTIONS: \*\*

1.

\*\*RESULTING ACTION: \*\*

1. **Unify all instances/references of “USER”, “PROVIDER”, “SERVICE PROVIDER“, “EMPLOYEE”, “CASE WORKER(?)” to one reference: \_**_**\_**_**\_**_**\_**_**\_\_**
2.

**Can you clearly define (possibly with examples) the difference and relationship between programs, categories, service types and employee/providers? Can we get an example of a service\_type that would be in different and exclusive programs and/or categories?**\\

***

\*\*Programs: \*\*

**1. Serving the currently homeless**

**2. Preventing Homelessness**

**3. Supporting families after becoming renters/homeowners again to prevent ending up homeless again**\\

***

**Categories:**

1. **Shelter support**
2. **Prevention/Diversion**
3. **Aftercare**

\*\*Service Types: really synonymous with the above. \*\*\\

***

\*\*For program/category 1: \*\*

**Food/meals**

**Showers**

**Laundry**

**Case management, etc. (stuff like showers is going to be exclusive to this Program/category, we are only providing showers to the currently homeless)**\\

***

**For program/category 2:**

**Rental assistance**

**Case management (rental assistance being exclusive to this program/category - only providing rental assistance to current tenants (not homeless, not a homeowner)**\\

***

**For program/category 3:**

**Food boxes**

**Case management**

**(food boxes being exclusive to this category, we don't hand out food boxes to currently homeless, nor to homeowners, etc)**\\

***

**Service types generally available to all programs/categories:**\
**Bus pass**

**Gas card**

**Food card (gift card to safeway,etc)**

**Case management**\\

***

\*\*FOLLOW UP QUESTIONS: \*\*

1. **I could use some clarification on “Case Management”: this sounds like it could be the provider/providers associated with service entry, but could be something distinct**
2. \*\*In the examples, programs seem to be the same thing as categories, as if we don’t need this table/insert into the database. But with Service Types, it says that they are synonymous with the “above”. Could use more clarification. \*\*

\*\* Here is one possible interpretation of the information: (even if agreed upon, I’d still need to clarify some things here)\*\*

**Program: Shelter Support**

\*\* Program Description: Serving the currently homeless\*\*

\*\* Program Notes: services like “Showers” are going to be exclusive to this Program, we are only providing showers to the currently homeless\*\*

\*\* Service Types: \*\*

1. **Food/meals**
2. **Showers**
   1. **Exclusive: TRUE (or just list it only to this program, etc)**
3. **Laundry**
4. **Case management**
5. **Etc.**

**Program: Prevention / Diversion**

**Program Description: Preventing Homelessness**

**Program Notes: rental assistance being exclusive to this program/category - only providing rental assistance to current tenants (not homeless, not a homeowner)**

\*\*Service Types: \*\*

1. **Rental assistance**
   1. **Exclusive: TRUE (or just list it only to this program, etc)**
2. **Case management**
3. **etc.**

**Program: Aftercare**

**Program Description: Supporting families after becoming renters/homeowners again to prevent ending up homeless again**

\*\*Program Notes: \*\*

\*\*Service Types: \*\*

1. **Bus pass**
2. **Gas card**
3. **Food card**
   1. **Ex. gift card to Safeway**
4. **Case management**
5. **etc.**

\*\*RESULTING ACTION: \*\*

1. **Delete category table, remove from front end**
2.

\*\*There is currently an option to have multiple providers attributed to a single logged service. Is this the desired state? Are multiple providers often/ever involved with a single logged service entry? \*\*\\

***

**There could be multiple case managers providing support to the same household. For example, two case managers providing a case management meeting (sometimes called triage, so the client gets all the support they need in one meeting that has the people necessary to enact the changes needed)**\\

***

\*\*FOLLOW UP QUESTIONS: \*\*

1. **Would it make sense to have one Provider associated with the logged service entry, and have an associated entry for the case managers?**
   1. **How does this relate to Case Management as a Service Type?**
   2. **Should they be listed only if that Service Type was the service that was provided for this particular logged service entry?**

\*\*RESULTING ACTION: \*\*

1. **Joined table 1-1 as primary provide, and will use the jsonb custom to add additional providers**

**How many recipients should be able to be attributed to a single logged service entry? One or multiple?**\\

***

**How ever many members are in the household**\\

***

\*\*FOLLOW UP QUESTIONS: \*\*

1. **Is there a situation where a single logged service would have more than one recipient, but in different households?**
2. **So, should a “household” be associated with a logged service entry? Just a recipient, then list the members of the household? What about a person who is homeless? Do they get a household associated with them, and what would that look like?**
3. **Would it work to have a mechanism, like a radio button, that asks if this applies to the recipient’s entire household? And if it did, would auto-populate all the occupants as recipients?**

\*\*RESULTING ACTION: \*\*

1. \*\*If FUQ 3, \*\*
   1. **delete joining table**
   2. **Add mech to associate all members of household**
   3. **Have frontend use the mark in the SE to look up the associated household, and display all the related recipients**
   4. \*\*Any DS would account for this mech and count the as recipients \*\*
   5.

**There is currently an option to have multiple phone numbers attributed to a single recipient. Is this the desired state? Or could we reduce and define the number of phone numbers of a single recipient to 1?**\\

***

\*\*Main and backup are good, plus emergency contact. \*\*\\

***

\*\*FOLLOW UP QUESTIONS: \*\*

1. **How to square this with PDL?**
   1. **The thinking for labs 35 for adding multiple phone numbers and emails, was for alternate/emergency contacts. So not just primary and secondary, but you can list their doctor or case worker, loan officer, next door neighbor, whatever it may be.**
   2. **https://lambda-students.slack.com/archives/C02AFKQBD2L/p1629179701339900?thread\_ts=1629157829.338900\&cid=C02AFKQBD2L**

**RESULTING ACTION:**

1. **Kept as is**

**There is currently an option to have multiple email addresses attributed to a single recipient. Is this the desired state? Or could we reduce and define the number of email addresses of a single recipient to 1?**\\

***

**Probably should narrow it down to one email for them.**\\

***

\*\*FOLLOW UP QUESTIONS: \*\*

1. **How to square this with PDL?**
   1. **The thinking for labs 35 for adding multiple phone numbers and emails, was for alternate/emergency contacts. So not just primary and secondary, but you can list their doctor or case worker, loan officer, next door neighbor, whatever it may be.**
   2. **https://lambda-students.slack.com/archives/C02AFKQBD2L/p1629179701339900?thread\_ts=1629157829.338900\&cid=C02AFKQBD2L**

\*\*RESULTING ACTION: \*\*

1. **Kept as is**

**DATABASE DESIGN QUESTIONS (for team):**

1. **Should we WRITE to the logged entry, instead of LINK it, so that deleting related info can’t be Cascaded out? How would that work? What about if you edit, for instance, a recipient’s name?**

**If so, does it make sense to make the whole thing (aside from the id) a jsonb???**
