## Installation

```
npm install --save react-terminal-ui-metalware
```

## Usage

_React Terminal UI_ is a "dumb component"-- whatever props you pass in, it will render. You usually want to have
a smart, controller component that controls terminal state. For example:

```
import React from 'react';
import Terminal, { ColorMode, TerminalOutput } from 'react-terminal-ui';

const TerminalController = (props = {}) => {
  const [terminalLineData, setTerminalLineData] = useState([
    <TerminalOutput>Welcome to the React Terminal UI Demo!</TerminalOutput>
  ]);
  // Terminal has 100% width by default so it should usually be wrapped in a container div
  return (
    <div className="container">
      <Terminal name='React Terminal Usage Example' colorMode={ ColorMode.Light }  onInput={ terminalInput => console.log(`New terminal input received: '${ terminalInput }'`) }>
        { terminalLineData }
      </Terminal>
    </div>
  )
};
```

## Component Props

| Name                | Description |
| ------------------- | ------------- |
| name                | Name of the terminal. Displays at the top of the rendered component. In the demo, the name is set to _React Terminal UI_. |
| colorMode           | Terminal color mode - either Light or Dark. Defaults to Dark. |
| onInput             | An optional callback function that is invoked when a user presses enter on the prompt. The function is passed the current prompt input. If the `onInput` prop is not passed, the prompt input line will not display in the terminal. |
| startingInputValue  | Starting input value. If this prop changes, any user-entered input will be overridden by this value. Defaults to the empty string (""). |
| prompt              | The prompt character. Defaults to '$'. |
| height              | Height of the terminal. Defaults to 600px. |
| redBtnCallback      | Optional callback function for the red button. If provided, the function will be invoked when the red button is clicked. |
| yellowBtnCallback   | Optional callback function for the yellow button. If provided, the function will be invoked when the yellow button is clicked. |
| greenBtnCallback    | Optional callback function for the green button. If provided, the function will be invoked when the green button is clicked. |

### Development

Make sure to run `npm run install-peers` after `npm install` so peer dependencies are also installed.

## License

[MIT](https://opensource.org/licenses/MIT)

Termynal.js is also licensed under MIT, Copyright (C) 2017 Ines Montani.
