[How To Set Up a Node Project With Typescript](https://www.digitalocean.com/community/tutorials/setting-up-a-node-project-with-typescript)

1. Create the project folder.
2. `npm init`
3. Install typescript deps
`npm install -D typescript`
`npm install -D tslint`
4. Configure typescript
Quick way: `tsc --init` -> creates tsconfig.json
Configure typescript linting: `./node_modules/.bin/tslint --init` -> creates tslint.json
Add the `"no-console": false` to `"rules":{}`
In `tsconfig.json` set `"outDir"` to `"dist"`
5. Update the package.json file with new npm scripts to run the project
update `"main": "dist/app.js"`
update `"scripts"` with `"start": "tsc & node dist/app.js",`
The tsc command tells TypeScript to compile the application and place the generated .js output in the specified outDir directory as it is set in the tsconfig.json file.
6. Make an `/src` directory and create an `app.ts` file there

[Get started with Apollo Server](https://www.apollographql.com/docs/apollo-server/getting-started/)

7. `npm install apollo-server graphql`
8. Follow example server setup

9. Install `ts-node` to run Typscript files without first compiling it to plain JavaScript
`npm i -g ts-node`
ex) `ts-node src/app.ts`

10. Install `nodemon`: `npm install --save-dev nodemon`
Add scripts to `package.json` that run `nodemon`
ex)
```
  "scripts": {
    "build": "tsc",
    "dev": "nodemon --watch 'src/**/*.ts' --exec 'ts-node' src/app.ts",
    "start": "tsc && node dist/app.js",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  ```

Then run `npm run dev` to start your development server.