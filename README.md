# dd-trace-url

To reproduce the bug:

1. Clone this repo
2. Run `yarn install` in the `dd-url` directory
3. Run `yarn dev`

In the terminal you'll see the following error:

```
 ⨯ uncaughtException: TypeError: Cannot read properties of undefined (reading 'url')
    at NextPlugin.pageLoad (/Users/tamara/code/dd-trace-url/dd-url/node_modules/dd-trace/packages/datadog-plugin-next/src/index.js:89:27)
    at /Users/tamara/code/dd-trace-url/dd-url/node_modules/dd-trace/packages/datadog-plugin-next/src/index.js:17:55
    at Subscription._handler (/Users/tamara/code/dd-trace-url/dd-url/node_modules/dd-trace/packages/dd-trace/src/plugins/plugin.js:14:9)
    at Channel.publish (node:diagnostics_channel:56:9)
    at /Users/tamara/code/dd-trace-url/dd-url/node_modules/dd-trace/packages/datadog-instrumentations/src/next.js:142:67
    at instrument (/Users/tamara/code/dd-trace-url/dd-url/node_modules/dd-trace/packages/datadog-instrumentations/src/next.js:115:33)
    at serveStatic (/Users/tamara/code/dd-trace-url/dd-url/node_modules/dd-trace/packages/datadog-instrumentations/src/next.js:141:12)
    at handleRequest (/Users/tamara/code/dd-trace-url/dd-url/node_modules/next/dist/server/lib/router-server.js:318:63)
    at async requestHandlerImpl (/Users/tamara/code/dd-trace-url/dd-url/node_modules/next/dist/server/lib/router-server.js:394:13)
    at async Server.requestListener (/Users/tamara/code/dd-trace-url/dd-url/node_modules/next/dist/server/lib/start-server.js:151:13)
```

It looks to occur when using middleware
