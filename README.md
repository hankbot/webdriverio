This fork applies minimal changes to the base [WebdriverIO](https://webdriver.io/) project in order to support using the framework with [Windows Application Driver](https://github.com/microsoft/winappdriver).

As of WebdriverIO v5.7.14 and WinAppDriver v1.1 there are 2 main issues that prevent stock WebdriverIO from being usable:
 1. [WinAppDriver does not return a NULL value](https://github.com/Microsoft/WinAppDriver/issues/654) after successfully clicking an element - this is incompatable with the spec and [WebdriverIO explicitly requires the null value](https://github.com/webdriverio/webdriverio/pull/3809)
 1. When an outputDir is configured in the wdio config WebdriverIO will make a call to the /session/:sessionId/log/types API - this causes WinAppDiver to fail test cases [since the log API is not implemented](https://github.com/Microsoft/WinAppDriver#supported-apis)
