# QA Production Sanity
This is QA-Production-Sanity automation project.

### Get the code
_Git:_

`ssh://git@bitbucket:7999/qat/qa-production-sanity.git`

### Use Gradle
Double click on individual task (/Tasks/verification) on the Gradle tab or Open a command window and run:

For PROD:

 `./gradlew PROD_CHROME --info `

 `./gradlew PROD_API --info `

For CI:

`./gradlew CI_CHROME --info `

`./gradlew CI_API --info `

For STG:

`./gradlew STG_CHROME --info `

`./gradlew STG_API --info `



 ### Prerequisite for all the environments
 1. Disable ReCAPTCHAs before running below test cases and enable them afterwards.

    `SP-PostBillPayWithBillpayCode.feature`

    `SP-PostBillPayUnbranded.feature`

    `SP-SecureBillUnbranded.feature`

    `NT-PayByWeb.feature`

 2. Replace the masked 3ds_card_number with the live 3DS card number in production.data if you run the test cases in local.

#  Below are the existing issues, due to some env/UI/ issues 
# QA STG/CT Sanity Manually Task
    1. PostbillpayBupa---IncognitoMode
    2. CheckDailyReport-Intranet
    3. 3DS Via DirectPost 2 [Using 3DS2 by creating order-Id]

#  QA CT Sanity Manually Task
    QBE-URL Not avaialble, kindly check yara valley branded page
#  QA STG Sanity Manually Task
    NT payment via Directpost-1 as STG option not avaiable on UI
    DDA
    HPP - If captcha is disabled, it should work through Automation
    http://ddddddddtransact/   [https is included in Suit]
    PayByWeb
    aus-post-mail-redirection.url
#   STG API 
    PostBillPayWebAPI SNIP
    XML-Transaction Register Service
    NT-Direct enetry for merchant-4CD00 
      
SubProjects Commands:
To run all the projects one after the other:
`./gradlew clean build `

To run all the subprojects in parallel
`./gradlew clean build --parallel `

To run only one subproject:
`./gradlew :sp:test clean build `
`./gradlew :nt:test clean build `

To build aggregated allure report
`./gradlew allureAggregateReport `

To build aggregated allure report and open in browser
`./gradlew allureAggregateServe `
