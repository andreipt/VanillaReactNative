# React Native Test Project

## Testing the "naming collision" error:

Related React Native issue: https://github.com/facebook/react-native/issues/11200

Running `react-native start --reset-cache` on the current project results in the following error:
```
jest-haste-map: @providesModule naming collision:
  Duplicate module name: inquirer
  Paths: /CoolProject/node_modules/react-native/node_modules/yeoman-generator/node_modules/inquirer/package.json collides with /CoolProject/node_modules/react-native/node_modules/inquirer/package.json

This warning is caused by a @providesModule declaration with the same name across two different files.
jest-haste-map: @providesModule naming collision:
  Duplicate module name: lodash
  Paths: /CoolProject/node_modules/react-native/node_modules/lodash/package.json collides with /CoolProject/node_modules/react-native/node_modules/inquirer/node_modules/lodash/package.json

This warning is caused by a @providesModule declaration with the same name across two different files.
jest-haste-map: @providesModule naming collision:
  Duplicate module name: cli-width
  Paths: /CoolProject/node_modules/react-native/node_modules/yeoman-generator/node_modules/cli-width/package.json collides with /CoolProject/node_modules/react-native/node_modules/cli-width/package.json

This warning is caused by a @providesModule declaration with the same name across two different files.
```

If the dependencies are updated to the following versions, packager will run successfully:
```
"dependencies": {
    "inquirer": "^0.12.0",
    "lodash": "^3.10.1",
    "yeoman-generator": "^0.21.2",
    "react": "15.3.1",
    "react-native": "0.36.0"
  },
```
