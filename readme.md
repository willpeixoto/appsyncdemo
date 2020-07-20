# Demo project using serverless framework and AppSync

we are going to use serverless-framework who can be found here server

what kind of service we are going to simulate ?
    Let´s work as a BillPayment simulation ?        
        - what we need for our use case ?
                - sign-up, at the first time you register in our company we are going to create a account at our bank for you,
                    this account will be create just providing a simple form, with FullName, phoneNumber, e-mail addres.
                        when new users is created, we need to create money for that client, how we have infinity money all our clients receive a bonus to use our service. AppSync + (cognito + event post creation lambda consumer).
                - login - username + password (cognito).
                - createmoney - this is for free and no need validate, just create infinite money for you.

                - create randomly fake Bills, our random process will generate some random amount and a random identificator.
                    at this time we are just return the amount and the identificator.

                - verify bills, we are going to receive the bill number that number represent the barcode number, and the amount.

                - pay bills, lets receive the barcode, amount and the summary, think we have infinity money and don´t need to validate if i have money or not we just will pay all bills.

                - confirm payment, at this time maybe we want to send e-mail confirmation. ? how much time we have yet ?

        Yes, ok lets think aboutpaying bills, what we nedd to pay a bill ?
        we need to provide a number for some bills, for that lets create some use cases.
        create-bill (we create some random number)
        validate-bill (we receive some value ) and validate if this bill are in our currently data-base


we also need to install this plugins in our projects:

    - serverless-plugin-additional-stacks
        With that we can manage our cloudFormation resourses separatly from the main projest, but what that means ?
        If you need to remove your serlerless-functions you don´t loose resources created in aditional stack, maybe you want to change for serverless for another technology, you can just remove main stack and your resources will still there for another services.
        this is a goob practice because you can module all your resources needed.
        Because of this plugin, we are going to share resources names in our stack.
        npm install --save serverless-plugin-additional-stacks
        /*commands 
            - sls deploy additionalstacks  to deploy only additionalstacks

            - sls remove additionalstacks --stack [stackname]

        */

    - serverless-offline
        For offline debugging propose, because is for debugging remenber to install as a development dependency =D
        npm install serverless-offline --save-dev

    - serverless-appsync-plugin
        npm install serverless-appsync-plugin
        Because we want to use AppSync in our app and GraphQl resolvers, the beauty here is you can call resources directly like aws cloudSearch, DynamoDb, LambdaFunctions, with the help of graphQl Validators we have garanty of type of data we are receiving, no need to validate fields at all graphQL made that for us. :D
