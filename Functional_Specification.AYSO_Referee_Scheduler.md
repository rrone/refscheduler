1.  Overview
    ========
    1.  The Referee Scheduler is a web application that supports Volunteer Registration, Schedule Management, Referee Assignments, Match Reporting and Team Management for soccer competitions, i.e. a typical season, tournaments or other such events.
    
    2.  The purpose of this specification is to simply discuss the functionality users see when they interact with the web application called the AYSO Referee Scheduler.

    3.  This specification is not, by any stretch of the imagination, complete. All of the wording will need to be         revised several times before it is finalized. The graphics and layout of the screens if included are merely to illustrate the underlying functionality. The actual look and feel will be developed over time with the input of graphics designers and iterative user feedback.

    4.  This specification does not discuss the algorithms used, which will be developed in a technical specification.

    5.  The Referee Scheduler is functionality available to all registered AYSO volunteers certified as Referees or acting as Referee Administrators or their designees.
    
    6.  The workflow of assigning matches is as follows:
        1.  Competition schedule is loaded into the application
        2.  Sites and fields are loaded into the application
        3.  Referees provide and maintain availability for the duration of the competition
        4.  The Assignor publishes assignments for scheduled matches
        5.  Referees receive notification of pending assignments and accept or decline the assignments.  NOTE: Once accepted, the Referee is obligated to keep the assignment until released by the Assignor.
        6.  The Assignor is notified of declined assignments for reassigning
        7.  Referees may request particular assignments.  The Assignor must approve such requests and publish the assignment for the Referee to accept.  NOTE: the Referee may, before the assignor approves the request, rescind the request by returning to the game and selecting "Remove Me From Assignment"
        8.  Referees may request to turnback assignments for reassignment.  NOTE: the Referee is obligated to keep the assignment until the Assignor reassigns the match.
        9.  On completion of the match, the match results are recorded by the Referee or a designated Scorer.
        10. The application incorporates the match results and published updated results

2.  Technology
    ==========
    1.  The application will be compatible with desktops, laptops, tablets, and mobile devices.

    2.  Compatibile operating systems
        1.  System will operate on:
            1.  iOS version 7 and higher
            2.  Mac OS version 10 and higher
            3.  Windows 7 and higher
            4.  Android version 4 and higher

        3.  Compatible Browsers:
            1.  Chrome version 43 and higher
            2.  Internet Explorer version 9 and higher
            3.  Firefox version 38 and higher
            4.  Safari version 7 and higher

3.  Security Model
    ==============
    1.  The system provides multi-level access controls for the
        following roles: SuperAdmin, Admin, Scheduler, Scorer, Assignor,
        Referee

  | Functions                  | SuperAdmin  | Admin  | Scheduler  | Assignor  | Scorer  | Referee   |
  | -------------------------- | :---------: | :----: | :--------: | :-------: | :------ | :-------: |
  | Database Admin             | X           |        |            |           |         |           |
  | Profile Data Entry         | X           | X      |            |           |         |           |
  | Schedule Data Entry        | X           | X      | X          |           |         |           |
  | Assignments                | X           |        |            | X         |         |           |
  | Views (depending on Role)  | X           | X      | X          | X         | X       | X         |
  | User Profile Mgmt          | X           | X      |            |           |         | X         |
  | Match Reporting            | X           | X      |            |           | X       | X         |

