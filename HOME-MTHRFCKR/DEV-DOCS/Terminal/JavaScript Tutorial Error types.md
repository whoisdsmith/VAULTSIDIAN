# JavaScript Tutorial => Error types

There are six specific core error constructors in JavaScript:

  * **`EvalError`** \- creates an instance representing an error that occurs regarding the global function `eval()`.

  * **`InternalError`** \- creates an instance representing an error that occurs when an internal error in the JavaScript engine is thrown. E.g. "too much recursion". (Supported only by **Mozilla Firefox**)

  * **`RangeError`** \- creates an instance representing an error that occurs when a numeric variable or parameter is outside of its valid range.

  * **`ReferenceError`** \- creates an instance representing an error that occurs when dereferencing an invalid reference.

  * **`SyntaxError`** \- creates an instance representing a syntax error that occurs while parsing code in `eval()`.

  * **`TypeError`** \- creates an instance representing an error that occurs when a variable or parameter is not of a valid type.

  * **`URIError`** \- creates an instance representing an error that occurs when `encodeURI()` or `decodeURI()` are passed invalid parameters.

If you are implementing error handling mechanism you can check which kind of error you are catching from code.
    
    
    try {
        throw new TypeError();
    }
    catch (e){
        if(e instanceof Error){
            console.log('instance of general Error constructor');
        }
    
        if(e instanceof TypeError) {
            console.log('type error');
        }
    }
    
    
    
    
    
    In such case e will be an instance of TypeError. All error types extend the base constructor Error, therefore it's also an instance of Error.
    
    
    
    
    Keeping that in mind shows us that checking e to be an instance of Error is useless in most cases.
    
                                
                                
                                __[ Previous](/javascript/example/1333/error-objects)
                                [ Next __ ](/javascript/example/1332/interaction-with-promises)



___

#article #errors