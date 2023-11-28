# Pinelabs React SDK
Pinelabs SDK helps in redirecting users to the specified test and production env with the help of the payment token. It provides a simple to use `usePinelabs()` hook for accessing a single method on it `open()`.

The `usePinelabs()` takes a single argument which is `mode (boolean)`. Set mode to `true` if testing in test env and `false` if running in production mode. It returns a single method which is `open()` It takes a single argument which is a payment token. When called it will open up a new tab with the payment url for user to make payment.


### Installation
In order to install this SDK you need to follow the following steps:

1. Extract SDK on your system locally somewhere
2. Run `yarn` or `npm install` or `npm i`
3. Build the sdk using `npm run build`
4. Now install using `yarn add file:./../{path_to_sdk}` or run `npm link  ../{path_to_sdk}` and `npm install ../{path_to_sdk}`

### Usage Sample
```javascript
import { useEffect, useState } from 'react'
import reactLogo from './assets/react.svg'
import viteLogo from '/vite.svg'
import './App.css'
import { usePinelabs } from "pine-react";

function App() {
  const [count, setCount] = useState(0);
  const { open } = usePinelabs(true);

  return (
    <>
      <div>
        <a href="https://vitejs.dev" target="_blank">
          <img src={viteLogo} className="logo" alt="Vite logo" />
        </a>
        <a href="https://react.dev" target="_blank">
          <img src={reactLogo} className="logo react" alt="React logo" />
        </a>
      </div>
      <h1>Vite + React</h1>
      <div className="card">
        <button onClick={() => open("S01amrEDNYPdrlJqqECyX75Q6bRNGaqLjkwXIucWvHwc30%3d")}>
          count is {count}
        </button>
        <p>
          Edit <code>src/App.jsx</code> and save to test HMR
        </p>
      </div>
      <p className="read-the-docs">
        Click on the Vite and React logos to learn more
      </p>
    </>
  )
}

export default App
```
