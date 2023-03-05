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
