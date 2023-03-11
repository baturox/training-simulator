# reactjs-gyroscope

This package allows to read gyroscope data [Gyroscope](https://developer.mozilla.org/en-US/docs/Web/API/Gyroscope).

## Installation
```sh
yarn add reactjs-gyroscope
```

## Usage

```jsx
import { useState } from 'react'
import { getGyroscope, gyroscopePermission } from 'reactjs-gyroscope';

function App() {
  const [start, setStart] = useState(false);

  const gyroscope = start && getGyroscope((event) => {
    console.log(event)
  });

  return (<>
    <button onClick={() => {
      gyroscopePermission().then(response => {
        if (response) {
          setStart(true);
        }
      });
    }}>Start</button>
  </>);
}

export default App;
```

## Notes

Needs permission for deviceorientation event.  (a.k.a. only using HTTPS).

## License

LGPL-3.0