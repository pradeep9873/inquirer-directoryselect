# inquirer-directoryselect

A directory prompt for [Inquirer.js](https://github.com/SBoudrias/Inquirer.js).

This project is a fork of [Inquirer-directory](https://github.com/nicksrandall/inquirer-directory) which does not limit the navigation to the current folder.
 
## Installation

```bash
npm install --save inquirer-directoryselect
```

## Features

-   Support for symlinked files
-   Vim style navigation
-   Search for file with "/" key

### Key Maps

-   Press "/" key to enter search mode.
-   Press "-" key to go up (back) a directory.
-   Press "." key to select the current directory.

## Usage

This prompt is anonymous, meaning you can register this prompt with the type name you please:

```javascript
inquirer.registerPrompt('directory', require('inquirer-directoryselect'));
inquirer.prompt({
  type: 'directory',
  ...
})
```

Change `directory` to whatever you might prefer.

### Parameters

Takes `type`, `name`, `message`, `basePath`, `options` properties.

See [inquirer](https://github.com/SBoudrias/Inquirer.js) readme for meaning of all except **basePath**.

**basePath** is the relative path from your current working directory
 

```javascript
inquirer.registerPrompt('directory', require('inquirer-directoryselect'));
inquirer.prompt([{
  type: 'directory',
  name: 'from',
  message: 'Where you like to put this component?',
  basePath: './src'
}]).then(function(answers) {
  //etc
});
```

### Options

#### options.displayFiles

default ***false***

Set this to true if you to display files

```javascript
inquirer.prompt([{
  type: 'directory',
  //...
  options: {
      displayFiles:true
  }
}]).then(function(answers) {
  //etc
});
```

#### options.displayHidden

default ***false***

Set this to true if you to display hidden folders (and files if displayFiles is set to `true`) 

```javascript
inquirer.prompt([{
  type: 'directory',
  //...
  options: {
      displayHidden:true
  }
}]).then(function(answers) {
  //etc
});
```

## License

MIT