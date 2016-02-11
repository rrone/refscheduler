1.  Overview
    ========

    1.  The purpose of this specification is to simply discuss the
        functionality users see when they interact with the web
        application called the AYSO Referee Scheduler.

    2.  This specification is not, by any stretch of the
        imagination, complete. All of the wording will need to be
        revised several times before it is finalized. The graphics and
        layout of the screens if included are merely to illustrate the
        underlying functionality. The actual look and feel will be
        developed over time with the input of graphics designers and
        iterative user feedback.

    3.  This specification does not discuss the algorithms used, which
        will be developed in a technical specification.

    4.  The Referee Scheduler is functionality available to all
        registered AYSO volunteers certified as Referees or acting as
        Referee Administrators or their designees.

2.  Technology
    ==========

    1.  Platforms

        1.  System will be compatible with desktops, laptops, tablets,
            mobile devices

    2.  Compatibility

        1.  System will operate on:

            1.  iOS version 7 and higher
            2.  Mac OS version 10 and higher
            3.  Windows 7 and higher
            4.  Android version 4 and higher

        3.  Compatible Browsers:
    
            1.  Chrome version 43 and higher
            2.  IE version 9 and higher
            3.  Firefox version 38 and higher
            4.  Safari version 7 and higher

1.  Security Model
    ==============

    1.  The system provides multi-level access controls for the
        following roles: SuperAdmin, Admin, Scheduler, Scorer, Assignor,
        Referee

  | Functions                  | SuperAdmin  | Admin  | Scheduler  | Assignor  | Scorer  | Referee   |
  | -------------------------- | ----------- | ------ | ---------- | --------- | ------- | --------- |
  | Database Admin             | X           |        |            |           |         |           |
  | Profile Data Entry         | X           | X      |            |           |         |           |
  | Schedule Data Entry        | X           | X      | X          |           |         |           |
  | Assignments                | X           |        |            | X         |         |           |
  | Views (depending on Role)  | X           | X      | X          | X         | X       | X         |
  | User Profile Mgmt          | X           | X      |            |           |         | X         |
  | Match Reporting            | X           | X      |            |           | X       | X         |

1.  Navigation ([samples](https://github.com/rrone/refscheduler/blob/master/screensnaps/menu.myaccount.png))
    ==========
    1. The application will have simple menus to navigate to the views.  The menus are dynamic depending on the role of the user.  

3.  System Functions
    ================

    1.  The system will verify and enforce eligibility by current Safe
        Haven, CDC, MY for all Referee accounts. Accounts will be given
        30 day notice of expiring qualifications by email. Accounts
        failing eligibility will be flagged as ineligible and will not
        be available for assignments.

    2.  The system will provide referees with email or text
        notifications of upcoming assignments 48 hours in advance.

    3.  The system will send all Admins notification of unaccepted
        assignments 96 hours in advance of the match.

    4.  The system will send all Admins notification of declined
        assignments immediately.

    5.  Based on User provided AYSO Volunteer ID (8-digits), the system
        will add to the user profile view:

        1.  AYSO Section-Area-Region

        2.  Referee Badge Level (None, U-8, Basic Referee, Intermediate
            Referee, Advanced Referee, National Referee)

2.  Admin Functions
    ===============

    1.  The Admin role will be able to send broadcast email to all
        referees by competition, all accounts showing availability, all
        accounts

    2.  Print account roster with contact info by competition 

    3.  Export schedule template for import

    4.  Import and maintain fields by site and sub-site

    5.  Import & maintain match schedules from Excel or comma-separated
        variables (CSV): Date, time, competition, site, field, division,
        home team, home coach, away team, away coach

3.  User Functions
    ==============

    1.  Each user is able to maintain profile data including:

        *  Full Name

        *  First Name

        *  Last Name

        *  Nick Name

        *  Email address

        *  Best phone number

        *  AYSO Volunteer ID (8-digits)

    2.  Each user will be available to provide availability
        for assignments. This will be done by blocking dates,
        partial-blocking parts of dates, clear by date or date range,
        time range, and providing maximum travel distance (in miles)

    3.  User will be able to block assignments (i.e., won’t
        take assignments) by site or other referees

    4.  Print Referee schedule by account, date, field, team to PDF or
        Excel (selectable)

    5.  Match assignments: assignment, accept, decline, notifications

    6.  Match results reporting: score, misconduct, incidents

    7.  Match misconduct reporting using standard form

    8.  Match incident reporting using standard form

    9.  Referee team views: upcoming teammates with contact info

    10. Historical search by account, date: export to Excel

    11. Schedule views:

        1.  By accepted

        2.  By declined

        3.  By assigned

        4.  By unassigned

        5.  Assignments by name, grade, mobile number

        6.  Sortable by date & time, site, field, division, referee last
            name, AR1 last name, AR2 last name

4.  Use Cases
    =========

    1.  UC 1: Account creation, pw reminders: new and returning users

        1.  The home page presents two options:

            1.  A login with username and password for returning users.
                There is a link to retrieve a lost or
                forgotten password.

            2.  A prompt to create a new account for new users.

    2.  UC 2: Match import and update
