# B-Speed
A speedtest framework based on Clash Core.

# B-Speed Design

B-Speed is a independent speedtest core.

It only calls the Clash API and acts like a common browser proxying the traffic via Clash core, which will be not involved with any Clash codes.

In principle, B-Speed **MAY NOT** be open-sourced according to GPL-3.0 License. 

However, we still insist on delivering its source code for our spirit of open source.

**We reserve our rights about decisions of opening source.**

Here is the B-Speed Core desgin.

```
                            |-------|    Call the Clash API   |---------|   RPC API   |-----------------|
      Stream   <----------- | Clash |  <--------------------  | B-Speed | <---------> | Webview Result/ |
      Unlock /              | Core  |  ---------------------> |  Core   |             | Web console     |
      Speedtest             |-------|     HTTP Proxy Callback |---------|             |-----------------|
```

## B-Speed Stream Unlock Test Desgin

B-Speed is new project, however, the current stream unlock testing scripts aren't new.

We don't want to write theses codes repeatedly, which is meaningless.

Also, we don't want to create a new "Environment" about B-Speed, which is also meaningless, because B-Speed is just a tool, not a system.

So, we aim to make our core **forward compatible** with those scripts.

B-Speed acts like Clash For Windows, it will set up the system proxy before stream lock tests.

The only task of B-Speed stream lock testing part is fetching the result of theses scripts, we are going to generate a "callback" script to help the B-Speed core to grab the result.

Therefore, the traffic of all the stream lock testing scripts will be proxyed via Clash core, and then via the proxy.
