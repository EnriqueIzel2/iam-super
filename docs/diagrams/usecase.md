graph TD
Admin((Admin))
User((Standard User))
System[System]

    subgraph IAM_Super_System [IAM Super System]
        UC1(Manage Sectors)
        UC2(Manage Processes)
        UC3(Assign Processes to Sectors)
        UC4(Onboard New User)
        UC5(Generate Access Message)
        UC6(View Sector Processes)
        UC7(Audit Logs)
        UC8(Login / Logout)
    end

    Admin --> UC1
    Admin --> UC2
    Admin --> UC3
    Admin --> UC4
    Admin --> UC7
    
    User --> UC6
    User --> UC8
    
    UC4 -.->|include| UC5
    System --> UC5
    System --> UC7