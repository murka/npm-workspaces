# How to work with NPM Workspaces?
First, read the official documentation, please: [Docs](https://docs.npmjs.com/cli/v7/using-npm/workspaces)
### Getting started with workspaces?

For start, init npm project: ```npm init --yyq```  
Also you can use basic template:
```json
{
  "private": true,
  "workspaces": [
    "packages/*"
  ]
}
```

### How to init a workspace for a basic template?
For this, you can use command: ```npm init -w ./packages/<workspace>```  
And you get it:
```
.
+-- node_modules
|  `-- <workspace> -> ../<workspace>
+-- package-lock.json
+-- package.json
`-- packages
   `-- <workspace>
      `-- package.json
```

### How to add dependencies to a workspace?
For one workspace you can use command:  
```npm i <package> -w ./packages/<workspace>```  
and for all workspaces:  
```npm i <package> -ws```

### How to add one workspace to another?
To solve this problem, you can use: ```npm i ./packages/<workspace> -workspace=<workspace>```

### How to require/import one workspace from another?
First, you must add one workspace to second, after:  
For JavaScript:
```javascript
const workspace = require('workspace')
```  

And TypeScript:
```typescript
import workspace from 'workspace'
```
