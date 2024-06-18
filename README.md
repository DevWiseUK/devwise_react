



### USING THE LIBRARY LOCALLY IN ANOTHER PROJECT FOR TESTING

To test the library locally, create a directory named example and then run the following command to initialize a React app in that directory:

```
npm create vite@latest . -- --template react-ts
npm install
```

Now, go to the root directory and build your npm package with the following command:

```
npm run build
```

To ensure you’re using the same version of React as your example app, run the following command from the root directory:

```
npm link "./example/node_modules/react"
```

Return to your example app’s directory and link your npm package to the example app using the package name you specified in its package.json. Replace {package-name} with your package's name.

```
npm link {package-name}
```

You can check whether the package is linked or not using the following command:

```
npm ls --location=global --depth=0 --link=true
```

Now, import the UI component from the library and test easily locally.

```
//App.tsx
import { Button } from "sld-ui-lib"; //replace name with you lib name

function App() {
  return <Button text="Button" />;
}

export default App;
```

After running the npm run dev command, you can test the locally published package.
