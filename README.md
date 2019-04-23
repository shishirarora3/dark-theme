Chrome Extension for Dark Theme
====================================


## Installations

1) go to chrome://extensions/
2) Switch to Developer mode form top-right corner
3) click "Load unpacked" button and upload extension folder "regression-tool". After this, an icon will appear on browser's top extension bar.

## Working(Initial setup)

1. choose any flow flow to test.
1. write sequential actions in actions.js, defining the sequence of actions. eg,  sequential actions, might be:
<ol>
  <li> click any of the check boxes(#1, #2..) and then press button, giving a unique id to every constituent sub-action.
  <li> click any of the radio buttons(#1, #2..) which appear and then press some button
</ol>
Now tool will take care of all possible permutations of constituent sub-actions, in the sequential actions  





## Before code change:
##### Note: in local storage: iter variable tracks the test case no. and snapshots variable tracks snapshots for all test cases.
1) in actions.js, set takeSnapshots variable as true. Also, iter and snapshots as empty in localstorage.
2) refresh chrome extension and let test snapshots get captured.


After code change, to run regression:

1) in actions.js, set takeSnapshots variable as false. Also, iter as empty in localstorage.
2) refresh chrome extension and let the tool diff, new snapshots against old snapshots and log as error in console starting with "Snapshot Error:".

We can overlook deliberate changes and correct un-intentional changes.
