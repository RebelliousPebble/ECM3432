Glenn First Draft
--------
Capture Platform: (surveymonkey)
- Lightweight web application, simple HTML and CSS with a JavaScript or .NET backend
- Lightweight as possible.as it will need to open quickly on possibly bad connections or slow devices. Can't guarantee anything, but chances are it'll be accessed on a phone as people leave the museum
- Something such as an ASP.NET site would achieve this with WASM and custom controls, allowing for questionnaires and surveys.
- React is very heavy for low powered devices

Storage and Analysis Platform: (literally any cots BI system)
- Could use an existing business information system that would handle all of the data as well as the analysis but the task says no
- So probably a non-relational / NoSQL database to store the data as it will be in multiple forms and relations will be difficult to create/design
- REST interface to submit the data 
- GraphQL to access data. Data can be batched, and analysis done locally
- Process that pulls data from external sources automatically, or a manual import 
- Analysis process done on a schedule (cron?) that analyses data and stores it based on preconfigured rules that can be setup from the access platform.
- Realistically analysis could be done by connecting the GraphQL interface to PowerBI.

Reporting Platform: (powerbi)
- Reporting client for the storage platform
- Could be another credential protected web interface, or alternatively a more advanced desktop application
- WPF for desktop app, Blazor Pages (WASM) for a webpage, accelerates processing power by using the WASM compiler
- Accesses the analysis results, and allows analysis to be configured and run on demand.
- Regular jobs can be configured as needed, or run as one offs
