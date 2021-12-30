### Version

27.4.5

### Steps to reproduce

1. clone repo https://github.com/rainbow-industries/jest-bug
2. npm i
3. npm test
4. experience the bug
```bash
npm test

> jest-bug@1.0.0 test
> jest --config=jest.config.js

 FAIL  ./demo.test.js
  ● Test suite failed to run

    TypeError: Cannot read properties of undefined (reading 'bind')

      at Runtime._createJestObjectFor (node_modules/jest-runtime/build/index.js:2193:46)

Test Suites: 1 failed, 1 total
Tests:       0 total
Snapshots:   0 total
Time:        0.372 s
Ran all test suites
```

### Expected behavior

I expect the test not to fail since it just contains one console.log statement.

### Actual behavior

The test fails with an error that looks very similar to this rejection: https://github.com/facebook/jest/issues/12189#issuecomment-1001059449 

### Additional context

I'd like to run test without transformations with ES Modules. That's the reason i use `jest-environment-jsdom-sixteen` as `testEnvironment` in the config.

### Environment

```shell
System:
  OS: Linux 5.11 Ubuntu 20.04.3 LTS (Focal Fossa)
  CPU: (16) x64 AMD Ryzen 7 2700X Eight-Core Processor
Binaries:
  Node: 16.13.1 - /usr/bin/node
  npm: 8.1.2 - /usr/bin/npm
npmPackages:
  jest: ^27.4.5 => 27.4.5
```
