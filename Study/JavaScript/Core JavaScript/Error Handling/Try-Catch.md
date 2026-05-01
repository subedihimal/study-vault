```js
function tester(test){

    try{
        if(!test){
         throw new Error("Empty value entry")
        }
    }catch(error){
        console.log(error);
        console.log(`Error was called ${error}`)
    }
}

const result = tester(false);
console.log(result)

//Output
/* 
	Error: Empty value entry
    at tester (/Users/himal/Projects/practice/test.js:5:16)
    at Object.<anonymous> (/Users/himal/Projects/practice/test.js:13:16)
    at Module._compile (node:internal/modules/cjs/loader:1761:14)
    at Object..js (node:internal/modules/cjs/loader:1893:10)
    at Module.load (node:internal/modules/cjs/loader:1481:32)
    at Module._load (node:internal/modules/cjs/loader:1300:12)
    at TracingChannel.traceSync (node:diagnostics_channel:328:14)
    at wrapModuleLoad (node:internal/modules/cjs/loader:245:24)
    at Module.executeUserEntryPoint [as runMain].                                   (node:internal/modules/run_main:154:5)
    at node:internal/main/run_main_module:33:47                                      Error was called Error: Empty value entry
undefined
*/


```

Properties of Error
- message
- name
- status
- stack