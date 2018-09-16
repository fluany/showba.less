# showba.less

## Description

showba.less will help you write media queries the easy way, plus other interesting functions to make you more productive coding css

## Media query

### .below and .above

You can only send a special letter that we reserve with fixed values that we consider appropriate for each modality.                  
.below will use the value of the last letter and set it to a max-width.                      
The .above will set in min-width  

Variables
```less
 @xs: 400px;                                     
 @m: 800px;                                      
 @l: 1050px;                                     
 @xl: 1800px;                                    
 @hd: 2200px;                                    
```

Detail, you do not pass the letter with the '@' the treatment is done by us.

#### .below

Example
```less
.yourclass {                                 
  .below (xs, {                              
    yourstyle                               
  });                                      
}    
```
Result
```css
.yourclass {                                 
  @media only screen and (max-width: 400px) {
    yourstyle                              
  }                                          
}
```
#### .above

Example
```less
.yourclass {                                    
  .above (l, {                                  
    yourstyle                                 
  });                                         
}                                                      
```
Result
```css
.yourclass {                                    
  @media only screen and (min-width: 1050px) {  
    yourstyle                                 
  }
}
```

### .belowF

Is a function that you can send the value that you prefer to set in max-width    

Example
```less
.yourclass {                                    
  .belowF (600px, {                             
     yourstyle                                  
   });                                        
}                                               
```
Result   
```css
.yourclass {                                    
  @media only screen and (max-width: 600px) {
    yourstyle                                 
  }                                             
} 
```

### .mobile, .tablet, .desktop, .hd

We've prepared some media query ranges that we think are right for you.
You can use one of the functions, only parameter is your style, so you can use our ranges.

Example
```less
.yourclass {
  .mobile ({
    yourstyle
  });
 }     
```
Result
```css
.yourclass {
  @media only screen and (min-width: 400px) {
    yourstyle  
  }                                             
}
```
Example
```less
.yourclass {
  .tablet ({
    yourstyle
  });
}
```
Result
```css
.yourclass {
  @media only screen and
    (min-width: 400px) and (max-width: 800px) {
       yourstyle                                   
     }                                             
  }  
```
Example
```less
.yourclass {
  .desktop ({                                   
    yourstyle                                  
  });                                         
}   
```
Result
```css
.yourclass {                                    
  @media only screen and                        
   (min-width: 800px) and (max-width: 1050px) {   
      yourstyle                                   
    }                                             
}
```
## Utils

We have here some functions that can help you to coding faster

### .size

You can set properties like width and height in an easy way with .size, just pass the values, we will put them for you.              
You must follow the order of the parameters, first the width after the height   

Example
```less
.yourclass {                                    
  .size(200px, 150px);                         
}        
```
Result
```css
.yourclass {                                    
  width: 200px;                                 
  height: 150px;                                
}
```

### .fontsize2em

Convert px into 'em' easily, just pass the number to function as it returns the font size property with last number converted to 'em' the context is set to a default value for the body, but you can modify it the way you prefer.

Example
```less
.yourclass {                                    
  .fontsize2em (42);                            
}  
```
Result
```css
.yourclass {
  font-size: 2.625em;                         
} 
```

## License

Copyright 2018 Fluany

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.