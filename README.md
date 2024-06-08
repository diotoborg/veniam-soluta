# @diotoborg/veniam-soluta
---

[![Build Status](https://travis-ci.org/aligay/@diotoborg/veniam-soluta.svg?branch=master)](https://travis-ci.org/aligay/@diotoborg/veniam-soluta/branches)
[![codecov](https://codecov.io/gh/aligay/@diotoborg/veniam-soluta/branch/master/graph/badge.svg)](https://codecov.io/gh/aligay/@diotoborg/veniam-soluta)
[![dependencies Status](https://david-dm.org/aligay/@diotoborg/veniam-soluta/status.svg)](https://david-dm.org/aligay/@diotoborg/veniam-soluta)
[![devDependencies Status](https://david-dm.org/aligay/@diotoborg/veniam-soluta/dev-status.svg)](https://david-dm.org/aligay/@diotoborg/veniam-soluta?type=dev)

## install
```
npm install @diotoborg/veniam-soluta
```
## use
```
import safeTrim from '@diotoborg/veniam-soluta'
safeTrim('    a      b  ')
```

## remove Invisible spaces

```
let str = '  "a":1    a \r\n\r\t  ᠎             　b       '
let ret = safeTrim(str)
expect(ret).toEqual('"a":1    a\n\nb')
```

## convert CR CR-LR into LR
```
a\r\n\r\nb  => 'a\n\nb'
a\r\rb => 'a\n\nb'
a\r\r\nb => 'a\n\nb'
```

## remove BOM
```
JSON.parse('﻿{"a":1}') // ❗️Error because BOM

JSON.parse(safeTrim('﻿{"a":1}')) // ✅
```


## more feature
[more feature](spec/test_spec.js)
