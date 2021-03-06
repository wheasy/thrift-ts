# thrift-ts

`thrift-ts` is a typescript compiler that compile *.thrift files to *.d.ts files.
It should works with `thrift --gen js:node` commands.

## Installation
```bash
$ npm install -g thrift-ts
```

## How to use
### CLI
```bash
// just compile one file
thrift-ts Model.thrift

// compile all IDL files in the folder and output in other folder
thrift-ts ./src -o ./dist
```

### Node
```js
import thriftTs from 'thriftTs';
import fs = require('fs');

const filename = './Model.thrift';
const files = thriftTs({
  filename,
  content: fs.readFileSync(filename),
});

console.log(files);
// [{ filename: 'Model_types.d.ts', content: '...'}]
```

