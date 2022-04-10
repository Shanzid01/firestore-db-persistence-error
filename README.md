### This project aims to demonstrate an issue in firestore persistence when running inside a Vue3+Typescript web app
### [See live demo](https://firestore-db-persistence-error.pages.dev/)

You'll find **all** the relevant code for this bug inside [`src/App.vue`](https://github.com/Shanzid01/firestore-db-persistence-error/blob/main/src/App.vue) file.

**Install** the app and **serve** the code (instructions below), you should see the error come up immediately in the browser logs when you visit the page (usually deployed to http://localhost:8080).

```
npm install
```

```
npm run serve
```

Browser logs when running on my computer (details of my setup can be found in the [original issue report](https://github.com/firebase/firebase-js-sdk/issues/6087)):

``
[2022-04-10T19:22:12.934Z]  @firebase/firestore: Firestore (9.6.10): INTERNAL UNHANDLED ERROR:  Error: Failed to execute 'put' on 'IDBObjectStore': #<Object> could not be cloned.
    at Ti.put (webpack-internal:///./node_modules/@firebase/firestore/dist/index.esm2017.js:5850:24)
    at Proxy.addEntry (webpack-internal:///./node_modules/@firebase/firestore/dist/index.esm2017.js:8783:22)
    at eval (webpack-internal:///./node_modules/@firebase/firestore/dist/index.esm2017.js:8969:49)
    at eval (webpack-internal:///./node_modules/@firebase/firestore/dist/index.esm2017.js:3626:37)
    at lt (webpack-internal:///./node_modules/@firebase/firestore/dist/index.esm2017.js:1050:70)
    at kn.forEach (webpack-internal:///./node_modules/@firebase/firestore/dist/index.esm2017.js:3625:9)
    at Or.applyChanges (webpack-internal:///./node_modules/@firebase/firestore/dist/index.esm2017.js:8963:29)
    at Or.apply (webpack-internal:///./node_modules/@firebase/firestore/dist/index.esm2017.js:8746:72)
    at eval (webpack-internal:///./node_modules/@firebase/firestore/dist/index.esm2017.js:10284:44)
    at eval (webpack-internal:///./node_modules/@firebase/firestore/dist/index.esm2017.js:5532:49)
defaultLogHandler @ index.esm2017.js?e691:78
error @ index.esm2017.js?e691:161
F @ index.esm2017.js?0829:120
eval @ index.esm2017.js?0829:16371
Promise.catch (async)
eval @ index.esm2017.js?0829:16339
Promise.then (async)
Ga @ index.esm2017.js?0829:16339
enqueue @ index.esm2017.js?0829:16306
enqueueAndForget @ index.esm2017.js?0829:16284
eval @ index.esm2017.js?0829:12493
eval @ index.esm2017.js?0829:12470
no @ index.esm2017.js?0829:11880
eval @ index.esm2017.js?0829:12104
eval @ index.esm2017.js?0829:12055
qb @ index.esm2017.js?8f6b:27
D @ index.esm2017.js?8f6b:25
Z.wa @ index.esm2017.js?8f6b:86
sc @ index.esm2017.js?8f6b:43
tc @ index.esm2017.js?8f6b:38
k.Ia @ index.esm2017.js?8f6b:36
k.gb @ index.esm2017.js?8f6b:34
qb @ index.esm2017.js?8f6b:27
D @ index.esm2017.js?8f6b:25
Ed @ index.esm2017.js?8f6b:65
k.cb @ index.esm2017.js?8f6b:64
k.Fa @ index.esm2017.js?8f6b:64
sd @ index.esm2017.js?8f6b:60
k.Sa @ index.esm2017.js?8f6b:58
Promise.then (async)
ud @ index.esm2017.js?8f6b:58
k.Va @ index.esm2017.js?8f6b:58
Promise.then (async)
k.send @ index.esm2017.js?8f6b:55
k.ea @ index.esm2017.js?8f6b:62
kc @ index.esm2017.js?8f6b:33
Rd @ index.esm2017.js?8f6b:78
k.Ga @ index.esm2017.js?8f6b:77
Db @ index.esm2017.js?8f6b:28
Promise.then (async)
Ab @ index.esm2017.js?8f6b:28
zb @ index.esm2017.js?8f6b:28
Gc @ index.esm2017.js?8f6b:76
sc @ index.esm2017.js?8f6b:43
tc @ index.esm2017.js?8f6b:38
k.Ia @ index.esm2017.js?8f6b:36
k.gb @ index.esm2017.js?8f6b:34
qb @ index.esm2017.js?8f6b:27
D @ index.esm2017.js?8f6b:25
Ed @ index.esm2017.js?8f6b:65
k.cb @ index.esm2017.js?8f6b:64
k.Fa @ index.esm2017.js?8f6b:64
sd @ index.esm2017.js?8f6b:60
k.Sa @ index.esm2017.js?8f6b:58
Promise.then (async)
ud @ index.esm2017.js?8f6b:58
k.Va @ index.esm2017.js?8f6b:58
Promise.then (async)
k.send @ index.esm2017.js?8f6b:55
k.ea @ index.esm2017.js?8f6b:62
kc @ index.esm2017.js?8f6b:33
ic @ index.esm2017.js?8f6b:33
k.Ha @ index.esm2017.js?8f6b:74
Db @ index.esm2017.js?8f6b:28
Promise.then (async)
Ab @ index.esm2017.js?8f6b:28
zb @ index.esm2017.js?8f6b:28
Y.m @ index.esm2017.js?8f6b:84
jr @ index.esm2017.js?0829:12047
send @ index.esm2017.js?0829:11871
Oo @ index.esm2017.js?0829:12385
Qo @ index.esm2017.js?0829:12547
eu @ index.esm2017.js?0829:12880
eval @ index.esm2017.js?0829:12915
eval @ reactivity.esm-bundler.js?a1e9:664
forEach @ reactivity.esm-bundler.js?a1e9:660
uu @ index.esm2017.js?0829:12914
eval @ index.esm2017.js?0829:12466
eval @ index.esm2017.js?0829:12493
eval @ index.esm2017.js?0829:16306
eval @ index.esm2017.js?0829:16339
Promise.then (async)
Ga @ index.esm2017.js?0829:16339
enqueue @ index.esm2017.js?0829:16306
enqueueAndForget @ index.esm2017.js?0829:16284
eval @ index.esm2017.js?0829:12493
eval @ index.esm2017.js?0829:12465
Zr @ index.esm2017.js?0829:11874
eval @ index.esm2017.js?0829:12113
setTimeout (async)
ho @ index.esm2017.js?0829:12108
Go @ index.esm2017.js?0829:12511
Uo @ index.esm2017.js?0829:12464
eval @ index.esm2017.js?0829:12454
Promise.then (async)
auth @ index.esm2017.js?0829:12445
start @ index.esm2017.js?0829:12350
su @ index.esm2017.js?0829:12895
Zo @ index.esm2017.js?0829:12861
zu @ index.esm2017.js?0829:14170
await in zu (async)
xu @ index.esm2017.js?0829:13516
eval @ index.esm2017.js?0829:18740
await in eval (async)
eval @ index.esm2017.js?0829:16306
eval @ index.esm2017.js?0829:16339
Promise.then (async)
Ga @ index.esm2017.js?0829:16339
enqueue @ index.esm2017.js?0829:16306
enqueueAndForget @ index.esm2017.js?0829:16284
eval @ index.esm2017.js?0829:18740
al @ index.esm2017.js?0829:18743
getData @ App.vue?47b3:35
eval @ App.vue?47b3:54
Promise.then (async)
mounted @ App.vue?47b3:54
callWithErrorHandling @ runtime-core.esm-bundler.js?5c40:155
callWithAsyncErrorHandling @ runtime-core.esm-bundler.js?5c40:164
hook.__weh.hook.__weh @ runtime-core.esm-bundler.js?5c40:2667
flushPostFlushCbs @ runtime-core.esm-bundler.js?5c40:356
render @ runtime-core.esm-bundler.js?5c40:5643
mount @ runtime-core.esm-bundler.js?5c40:3877
app.mount @ runtime-dom.esm-bundler.js?830f:1590
eval @ main.ts?e4f2:4
./src/main.ts @ app.js:1009
__webpack_require__ @ app.js:849
fn @ app.js:151
1 @ app.js:1022
__webpack_require__ @ app.js:849
checkDeferredModules @ app.js:46
(anonymous) @ app.js:925
(anonymous) @ app.js:928
index.esm2017.js?0829:5763 Uncaught (in promise) DOMException: Failed to execute 'put' on 'IDBObjectStore': #<Object> could not be cloned.
    at Ti.put (webpack-internal:///./node_modules/@firebase/firestore/dist/index.esm2017.js:5850:24)
    at Proxy.addEntry (webpack-internal:///./node_modules/@firebase/firestore/dist/index.esm2017.js:8783:22)
    at eval (webpack-internal:///./node_modules/@firebase/firestore/dist/index.esm2017.js:8969:49)
    at eval (webpack-internal:///./node_modules/@firebase/firestore/dist/index.esm2017.js:3626:37)
    at lt (webpack-internal:///./node_modules/@firebase/firestore/dist/index.esm2017.js:1050:70)
    at kn.forEach (webpack-internal:///./node_modules/@firebase/firestore/dist/index.esm2017.js:3625:9)
    at Or.applyChanges (webpack-internal:///./node_modules/@firebase/firestore/dist/index.esm2017.js:8963:29)
    at Or.apply (webpack-internal:///./node_modules/@firebase/firestore/dist/index.esm2017.js:8746:72)
    at eval (webpack-internal:///./node_modules/@firebase/firestore/dist/index.esm2017.js:10284:44)
    at eval (webpack-internal:///./node_modules/@firebase/firestore/dist/index.esm2017.js:5532:49)
put @ index.esm2017.js?0829:5763
addEntry @ index.esm2017.js?0829:8696
eval @ index.esm2017.js?0829:8882
eval @ index.esm2017.js?0829:3539
lt @ index.esm2017.js?0829:963
forEach @ index.esm2017.js?0829:3538
applyChanges @ index.esm2017.js?0829:8876
apply @ index.esm2017.js?0829:8659
eval @ index.esm2017.js?0829:10197
eval @ index.esm2017.js?0829:5445
wrapUserFunction @ index.esm2017.js?0829:5438
wrapSuccess @ index.esm2017.js?0829:5445
nextCallback @ index.esm2017.js?0829:5425
t.isDone @ index.esm2017.js?0829:5414
eval @ index.esm2017.js?0829:5468
eval @ index.esm2017.js?0829:5445
wrapUserFunction @ index.esm2017.js?0829:5438
wrapSuccess @ index.esm2017.js?0829:5445
nextCallback @ index.esm2017.js?0829:5425
t.isDone @ index.esm2017.js?0829:5414
eval @ index.esm2017.js?0829:5445
wrapUserFunction @ index.esm2017.js?0829:5438
wrapSuccess @ index.esm2017.js?0829:5445
nextCallback @ index.esm2017.js?0829:5425
t.isDone @ index.esm2017.js?0829:5414
eval @ index.esm2017.js?0829:5445
wrapUserFunction @ index.esm2017.js?0829:5438
wrapSuccess @ index.esm2017.js?0829:5445
nextCallback @ index.esm2017.js?0829:5425
t.isDone @ index.esm2017.js?0829:5414
t.onsuccess @ index.esm2017.js?0829:5910
Promise.then (async)
enqueue @ index.esm2017.js?0829:16307
enqueueAndForget @ index.esm2017.js?0829:16284
eval @ index.esm2017.js?0829:12493
eval @ index.esm2017.js?0829:12470
no @ index.esm2017.js?0829:11880
eval @ index.esm2017.js?0829:12104
eval @ index.esm2017.js?0829:12055
qb @ index.esm2017.js?8f6b:27
D @ index.esm2017.js?8f6b:25
Z.wa @ index.esm2017.js?8f6b:86
sc @ index.esm2017.js?8f6b:43
tc @ index.esm2017.js?8f6b:38
k.Ia @ index.esm2017.js?8f6b:36
k.gb @ index.esm2017.js?8f6b:34
qb @ index.esm2017.js?8f6b:27
D @ index.esm2017.js?8f6b:25
Ed @ index.esm2017.js?8f6b:65
k.cb @ index.esm2017.js?8f6b:64
k.Fa @ index.esm2017.js?8f6b:64
sd @ index.esm2017.js?8f6b:60
k.Sa @ index.esm2017.js?8f6b:58
Promise.then (async)
ud @ index.esm2017.js?8f6b:58
k.Va @ index.esm2017.js?8f6b:58
Promise.then (async)
k.send @ index.esm2017.js?8f6b:55
k.ea @ index.esm2017.js?8f6b:62
kc @ index.esm2017.js?8f6b:33
Rd @ index.esm2017.js?8f6b:78
k.Ga @ index.esm2017.js?8f6b:77
Db @ index.esm2017.js?8f6b:28
Promise.then (async)
Ab @ index.esm2017.js?8f6b:28
zb @ index.esm2017.js?8f6b:28
Gc @ index.esm2017.js?8f6b:76
sc @ index.esm2017.js?8f6b:43
tc @ index.esm2017.js?8f6b:38
k.Ia @ index.esm2017.js?8f6b:36
k.gb @ index.esm2017.js?8f6b:34
qb @ index.esm2017.js?8f6b:27
D @ index.esm2017.js?8f6b:25
Ed @ index.esm2017.js?8f6b:65
k.cb @ index.esm2017.js?8f6b:64
k.Fa @ index.esm2017.js?8f6b:64
sd @ index.esm2017.js?8f6b:60
k.Sa @ index.esm2017.js?8f6b:58
Promise.then (async)
ud @ index.esm2017.js?8f6b:58
k.Va @ index.esm2017.js?8f6b:58
Promise.then (async)
k.send @ index.esm2017.js?8f6b:55
k.ea @ index.esm2017.js?8f6b:62
kc @ index.esm2017.js?8f6b:33
ic @ index.esm2017.js?8f6b:33
k.Ha @ index.esm2017.js?8f6b:74
Db @ index.esm2017.js?8f6b:28
Promise.then (async)
Ab @ index.esm2017.js?8f6b:28
zb @ index.esm2017.js?8f6b:28
Y.m @ index.esm2017.js?8f6b:84
jr @ index.esm2017.js?0829:12047
send @ index.esm2017.js?0829:11871
Oo @ index.esm2017.js?0829:12385
Qo @ index.esm2017.js?0829:12547
eu @ index.esm2017.js?0829:12880
eval @ index.esm2017.js?0829:12915
eval @ reactivity.esm-bundler.js?a1e9:664
forEach @ reactivity.esm-bundler.js?a1e9:660
uu @ index.esm2017.js?0829:12914
eval @ index.esm2017.js?0829:12466
eval @ index.esm2017.js?0829:12493
eval @ index.esm2017.js?0829:16306
eval @ index.esm2017.js?0829:16339
Promise.then (async)
Ga @ index.esm2017.js?0829:16339
enqueue @ index.esm2017.js?0829:16306
enqueueAndForget @ index.esm2017.js?0829:16284
eval @ index.esm2017.js?0829:12493
eval @ index.esm2017.js?0829:12465
Zr @ index.esm2017.js?0829:11874
eval @ index.esm2017.js?0829:12113
setTimeout (async)
ho @ index.esm2017.js?0829:12108
Go @ index.esm2017.js?0829:12511
Uo @ index.esm2017.js?0829:12464
eval @ index.esm2017.js?0829:12454
Promise.then (async)
auth @ index.esm2017.js?0829:12445
start @ index.esm2017.js?0829:12350
su @ index.esm2017.js?0829:12895
Zo @ index.esm2017.js?0829:12861
zu @ index.esm2017.js?0829:14170
await in zu (async)
xu @ index.esm2017.js?0829:13516
eval @ index.esm2017.js?0829:18740
await in eval (async)
eval @ index.esm2017.js?0829:16306
eval @ index.esm2017.js?0829:16339
Promise.then (async)
Ga @ index.esm2017.js?0829:16339
enqueue @ index.esm2017.js?0829:16306
enqueueAndForget @ index.esm2017.js?0829:16284
eval @ index.esm2017.js?0829:18740
al @ index.esm2017.js?0829:18743
getData @ App.vue?47b3:35
eval @ App.vue?47b3:54
Promise.then (async)
mounted @ App.vue?47b3:54
callWithErrorHandling @ runtime-core.esm-bundler.js?5c40:155
callWithAsyncErrorHandling @ runtime-core.esm-bundler.js?5c40:164
hook.__weh.hook.__weh @ runtime-core.esm-bundler.js?5c40:2667
flushPostFlushCbs @ runtime-core.esm-bundler.js?5c40:356
render @ runtime-core.esm-bundler.js?5c40:5643
mount @ runtime-core.esm-bundler.js?5c40:3877
app.mount @ runtime-dom.esm-bundler.js?830f:1590
eval @ main.ts?e4f2:4
./src/main.ts @ app.js:1009
__webpack_require__ @ app.js:849
fn @ app.js:151
1 @ app.js:1022
__webpack_require__ @ app.js:849
checkDeferredModules @ app.js:46
(anonymous) @ app.js:925
(anonymous) @ app.js:928
index.esm2017.js?e691:78 [2022-04-10T19:22:16.217Z]  @firebase/firestore: Firestore (9.6.10): FIRESTORE (9.6.10) INTERNAL ASSERTION FAILED: Unexpected state
defaultLogHandler @ index.esm2017.js?e691:78
error @ index.esm2017.js?e691:161
F @ index.esm2017.js?0829:120
L @ index.esm2017.js?0829:193
qa @ index.esm2017.js?0829:16383
enqueue @ index.esm2017.js?0829:16299
enqueueAndForget @ index.esm2017.js?0829:16284
handleDelayElapsed @ index.esm2017.js?0829:13281
eval @ index.esm2017.js?0829:13263
setTimeout (async)
start @ index.esm2017.js?0829:13263
createAndSchedule @ index.esm2017.js?0829:13257
enqueueAfterDelay @ index.esm2017.js?0829:16379
ps @ index.esm2017.js?0829:9452
eval @ index.esm2017.js?0829:9350
Promise.then (async)
start @ index.esm2017.js?0829:9345
initialize @ index.esm2017.js?0829:14861
initialize @ index.esm2017.js?0829:14888
Oa @ index.esm2017.js?0829:15522
await in Oa (async)
eval @ index.esm2017.js?0829:16689
eval @ index.esm2017.js?0829:16306
eval @ index.esm2017.js?0829:16339
Promise.then (async)
Ga @ index.esm2017.js?0829:16339
enqueue @ index.esm2017.js?0829:16306
Cc @ index.esm2017.js?0829:16687
Sc @ index.esm2017.js?0829:16650
initFirestore @ App.vue?47b3:27
mounted @ App.vue?47b3:54
callWithErrorHandling @ runtime-core.esm-bundler.js?5c40:155
callWithAsyncErrorHandling @ runtime-core.esm-bundler.js?5c40:164
hook.__weh.hook.__weh @ runtime-core.esm-bundler.js?5c40:2667
flushPostFlushCbs @ runtime-core.esm-bundler.js?5c40:356
render @ runtime-core.esm-bundler.js?5c40:5643
mount @ runtime-core.esm-bundler.js?5c40:3877
app.mount @ runtime-dom.esm-bundler.js?830f:1590
eval @ main.ts?e4f2:4
./src/main.ts @ app.js:1009
__webpack_require__ @ app.js:849
fn @ app.js:151
1 @ app.js:1022
__webpack_require__ @ app.js:849
checkDeferredModules @ app.js:46
(anonymous) @ app.js:925
(anonymous) @ app.js:928
index.esm2017.js?0829:193 Uncaught Error: FIRESTORE (9.6.10) INTERNAL ASSERTION FAILED: Unexpected state
    at L (index.esm2017.js?0829:193:1)
    at Proxy.qa (index.esm2017.js?0829:16383:1)
    at Proxy.enqueue (index.esm2017.js?0829:16299:1)
    at Proxy.enqueueAndForget (index.esm2017.js?0829:16284:1)
    at bu.handleDelayElapsed (index.esm2017.js?0829:13281:1)
    at eval (index.esm2017.js?0829:13263:1)
``
