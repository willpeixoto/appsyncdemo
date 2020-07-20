# Demo project using serverless framework and AppSync

we are going to use serverless-framework who can be found here server

we also need to install this plugins in our projects.
    - serverless-plugin-additional-stacks
        With that we can manage our cloudFormation resourses separatly from the main projest, but what that means ?
        If you need to remove your serlerless-functions you don´t loose resources created in aditional stack, maybe you want to change for serverless for another technology, you can just remove main stack and your resources will still there for another services.
        this is a goob practice because you can module all your resources needed.
        Because of this plugin, we are going to share resources names in our stack.
        npm install --save serverless-plugin-additional-stacks

    - serverless-offline
        For offline debugging propose, because is for debugging remenber to install as a development dependency =D
        npm install serverless-offline --save-dev

    - serverless-appsync-plugin
        npm install serverless-appsync-plugin
        Because we want to use AppSync in our app and GraphQl resolvers, the beauty here is you can call resources directly like aws cloudSearch, DynamoDb, LambdaFunctions, with the help of graphQl Validators we have garanty of type of data we are receiving, no need to validate fields at all graphQL made that for us. :D