4.  Navigation 
    ==========
    1. The application will have simple menus to navigate to the views ([samples](https://github.com/rrone/refscheduler/blob/master/screensnaps/menus.png)).  The menus are dynamic depending on the role of the user. 
    
    2. The menus provide navigation to the following functions to anyone accessing the application:
        * Schedules ([sample](https://github.com/rrone/refscheduler/blob/master/screensnaps/menu.schedules.png))
        * Results ([sample](https://github.com/rrone/refscheduler/blob/master/screensnaps/menu.results.png))
    
    3. The menus provide navigation to any registered official:
        * Referee Schedule ([sample](https://github.com/rrone/refscheduler/blob/master/screensnaps/menu.referee_schedules.png))
    
    4. The menus provide navigation to any user with admin privilege:
        * Admin ([sample](https://github.com/rrone/refscheduler/blob/master/screensnaps/menus.png))
    
    5. The menus provide navigation to any registered user:
        * My Account ([sample](https://github.com/rrone/refscheduler/blob/master/screensnaps/menu.myaccount.png))

5.  Application Functions
    ================
    1.  The application will have read connectivity with volunteer registration records and training records to access current Safe Haven, Concussion Training (CDC), Membership Year(MY) data for each official.

    2.  The application will verify and enforce eligibility by current Safe Haven, CDC, MY for all Referee accounts. Accounts will be given 30 day notice of expiring qualifications by email. Accounts failing eligibility will be flagged as ineligible and will not be available for assignments.
    
    3.  The application will be able to manage multiple competitions within one Section, Area or Region, i.e., Core program, Extra program, U16-U19 program, etc.
    
    4.  The application will be able to promote compeition pool play leaders to playoffs to medal rounds according to rules determined by the Admin.
    
    5.  All exported files to contain a concise descriptive name with a date and time stamp ("_yyyymmdd_hhmm").  All spaces in the filename to be underscore, e.g. ("officials_20160211_0912").
    
    4.  The application will provide referees with email or text notifications of upcoming assignments 48 hours in advance.
    
    5.  The application will send all Admins notification of unaccepted assignments 96 hours in advance of the match.
    
    6.  The application will send all Admins notification of declined assignments immediately.
    
    7.  Based on User provided AYSO Volunteer ID (8-digits), the application will add to the user profile view:
        * AYSO Section-Area-Region
        * Referee Badge Level (None, U-8, Basic, Intermediate, Advanced, National)
        NOTE: this data is not editable in this application but will contain a link to the source system, i.e., eAYSO

6.  Admin Functions
    ===============
    1. The Admin role will have the following functions
        2.  Communications Functions
           1.  The ability to send broadcast email and/or SMS text to all Referees:
                1.  By grade
                2.  Individually
                1.  With accepted assignments in a date range
                2.  With declined assignments in a date range
                3.  With assigned pending acceptance in a date range
                4.  Without unassignments in a date range
                5.  With current credentials
                6.  With out-of-date credentials
        
        2.  Account Management Functions
            1. View all officials in a matrix showing Account Information, Contact Information, AYSO Certfications, Competition availability (sample on request)
            2. Export list of all officials (to Excel) (sample on request).  The export filename to contain a "officials" and date and time stamp.
            3. View all officials with out-of-date credentials in a matrix showing Account Information, Contact Information, AYSO Certfications, Competition availability (sample on request).
            4. Export all officials with out-of-date credentials (to Excel) (sample on request).   The export filename to contain "ineligible_officials" and date and time stamp.
            5. View Staff Roles ([sample](https://github.com/rrone/refscheduler/blob/master/screensnaps/admin.view_staff_roles.png))
            6.  Print simplified roster of officials with contact info (name, email, phone number) by competition sorted by last name.
        
        3.  Referee Assignment Functions
            1.  View all referee assignments ([sample](https://github.com/rrone/refscheduler/blob/master/screensnaps/admin.view_referee_assignments.png))
            2.  Referee assignment view to be filterable by:
                1.  Games with issues.  An "issue" is open, pending, requested, turnback slots.
                2.  Games with open slots
                3.  Games with pending slots
                4.  Games with published slots
                5.  Games with requested slots
                6.  Games with turnback slots
            2.  Export Referee assignments to Excel ([sample](\#)).   The export to be selectable by program.  The export filename to contain "assignments" and date and time stamp.
            3.  Import Referee assignments from Excel (using the export as the defined template for import) ([sample](https://github.com/rrone/refscheduler/blob/master/screensnaps/admin.import_referee_assignments.png))
        
        4.  Schedule Management Functions
            1.  View game schedules ([sample](https://github.com/rrone/refscheduler/blob/master/screensnaps/admin.view_game_schedule.png)) filterable by date, programs, and division. Each filtered view to be exportable to Excel or as CSV text.
            2.  Export entire game schedule by program to Excel.  This export is the template for all imports.
            3.  View team schedules ([sample](https://github.com/rrone/refscheduler/blob/master/screensnaps/admin.view_game_schedule.png)) filterable by date, programs, and division. Each filtered view to be exportable to Excel or as CSV text.
            4.  Import & maintain match schedules from Excel or comma-separated variables (CSV): Date, time, competition, site, field, division, home team, home coach, away team, away coach.  Import template available by the Export function. ([sample](https://github.com/rrone/refscheduler/blob/master/screensnaps/admin.import_game_schedule.png))
        
        5.  Team Management Functions
            1.  View Teams
            2.  Export Teams to Excel (sample on request). The export filename to contain "teams" and date and time stamp.
            3.  Import and update teams ([sample](https://github.com/rrone/refscheduler/blob/master/screensnaps/admin.import_update_teams.png))
        
        6.  Match Reporting Functions
            1.  Enter match results ([sample](https://github.com/rrone/refscheduler/blob/master/screensnaps/admin.enter_match_results.png))
            2.  Export Pool Play Standings filterable by program to formatted Excel ([sample](https://github.com/rrone/refscheduler/blob/master/exports/ResultsPoolPlay20160211-0958.xlsx)). The export filename to contain "ResultsPoolPlay" and date and time stamp.
            3.  Export Playoff or Medal Round Standings filterable by program to formatted Excel ([sample](https://github.com/rrone/refscheduler/blob/master/exports/ResultsPlayoffs20160211-1000.xlsx)). The export filename to contain "ResultsPlayoffs" and date and time stamp.
            4.  Export Sportsmanship Standings filterable by program to formatted Excel ([sample](https://github.com/rrone/refscheduler/blob/master/exports/ResultsSportsmanship20160211-1004.xlsx)). The export filename to contain "ResultsSportsmanship" and date and time stamp.

        7.  Import and maintain fields by site and sub-site
        
        8.  Import and maintain divisions by program

7.  User Functions
    ==============
    1.  Each user will be able to maintain profile data including:
        *  Full Name
        *  First Name
        *  Last Name
        *  Nick Name
        *  Email address
        *  Best phone number
        *  AYSO Volunteer ID (8-digits)
    
    2.  Each user will be available to provide availability for assignments. This will be done by blocking dates,         partial-blocking parts of dates, clear by date or date range, time range, and providing maximum travel distance (in miles)
    
    3.  Each user will be able to block assignments (i.e., won’t take assignments) by site or other referees

    4.  Each user will be able to print their Referee schedule by date, field, team to PDF or Excel (selectable)

    5.  Each user will be able to accept, decline, or request turnback of match assignments 
    
    6.  Each user (as Referee) will be able to enter match results reporting ([sample](https://github.com/rrone/refscheduler/blob/master/screensnaps/admin.enter_match_results.png))

    7.  Each user (as Referee) will be able to complete and submit a match misconduct report in standard form ([sample](http://ayso1ref.com/lib/misconduct_report-fillin.pdf))

    8.  Each user will be able to complete and submit a match incident report in standard form ([sample](https://sites.google.com/site/ayso1dreferee/incident_report_form_with_instructions.pdf))

    9.  Each official will be able to print out team views (upcoming match assignments with teammates and their contact info)

    10. Each official will be able to complete and export to Excel a historical search of their assignments by date.

8.  Use Cases
    =========
    To be supplied upon request
