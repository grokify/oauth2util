# OAuth 2.0 Plus for Go

[![Build Status][build-status-svg]][build-status-link]
[![Go Report Card][goreport-svg]][goreport-link]
[![Docs][docs-godoc-svg]][docs-godoc-link]
[![License][license-svg]][license-link]


[OAuth 2.0 - https://github.com/golang/oauth2](https://github.com/golang/oauth2) helper API calls related to OAuth 2.0 user profile information. Currently provides:

* `NewClient()` functions to create `*http.Client` structs for services like `aha`, `metabase`, `ringcentral`, `salesforce`, etc.
* Helper libraries to retrieve canonical user information from services. The [SCIM](http://www.simplecloud.info/) user schema is used for a canonical user model.
* Multi-service libraries to more transparently handle OAuth 2 for multiple services, e.g. a website that supports Google and Facebook auth. This is demoed in [grokify/beego-oauth2-demo](https://github.com/grokify/beego-oauth2-demo)

## Installation

```
$ go get github.com/grokify/oauth2util/...
```

## Usage

### Google

```golang
import(
	"github.com/grokify/oauth2util/google"
)

// googleOAuth2HTTPClient is *http.Client from Golang OAuth2
googleClientUtil := google.NewClientUtil(googleOAuth2HTTPClient)
scimuser, err := googleClientUtil.GetSCIMUser()
```

### Facebook

```golang
import(
	"github.com/grokify/oauth2util/facebook"
)

// fbOAuth2HTTPClient is *http.Client from Golang OAuth2
fbClientUtil := facebook.NewClientUtil(fbOAuth2HTTPClient)
scimuser, err := fbClientUtil.GetSCIMUser()
```

### RingCentral

```golang
import(
	"github.com/grokify/oauth2util/ringcentral"
)

// rcOAuth2HTTPClient is *http.Client from Golang OAuth2
rcClientUtil := ringcentral.NewClientUtil(rcOAuth2HTTPClient)
scimuser, err := rcClientUtil.GetSCIMUser()
```

### Example App

See the following repo for a Beego-based demo app:

* https://github.com/grokify/beego-oauth2-demo

 [build-status-svg]: https://api.travis-ci.org/grokify/oauth2util.svg?branch=master
 [build-status-link]: https://travis-ci.org/grokify/oauth2util
 [goreport-svg]: https://goreportcard.com/badge/github.com/grokify/oauth2util
 [goreport-link]: https://goreportcard.com/report/github.com/grokify/oauth2util
 [docs-godoc-svg]: https://img.shields.io/badge/docs-godoc-blue.svg
 [docs-godoc-link]: https://godoc.org/github.com/grokify/oauth2util
 [license-svg]: https://img.shields.io/badge/license-MIT-blue.svg
 [license-link]: https://github.com/grokify/oauth2util/blob/master/LICENSE.md
