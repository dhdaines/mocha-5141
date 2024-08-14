Reproduction of issue 5141 for Mocha
------------------------------------

To reproduce:

    # Either do this (*do not* run npm install!)
    npx mocha
    # Or this
    node /path/to/mocha/bin/mocha.js
    
Expected behaviour:

    Error: Unable to parse /home/dhd/work/flair/src/mocha-5141/package.json: SyntaxError: Expected double-quoted property name in JSON at position 570

Actual behaviour:

    Error: No test files found: "test"

Note that if you run mocha from `npm`, (i.e. via a "test" script in
package.json), then `npm` will catch the invalid JSON.  Running
`mocha` directly ought to do this too (since if your `package.json` is
invalid, you already have problems).
