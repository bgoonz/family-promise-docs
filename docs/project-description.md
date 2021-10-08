# PROJECT DESCRIPTION \(Feature List\)

## Feature List

| Feature Name | Description |
| :--- | :--- |
| [Tablet-First](https://www.notion.so/Tablet-First-3cdda8c13fa14f45887330f84d7b3078) | The application should support tablet-sized screens for data input and general application use. All users should also be able to use the application comfortably on a computer. **Work closely with the Product Manager.** |
| [Metrics](https://www.notion.so/Metrics-31831f815c4c496dbe531243c0379e44) | Pick up the work started by previous teams on **Metrics** that measure data of interest. We're building a "monitoring and evaluation" tool, so **Metrics** will be our users' main window into their data to do this! Default metrics should be automatically generated based on each service added to the platform. Additional metrics can also be added manually—e.g. "composite" metrics, such as: - ratio of money spent / \[set of services\] - density of \[set of services\] / \[given area\] - frequency of \[set of services\] Make metrics as generalized and composable as possible to empower users to build them based on their own use cases. **Work closely with the stakeholder and all the Labs managers.** |
| [Goals](https://www.notion.so/Goals-54b5bceb60344faa99ef45eda48e8f8d) | Let Administrators and Program Managers define **Goals** based on one or more metrics. A goal might be a specific numerical target for a metric, an increase or decrease in a value for a metric, or something else. **Work closely with the stakeholder and the product manager.** |
| [Analytics](https://www.notion.so/Analytics-74a611468b0b499989d87f42456dc707) | All users should have a dashboard view containing data relevant to them along with basic analytics on metrics. **Work closely with your design lead, the Design Manager, and the Product Manager.** |
| [Visualizations](https://www.notion.so/Visualizations-1f8f6e3a033244fab61d47388f131e14) | Create visualizations to summarize relevant data for each user group's dashboard. **Work closely with the stakeholder and the Associate Data Science Lead**. |

### Type

**Web \(Node\) + DS** \(Build-on\)

### Overview

Family Promise helps local communities coordinate their compassion to address the root causes of family homelessness. They tap existing local resources to empower families towards economic stability. Families come to them in crisis; they help them rebuild their lives with new skills and ongoing support. They address the issue holistically, providing prevention services before families reach crisis, shelter and case management when they become homeless, and stabilization programs once they have secured housing to ensure they remain independent.

Family Promise needs a way to **track and visualize the services they provide external to the shelter to gain actionable insights**.

Our goal is to build a _**generalizable**_ **monitoring and evaluation \(M&E\) platform** that meets Family Promise's needs, with an eye toward additional potential use cases that would be useful for many other organizations.

This product will take multiple Labs cohorts to complete.

For the first round, students laid a solid foundation for the application. They built out user roles and profiles, an interface for user management, and a way for users to manage programs in the application.

The next round focused on ensuring individual services can be tracked for recipients at the household and individual level.

This round, we'll pick up the previous team's work building out **metrics** to serve as the main window our users will have into conducting monitoring and evaluation of their programs and services. Then we'll let Administrators and Program Managers define **Goals** based on one or more metrics, and provide **analytics** and **visualizations** to display relevant data for each user type.

### Contacts

**Stakeholder Name:** J Wylie

**Stakeholder Email:** [jwylie@familypromiseofspokane.org](mailto:jwylie@familypromiseofspokane.org)

### Technology Stack

* **BE:** Node
* **FE:** React
* **Auth:** Okta

### User Base

* **Administrators:** Manage all aspects of the application, including:
  * Users
  * Programs
  * Services
* **Program Managers:** Manage one or more programs.
* **Service Providers:** Manage one or more services.

[Feature List](https://www.notion.so/649befae354f455abbd7b642f8f0a120)

### Resources

#### Trello Boards

[**Product Trello Board**](https://trello.com/invite/b/3tDU57dX/c3402ecb4c4a579a18794a51dbd33219/family-promise-service-tracker)

[**Team A Trello Board**](https://trello.com/invite/b/U8UUCBeb/1e2fa0c9b49a4f8b327874bebec596ff/family-promise-a)

#### Stakeholder Resources

**Family Promise Colors:**

* Purple: \#472D5B
* Blue: \#006FBA
* Lilac: \#8D4982
* Yellow: \#FEC357

#### Recordings

📼 [**Labs 33 Playlist**](https://www.youtube.com/playlist?list=PLWX9jswdDQ0WPE7UjrgmGx-nkI8ZuN0lg)

📼 [**Labs 34 Playlist**](https://youtube.com/playlist?list=PLWX9jswdDQ0VP4avK4t33TMpOz_AnBnw7)

📼 [**Labs 35 Playlist**](https://youtube.com/playlist?list=PLWX9jswdDQ0V0521r_6qoVRdkjc4NItEl)

#### Previous Team Pages

[Labs 33: Family Promise: Team A](https://www.notion.so/Labs-33-Family-Promise-Team-A-67cafe38210c4cb5b03ceee65cd72e88)

[Labs 34: Family Promise: Team A](https://www.notion.so/Labs-34-Family-Promise-Team-A-36825ea9492247fd85208f2955f185ac)

[Labs 34: Family Promise: Team B](https://www.notion.so/Labs-34-Family-Promise-Team-B-fadaa6d067a148aa9fd5f09e75244083)

[Labs 35: Family Promise: Team A](https://www.notion.so/Labs-35-Family-Promise-Team-A-66f3cd8444d04302a609d695dba1aa3e)

[Labs 35: Family Promise: Team B](https://www.notion.so/Labs-35-Family-Promise-Team-B-10be7365bdbf479f968b6b28a3b07f4d)

[Family Promise: Team A](https://www.notion.so/Family-Promise-Team-A-765f45407d6640f0853b2ac402acc3a5)

#### Future Brainstorm

* Let Program Managers select an area on a map and name it as a neighborhood/area
  * Let Program Managers add in insider knowledge/community resources per neighborhood/area

