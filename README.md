# feedback-screenshot

[![](https://img.shields.io/npm/v/feedback-screenshot.svg?style=flat-square)](https://www.npmjs.com/package/feedback-screenshot)

Feedback tool for only screen shot similar to Google's.

This is a component extracted from [@ivoviz/feedback.js](https://github.com/ivoviz/feedback)

![](https://raw.githubusercontent.com/gogogoghost/feedback-screenshot/dev/readme/demo.gif)

### Installing

```
npm install feedback-screenshot
```

### Usage

```js
import Feedback from 'feedback-screenshot';

const feedback = new Feedback({
  //default:#347EF8(blue)
  borderColor:'#000',
  
  //zIndex of screen shot content
  //default:999
  zIndex:200,
  
  //content will append to
  //default:document.body
  parent:document.querySelector('#content'),
  
  //html2canvas options
  //default:{}
  html2canvas:{
    logging:false,
    useCROS:true
  }
})

//start screen shot
feedback.open();

//change rect background to black, cover some private data
feedback.setBlackMode(true);

//close screen shot and wait for canvas
feedback.close().then(canvas=>{
  console.log(canvas);
})

//cancel screen shot, will return null
feedback.close(true)
```

