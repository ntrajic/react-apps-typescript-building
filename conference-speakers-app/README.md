# Building React Apps with TypeScript

  This is a sample JavaScript conference-speakers application for the Building React Apps with TypeScript.


## Installation

  Run `npm run install-deps` at the root of the project and it will install all the dependencies.

## Running the javascript app

  Run `npm run start` at the root of the project.

  The API is available at /api.

  The example app used is available at /app.

        C:\SRC\React\react-apps-typescript-building\conference-speakers-app>npm run start

        > conference-speakers@1.0.0 start C:\SRC\React\react-apps-typescript-building\conference-speakers-app
        > run-p app api


        > conference-speakers@1.0.0 app C:\SRC\React\react-apps-typescript-building\conference-speakers-app
        > cd app && npm run start


        > conference-speakers@1.0.0 api C:\SRC\React\react-apps-typescript-building\conference-speakers-app
        > cd api && npm run start


        > globomantics-react@0.1.0 start C:\SRC\React\react-apps-typescript-building\conference-speakers-app\app
        > react-scripts start


        > graphqlapi@1.0.0 start C:\SRC\React\react-apps-typescript-building\conference-speakers-app\api
        > nodemon index.js --ignore 'data'

        [nodemon] 2.0.22
        [nodemon] to restart at any time, enter `rs`
        [nodemon] watching path(s): *.*
        [nodemon] watching extensions: js,mjs,json
        [nodemon] starting `node index.js server.js`
        graphQL running at port 4000
        [HPM] Proxy created: /  -> http://localhost:4000
        i ｢wds｣: Project is running at http://192.168.1.68/
        i ｢wds｣: webpack output is served from
        i ｢wds｣: Content not from webpack is served from C:\SRC\React\react-apps-typescript-building\conference-speakers-app\app\public
        i ｢wds｣: 404s will fallback to /
        Starting the development server...
        Compiled successfully!

        You can now view globomantics-react in the browser.

          Local:            http://localhost:1337
          On Your Network:  http://192.168.1.68:1337

        Note that the development build is not optimized.

## Module Layout

#### main branch, and first step branch
  The first module is about updating the existing javascript application to use TypeScript, check out the `main` branch for a default implementation of the app written in javascript. You can use this project (or any javascrit project you have) to start with.

  To convert conference-speakers-app into a TypeScript one:
    package.json:
    "scripts": {
    "app": "cd app && npm run start",
    "api": "cd api && npm run start",
    "start": "run-p app api",                                                                                                // npm run start <enter>      // will start react-js in dev mode
    "install-deps": "cd api && npm install && cd .. && cd app && npm install && cd .. && npm install"                        // preparing javascript's <node_modules> for both /api and /app directory to be installed
    },

    0. CONFIGURING AN EXISTING JAVASCRIPT REACT APP into REACT TYPESCRIPT APP 
	      cd conference-speakers-app <enter>
        npm run install-deps <enter>                // against package.json w/ dependencies: 
                                                    // typescript, @types/react,     @types/react-dom, @types/node 

    NOTE: when there's no package.json, then add these dependecies manually into package.json:
        npm add typescript @types/react @types/react-dom @types/node

    1. git mv .\app\src\App.jsx .\app\src\App.tsx   //move app/src/App.jsx app/src/App.tsx
    2. npm run start <enter>                        // this will create and configure: tsconfig.json file !!!!

    3. conference-speakers-app\app> git add tsconfig.json 
    where its content is:

    {
      "compilerOptions": {
        "target": "es5",
        "lib": [
          "dom",
          "dom.iterable",
          "esnext"
        ],
        "allowJs": true,
        "skipLibCheck": true,
        "esModuleInterop": true,
        "allowSyntheticDefaultImports": true,
        "strict": true,
        "forceConsistentCasingInFileNames": true,
        "module": "esnext",
        "moduleResolution": "node",
        "resolveJsonModule": true,
        "isolatedModules": true,
        "noEmit": true,
        "jsx": "react"
      },
      "include": [
        "src"
      ]
    }


#### second step branch
    The second module covering class and function components is located from the `m3-class-and-function-components` branch to start, and the completed example is in the `m3-class-and-function-components-final` branch.

    - Class components
        - implementing error boundary with props and state
        - working with component children
    - Function components
        - implementing navigation link
        - warning of potential bugs
        - self-documenting code

    files:
    conference-speakers-app/app/src/pages/conference/Conference.tsx
    conference-speakers-app/app/src/pages/conference/ErrorBoundary.tsx
    conference-speakers-app/app/src/pages/conference/Navigation.tsx


#### third step branches
    The last module follows the same pattern, with the initial starting point in the `m4-declaring-and-using-hooks-with-typescript` branch and the final code in the `m4-declaring-and-using-hooks-with-typescript-final` branch.

    React hooks provide way:
    - To use State, context, side-effects (data fetching) or interact with DOM
    - To compose custom hooks to encapsulate functionality in our code
    - Typescript enables type safe interactions

    TypeScript conversion:

    1. useState hook and Context
    2. useEffect hook (for composing custom hooks)
    3. useReducer and useRef hooks
    4. how TypeScript is used for dealing w/ input in forms
    5. working w/ APIs to ensure data structs are working as we expect



    conference-speakers-app/api/resolvers/speakers.js
    conference-speakers-app/app/graphql-types.ts
    conference-speakers-app/app/src/App.tsx
    conference-speakers-app/app/src/App.tsx
    conference-speakers-app/app/src/AuthLink.tsx
    conference-speakers-app/app/src/graphql-types.ts
    conference-speakers-app/app/src/useAppInit.tsx
    conference-speakers-app/app/src/context/AuthProvider.tsx
    conference-speakers-app/app/src/pages/conference/sessions/AddSession.tsx
    conference-speakers-app/app/src/pages/conference/sessions/CREATE_SESSION.tsx
    conference-speakers-app/app/src/pages/conference/sessions/SESSION_BY_ID.tsx
    conference-speakers-app/app/src/pages/conference/sessions/SessionDetails.tsx
    conference-speakers-app/app/src/pages/conference/sessions/SessionForm.tsx
    conference-speakers-app/app/src/pages/conference/sessions/SessionFormVanilla.tsx
    conference-speakers-app/app/src/pages/conference/sessions/SessionItem.tsx