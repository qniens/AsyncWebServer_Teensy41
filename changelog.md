# AsyncWebServer_Teensy41 Library

[![arduino-library-badge](https://www.ardu-badge.com/badge/AsyncWebServer_Teensy41.svg?)](https://www.ardu-badge.com/AsyncWebServer_Teensy41)
[![GitHub release](https://img.shields.io/github/release/khoih-prog/AsyncWebServer_Teensy41.svg)](https://github.com/khoih-prog/AsyncWebServer_Teensy41/releases)
[![GitHub](https://img.shields.io/github/license/mashape/apistatus.svg)](https://github.com/khoih-prog/AsyncWebServer_Teensy41/blob/master/LICENSE)
[![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](#Contributing)
[![GitHub issues](https://img.shields.io/github/issues/khoih-prog/AsyncWebServer_Teensy41.svg)](http://github.com/khoih-prog/AsyncWebServer_Teensy41/issues)

<a href="https://www.buymeacoffee.com/khoihprog6" title="Donate to my libraries using BuyMeACoffee"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Donate to my libraries using BuyMeACoffee" style="height: 50px !important;width: 181px !important;" ></a>
<a href="https://www.buymeacoffee.com/khoihprog6" title="Donate to my libraries using BuyMeACoffee"><img src="https://img.shields.io/badge/buy%20me%20a%20coffee-donate-orange.svg?logo=buy-me-a-coffee&logoColor=FFDD00" style="height: 20px !important;width: 200px !important;" ></a>


---
---

## Table of contents

* [Table of contents](#table-of-contents)
* [Changelog](#changelog)
  * [Releases v1.8.0](#releases-v180)
  * [Releases v1.7.0](#releases-v170)
  * [Releases v1.6.2](#releases-v162)
  * [Releases v1.6.1](#releases-v161)
  * [Releases v1.6.0](#releases-v160)
  * [Releases v1.5.0](#releases-v150)
  * [Releases v1.4.1](#releases-v141)

---
---

## Changelog

### Releases v1.8.0

1. **Security**: CRLF injection protection in HTTP headers (upstream fix GHSA-87j8-6f7g-h8wh from v3.7.9)
2. **Bug fix**: Header parsing robustness - reject malformed headers, handle optional whitespace after colon (from v3.7.10)
3. **Bug fix**: Initialize `_onDisconnectfn` to nullptr to prevent use of uninitialized callback (from v3.7.10)
4. **Bug fix**: Add HTTP 429 Too Many Requests status code (from v3.8.0)
5. **Bug fix**: Use `%zu` format specifier for `size_t` Content-Length to avoid truncation
6. **Bug fix**: Handle `text/plain` POST with charset parameter using `startsWith` (from v3.8.1)
7. **Bug fix**: Handle Safari fragmented WebSocket mask data across TCP packets (from v3.9.3 PR #353)
8. **Bug fix**: Fix JSON deserialization buffer bounds - allocate null terminator byte (from v3.7.8 PR #184)
9. **Bug fix**: Fix `_removeNotInterestingHeaders` modifying list during iteration
10. **Bug fix**: Discard bytes received after Content-Length to prevent handler buffer overruns (from v3.7.2 PR #101)

### Releases v1.7.0

1. Fix file upload to Teensy 4.1 board based on suggestions made on the PJRC forum. Align signatures of file upload handlers.
For more details, please see this post: [AsyncWebServer_Teensy41 bug onUpload](https://forum.pjrc.com/index.php?threads/asyncwebserver_teensy41-bug-onupload.72220).

### Releases v1.6.2

1. Add examples [Async_WebSocketsServer](https://github.com/khoih-prog/AsyncWebServer_Teensy41/tree/main/examples/Async_WebSocketsServer) to demo how to use `Async_WebSockets`

### Releases v1.6.1

1. Add examples [Async_AdvancedWebServer_SendChunked](https://github.com/khoih-prog/AsyncWebServer_Teensy41/tree/main/examples/Async_AdvancedWebServer_SendChunked) and [AsyncWebServer_SendChunked](https://github.com/khoih-prog/AsyncWebServer_Teensy41/tree/main/examples/AsyncWebServer_SendChunked) to demo how to use `beginChunkedResponse()` to send large `html` in chunks
2. Use `allman astyle` and add `utils`


### Releases v1.6.0

1. Support using `CString` to save heap to send `very large data`. Check [request->send(200, textPlainStr, jsonChartDataCharStr); - Without using String Class - to save heap #8](https://github.com/khoih-prog/Portenta_H7_AsyncWebServer/pull/8) and [All memmove() removed - string no longer destroyed #11](https://github.com/khoih-prog/Portenta_H7_AsyncWebServer/pull/11)
2. Add multiple examples to demo the new feature

### Releases v1.5.0

1. Fix issue with slow browsers or network. Check [Target stops responding after variable time when using Firefox on Windows 10 #3](https://github.com/khoih-prog/AsyncWebServer_RP2040W/issues/3)
2. Add functions and example `Async_AdvancedWebServer_favicon` to support `favicon.ico`

### Releases v1.4.1

1. Initial porting and coding for **Teensy 4.1 using built-in QNEthernet**
2. Bump up version to v1.4.1 to sync with [AsyncWebServer_STM32](https://github.com/khoih-prog/AsyncWebServer_STM32) v1.4.1



