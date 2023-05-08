Repositório de ACs - Frameworks FullStack - Bruno Raus / Pedro Henrico / Enrico Genaro

### Para executar o projeto:
### `npm start`

[http://localhost:3000](http://localhost:3000)

## AC2

[http://localhost:3000/apirequest](http://localhost:3000/apirequest)

## AC3

### Dependências do backend:
### `pip install -r backend/requirements.txt`

- Flask
- Flask CORS

[http://localhost:3000/flaskapi](http://localhost:3000/flaskapi)

Servidor da API está em ./backend/flask_api.py

###

from flask import Flask, jsonify
from flask_cors import CORS

app = Flask(__name__)
CORS(app)

@app.route('/flaskapi', methods=['GET'])
def flask_api():
    return jsonify([{
        'disciplina': 'Frameworks FullStack',
        'atividade': 'AC3',
        'aluno': 'Bruno Raus',
        'turma': 'SI4A',
        'ra': '2102648'
    }])

if __name__ == '__main__':
    app.run(debug=True)
    
##
    
    Flask==2.3.2
flask-cors==3.0.10

##

{
  "name": "reactapp01",
  "version": "0.1.0",
  "private": true,
  "dependencies": {
    "@testing-library/jest-dom": "^5.16.5",
    "@testing-library/react": "^13.4.0",
    "@testing-library/user-event": "^13.5.0",
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
    "react-router-dom": "^6.9.0",
    "react-scripts": "5.0.1",
    "web-vitals": "^2.1.4"
  },
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject"
  },
  "eslintConfig": {
    "extends": [
      "react-app",
      "react-app/jest"
    ]
  },
  "browserslist": {
    "production": [
      ">0.2%",
      "not dead",
      "not op_mini all"
    ],
    "development": [
      "last 1 chrome version",
      "last 1 firefox version",
      "last 1 safari version"
    ]
  }
}

##

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <link rel="icon" href="%PUBLIC_URL%/favicon.ico" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <meta name="theme-color" content="#000000" />
    <meta
      name="description"
      content="Web site created using create-react-app"
    />
    <link rel="apple-touch-icon" href="%PUBLIC_URL%/logo192.png" />
    <!--
      manifest.json provides metadata used when your web app is installed on a
      user's mobile device or desktop. See https://developers.google.com/web/fundamentals/web-app-manifest/
    -->
    <link rel="manifest" href="%PUBLIC_URL%/manifest.json" />
    <!--
      Notice the use of %PUBLIC_URL% in the tags above.
      It will be replaced with the URL of the `public` folder during the build.
      Only files inside the `public` folder can be referenced from the HTML.
      Unlike "/favicon.ico" or "favicon.ico", "%PUBLIC_URL%/favicon.ico" will
      work correctly both with client-side routing and a non-root public URL.
      Learn how to configure a non-root public URL by running `npm run build`.
    -->
    <title>React App</title>
  </head>
  <body>
    <noscript>You need to enable JavaScript to run this app.</noscript>
    <div id="root"></div>
    <!--
      This HTML file is a template.
      If you open it directly in the browser, you will see an empty page.
      You can add webfonts, meta tags, or analytics to this file.
      The build step will place the bundled scripts into the <body> tag.
      To begin the development, run `npm start` or `yarn start`.
      To create a production bundle, use `npm run build` or `yarn build`.
    -->
  </body>
</html>

##
![image](https://user-images.githubusercontent.com/104082146/236846187-c003b70d-3f16-4218-b90c-b7d5ab6a4a80.png)
![image](https://user-images.githubusercontent.com/104082146/236846256-3bbd043f-ffc0-4f48-814b-5d01ddd33c03.png)

##


{
  "short_name": "React App",
  "name": "Create React App Sample",
  "icons": [
    {
      "src": "favicon.ico",
      "sizes": "64x64 32x32 24x24 16x16",
      "type": "image/x-icon"
    },
    {
      "src": "logo192.png",
      "type": "image/png",
      "sizes": "192x192"
    },
    {
      "src": "logo512.png",
      "type": "image/png",
      "sizes": "512x512"
    }
  ],
  "start_url": ".",
  "display": "standalone",
  "theme_color": "#000000",
  "background_color": "#ffffff"
}


User-agent: *
Disallow:


.App {
  text-align: center;
}

.App-logo {
  height: 40vmin;
  pointer-events: none;
}

@media (prefers-reduced-motion: no-preference) {
  .App-logo {
    animation: App-logo-spin infinite 20s linear;
  }
}

.App-header {
  background-color: #282c34;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  font-size: calc(10px + 2vmin);
  color: white;
}

.App-link {
  color: #61dafb;
}

@keyframes App-logo-spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

##

import Sobre from './Sobre';
import Teste from './Teste';
import Header from './Header';
import TesteApi from './TesteApi';
import ConsumeFlaskApi from './ConsumeFlaskApi'
import { Routes, Route, Link } from 'react-router-dom';

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <Link to='/sobre'>Sobre</Link> <br></br>
        <Link to='/teste'>Teste</Link> <br></br>
        <Link to='/header'>Header</Link> <br></br>
        <Link to='/apirequest'>Request API</Link> <br></br>
        <Link to='/flaskapi'>Request Flask API</Link> <br></br>
      </header>
      <main>
        <Routes>
            <Route path='/sobre' element={<Sobre/>}/>
            <Route path='/teste' element={<Teste/>}/>
            <Route path='/header' element={<Header/>}/>
            <Route path='/apirequest' element={<TesteApi/>}/>
            <Route path='/flaskapi' element={<ConsumeFlaskApi/>}/>
        </Routes>
    </main>
    </div>
  );
}

export default App;

##

import { render, screen } from '@testing-library/react';
import App from './App';

test('renders learn react link', () => {
  render(<App />);
  const linkElement = screen.getByText(/learn react/i);
  expect(linkElement).toBeInTheDocument();
});


import React, { useState, useEffect } from 'react';

export default function FlaskApi(){

    const [msg, setMsg] = useState();

    const getApiData = async () => {
        const response = await fetch(
          "http://localhost:5000/flaskapi"
        ).then((response) => response.json());

        setMsg(response);
        };

        useEffect(() => {
            getApiData();
        }, []);
        return (
            <div className="app">
                {msg && msg.map(msg => (
                    <div className="item-container">
                        <p>Aluno: {msg.aluno}</p>
                        <p>Turma: {msg.turma}</p>
                        <p>RA: {msg.ra}</p>
                        <p>Disciplina: {msg.disciplina}</p>
                        <p>Atividade: {msg.atividade}</p>
                        </div>
                ))}
            </div>);
}

##

.Header {
    display: flex;
    flex-direction: column;
    text-align: center;
    align-items: center;
    justify-content: center;
}


import './Header.css'

function Header () {

    return (
        <header>Teste Header</header>
    )

}

export default Header;


##

import { Link } from "react-router-dom";

export default function RotaTest(){
   return (
       <div>
           <h1>Usuário</h1>
           <Link to="/">Retornar a página inicial</Link>
       </div>
   );
}

##

import React from "react";
import { Link, useLocation } from 'react-router-dom'

##

export default function Sobre (){
    const location = useLocation();
    return (
        <div>
            <h1>Path: {location.pathname}</h1>
            <Link to="/">retornar a página inicial</Link>
        </div>
    );
}

##

.Teste {
    display: flex;
    flex-direction: column;
    text-align: center;
    align-items: center;
    justify-content: center;
}


import './Teste.css'

function Teste() {

    return (
        <div>
            <h1>Página de teste!</h1>
        </div>
    )

}

##

export default Teste;

##

import React, { useState, useEffect } from 'react';

export default function Alunos(){

    const [users, setUsers] = useState();

    const getApiData = async () => {
        const response = await fetch(
          "https://jsonplaceholder.typicode.com/todos/"
        ).then((response) => response.json());

        setUsers(response);
        };

        useEffect(() => {
            getApiData();
        }, []);
        return (
            <div className="app">
            {users && users.map((user) => (
            <div className="item-container">
            Id:{user.id} - Title: {user.title} 
            </div>
        ))}
        </div>);
}

##

body {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen',
    'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue',
    sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

code {
  font-family: source-code-pro, Menlo, Monaco, Consolas, 'Courier New',
    monospace;
}

##

body {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen',
    'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue',
    sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

code {
  font-family: source-code-pro, Menlo, Monaco, Consolas, 'Courier New',
    monospace;
}

##


![image](https://user-images.githubusercontent.com/104082146/236848647-6c1b88c2-10ba-4e2e-9b87-ed87f28459ec.png)

##

const reportWebVitals = onPerfEntry => {
  if (onPerfEntry && onPerfEntry instanceof Function) {
    import('web-vitals').then(({ getCLS, getFID, getFCP, getLCP, getTTFB }) => {
      getCLS(onPerfEntry);
      getFID(onPerfEntry);
      getFCP(onPerfEntry);
      getLCP(onPerfEntry);
      getTTFB(onPerfEntry);
    });
  }
};

##

export default reportWebVitals;

##


// jest-dom adds custom jest matchers for asserting on DOM nodes.
// allows you to do things like:
// expect(element).toHaveTextContent(/react/i)
// learn more: https://github.com/testing-library/jest-dom
import '@testing-library/jest-dom';
