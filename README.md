# Postman API Automation Integration with Github Action #

This repository is a demostration for POC for integrating your postman tests with github actions. The tests are written in postman and they are executed on the virtual machine with the help of newman and newman-reporters-htmlextra.
Github Aciton will trigger the project execution on every push to the main branch. You can also execute the project manually using workflow_dispatch. The project works on the scehdule time with the help of CRON Job.
The html reportes is achieved and kept in the artifact section for the team to download along with that they can view the report directly from the github page: https://yashwanthk-idexcel.github.io/In-warranty-Flow-Collection/.
The Latest Report is mailed to the team members using Gmail SMTP.

## Testing Coverage ##
1. Happy Flow Testing
2. NEgative Testing
3. Edge Case Testing
4. Token Testing
5. Data Driven Testing with csv
6. Scehema Validation
7. Secrets Management with Github Secrets

## Tech Stack ##
1. Postman
2. Newman
3. Newman-reporter-htmlextra
4. NodeJS v22
5. Github Action
6. Gmail SMTP
7. Github Pages
8. csv for data driven testing
9. AWS EC2 instance for self hosted github runner

## Github Pages ##
You can directly view the latest test report of the Postman test at the Github Page - https://yashwanthk-idexcel.github.io/In-warranty-Flow-Collection/.

## HTML Report ##
The report will be created in the newman folder
![Postman Report](https://github.com/Yashwanthk-idexcel/In-warranty-Flow-Collection/blob/static-content/newman-report.png)
- if above line doesn't work, use below line 
![Postman Report](https://raw.githubusercontent.com/Yashwanthk-idexcel/In-warranty-Flow-Collection/static-content/newman-report.png)

## Project Structure ##
```
In-warranty Flow Collection
├─ In-warranty_Flow_Collection_Excel_Data.postman_collection.json #Collection File with DDT
├─ In-warranty_Flow_Collection_Random_Data.postman_collection.json #Collection File with Random Data
├─ In-warranty_Flow_TestData.csv #Test Data file for DDT
└─ QA.postman_environment.json #Environment variables file
```

## how to run the project? ##
You can run the project on your local system, for that:
1. Clone the project on your local system - https://github.com/Yashwanthk-idexcel/In-warranty-Flow-Collection.git
2. Install Nodejs and npm from https://nodejs.org/en
3. Install newman -> ``` npm install -g newman ```
4. Install newman-reporter-htmlextra -> ``` npm install -g newman-reporter-htmlextra ```
5. Run the newman command:
```
            newman run In-warranty_Flow_Collection_Random_Data.postman_collection.json \  
            -e QA.postman_environment.json \
            -r cli,htmlextra \
            --reporter-htmlextra-export ./newman/index.html
```



