## Login Process
```mermaid
sequenceDiagram
  autonumber
    actor User
    participant FE as Website
    participant OneLogin

    User->>FE: Visits Website
    Note over FE: checks from cookie
    FE->>FE:Check cookies if already logged in
    alt User Not Logged In
        
        FE-->>OneLogin: Redirect to One Login
        note over User, OneLogin: Repeat Process
        OneLogin->>User: Diplay Login Page

        
        User->>+OneLogin: Enter Credentials
        alt Credentials Correct
            note over User, OneLogin: Until Correct Credential is given
            OneLogin-->>FE: Pass Token to Callback Page
            create participant UR as Get User Info
            FE--)UR: Perform Get User Info
        else Credentials Incorrect
            
            OneLogin-->>-User: Show Error Message
            User->>OneLogin: Retry Entering Credentials

            note over User, OneLogin: Or until user exit page         
        end
    else User Logged In
            FE--)UR: Perform Get User Info
    end

```

## Get User Info
```mermaid
sequenceDiagram
  autonumber
    actor User
    participant FE as Website
    participant API
    
    

    FE->>API: Get User Info
    FE->>API: Calls api/common/getuserinfo
    alt User not in DB
        API-->>FE: data is OneLogin token content
    else User in DB
        API-->>FE: data is data details
    end
    alt User in DB
        par
        FE->>User: Display content
        create participant E as Process End
        FE->>E: End Process
        end
    else
        FE->>User: Display Error
        create participant R as Registration Process
        FE--)R: Perform Regitration Process
    end
```
## Regitration Process
```mermaid
sequenceDiagram
  autonumber
    actor U as User
    participant FE as Website
    participant API
    participant M as MailServer
    participant E as Process End

    FE->>U: Display Site Registration Form
    alt Proceed Registration
        U->>U: Key in need details
        U->>FE: Submit Form
        FE->>API: Calls Register API
        API->API: Performs registration process
        API->>M: Send Email with regitration link
        
        M->>U:Recieves Email
        U->>API:Open email and click link
        API->>API: Link One Login ID with DB User key [uuid]
        API->>M: Send Registration success Email
        M->>E:End Process
    else Cancel Regitration
        U->>E:Cancel/Exit Website
    end

```

[1]:https://chatgpt.com/
[2]:https://www.datacamp.com/cheat-sheet/markdown-cheat-sheet-23
[3]:https://mermaid.js.org/syntax/sequenceDiagram.html
