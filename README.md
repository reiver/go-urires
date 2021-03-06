# go-urires

Package **urires** — `/uri-res/` — provides **a trivial convention for using HTTP in URN resolution** (as per RFC-2169),
which is useful for creating a **content-addressable web**,
which nowadays would be considered useful, and even necessary for a **distributed web**, or **decentralized web**.

## Documention

Online documentation, which includes examples, can be found at: http://godoc.org/github.com/reiver/go-urires

[![GoDoc](https://godoc.org/github.com/reiver/go-urires?status.svg)](https://godoc.org/github.com/reiver/go-urires)

## URLs, URNs, URCs

The basic idea is that we have **URL**s, **URN**s, and **URC**s.

URLs express **locations**, such as:
* `http://www.example.com/apple/banana/cherry.html`
* `ftp://files.example.net/path/to/file.txt`

URNs express **names**, such as:
* `hash://sha256/c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `ni:///sha-256;SGVsbG8gd29ybGQh`
* `urn:hash::sha256:YBJV4S7CW6P73EZJCMCUG27YREYU4SR7V3AF5T74XN67GGWZ4UNA====`
* `urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `magnet:?xt=urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`

URCs express **characteristics** — meta-data — about a URL, or URN.

## Resolution Services

There are then 10 **resolution services**:
**N2L**,
**N2Ls**,
**N2R**,
**N2Rs**,
**N2C**,
**N2Cs**,
**N2Ns**,
**L2Ns**,
**L2Ls**, and
**L2C**.

These **resolution services** are exposed through URLs such as the following:
* `/uri-res/N2L?<query>`
* `/uri-res/N2Ls?<query>`
* `/uri-res/N2R?<query>`
* `/uri-res/N2Rs?<query>`
* `/uri-res/N2C?<query>`
* `/uri-res/N2Cs?<query>`
* `/uri-res/N2Ns?<query>`
* `/uri-res/L2Ns?<query>`
* `/uri-res/L2Ls?<query>`
* `/uri-res/L2C?<query>`

Which, of course in practice, would be on some HTTP or HTTPS based URL, such as:
* `http://www.example.com/uri-res/N2L?<query>`
* `http://www.example.com/uri-res/N2Ls?<query>`
* `http://www.example.com/uri-res/N2R?<query>`
* `http://www.example.com/uri-res/N2Rs?<query>`
* `http://www.example.com/uri-res/N2C?<query>`
* `http://www.example.com/uri-res/N2Cs?<query>`
* `http://www.example.com/uri-res/N2Ns?<query>`
* `http://www.example.com/uri-res/L2Ns?<query>`
* `http://www.example.com/uri-res/L2Ls?<query>`
* `http://www.example.com/uri-res/L2C?<query>`

Or:
* `http://something.test/uri-res/N2L?<query>`
* `http://something.test/uri-res/N2Ls?<query>`
* `http://something.test/uri-res/N2R?<query>`
* `http://something.test/uri-res/N2Rs?<query>`
* `http://something.test/uri-res/N2C?<query>`
* `http://something.test/uri-res/N2Cs?<query>`
* `http://something.test/uri-res/N2Ns?<query>`
* `http://something.test/uri-res/L2Ns?<query>`
* `http://something.test/uri-res/L2Ls?<query>`
* `http://something.test/uri-res/L2C?<query>`

Etc.

## Resolution Services: Examples

Some more concrete examples — with example queries — is:
* `/uri-res/N2L?urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `/uri-res/N2Ls?urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `/uri-res/N2R?urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `/uri-res/N2Rs?urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `/uri-res/N2C?urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `/uri-res/N2Cs?urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `/uri-res/N2Ns?urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `/uri-res/L2Ns?http://www.example.com/apple/banana/cherry.html`
* `/uri-res/L2Ls?http://www.example.com/apple/banana/cherry.html`
* `/uri-res/L2C?http://www.example.com/apple/banana/cherry.html`

Which, of course in practice, would be on some HTTP or HTTPS based URL, such as:
* `http://www.example.com/uri-res/N2L?urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `http://www.example.com/uri-res/N2Ls?urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `http://www.example.com/uri-res/N2R?urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `http://www.example.com/uri-res/N2Rs?urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `http://www.example.com/uri-res/N2C?urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `http://www.example.com/uri-res/N2Cs?urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `http://www.example.com/uri-res/N2Ns?urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `http://www.example.com/uri-res/L2Ns?http://www.example.com/apple/banana/cherry.html`
* `http://www.example.com/uri-res/L2Ls?http://www.example.com/apple/banana/cherry.html`
* `http://www.example.com/uri-res/L2C?http://www.example.com/apple/banana/cherry.html`

Or:
* `http://something.test/uri-res/N2L?urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `http://something.test/uri-res/N2Ls?urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `http://something.test/uri-res/N2R?urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `http://something.test/uri-res/N2Rs?urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `http://something.test/uri-res/N2C?urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `http://something.test/uri-res/N2Cs?urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `http://something.test/uri-res/N2Ns?urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `http://something.test/uri-res/L2Ns?http://www.example.com/apple/banana/cherry.html`
* `http://something.test/uri-res/L2Ls?http://www.example.com/apple/banana/cherry.html`
* `http://something.test/uri-res/L2C?http://www.example.com/apple/banana/cherry.html`

Etc.

## Resolution Services: More Examples

All the examples provided so far just used `urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a` as the URN.

Other types of URNs could be used too.

For example:
* `/uri-res/N2L?hash://sha256/c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `/uri-res/N2Ls?hash://sha256/c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `/uri-res/N2R?hash://sha256/c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `/uri-res/N2Rs?hash://sha256/c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `/uri-res/N2C?hash://sha256/c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `/uri-res/N2Cs?hash://sha256/c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `/uri-res/N2Ns?hash://sha256/c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`

And:
* `/uri-res/N2L?ni:///sha-256;SGVsbG8gd29ybGQh`
* `/uri-res/N2Ls?ni:///sha-256;SGVsbG8gd29ybGQh`
* `/uri-res/N2R?ni:///sha-256;SGVsbG8gd29ybGQh`
* `/uri-res/N2Rs?ni:///sha-256;SGVsbG8gd29ybGQh`
* `/uri-res/N2C?ni:///sha-256;SGVsbG8gd29ybGQh`
* `/uri-res/N2Cs?ni:///sha-256;SGVsbG8gd29ybGQh`
* `/uri-res/N2Ns?ni:///sha-256;SGVsbG8gd29ybGQh`

And also:
* `/uri-res/N2L?urn:hash::sha256:YBJV4S7CW6P73EZJCMCUG27YREYU4SR7V3AF5T74XN67GGWZ4UNA====`
* `/uri-res/N2Ls?urn:hash::sha256:YBJV4S7CW6P73EZJCMCUG27YREYU4SR7V3AF5T74XN67GGWZ4UNA====`
* `/uri-res/N2R?urn:hash::sha256:YBJV4S7CW6P73EZJCMCUG27YREYU4SR7V3AF5T74XN67GGWZ4UNA====`
* `/uri-res/N2Rs?urn:hash::sha256:YBJV4S7CW6P73EZJCMCUG27YREYU4SR7V3AF5T74XN67GGWZ4UNA====`
* `/uri-res/N2C?urn:hash::sha256:YBJV4S7CW6P73EZJCMCUG27YREYU4SR7V3AF5T74XN67GGWZ4UNA====`
* `/uri-res/N2Cs?urn:hash::sha256:YBJV4S7CW6P73EZJCMCUG27YREYU4SR7V3AF5T74XN67GGWZ4UNA====`
* `/uri-res/N2Ns?urn:hash::sha256:YBJV4S7CW6P73EZJCMCUG27YREYU4SR7V3AF5T74XN67GGWZ4UNA====`

And even:
* `/uri-res/N2L?magnet:?xt=urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `/uri-res/N2Ls?magnet:?xt=urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `/uri-res/N2R?magnet:?xt=urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `/uri-res/N2Rs?magnet:?xt=urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `/uri-res/N2C?magnet:?xt=urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `/uri-res/N2Cs?magnet:?xt=urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`
* `/uri-res/N2Ns?magnet:?xt=urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a`

## N2L

“N2L” is an abbreviation for “Name To Location”.

The `/uri-res/N2L?<query>` resolver takes a **name**, typically expressed as a **URN** (in the `<query>`), and returns a **location**.

The **location** is returned using the HTTP response `Location` header, with a HTTP 3xx class HTTP status response code.

For example, the following HTTP response codes could be used:
* 301 Moved Permanently
* 302 Found
* 303 See Other
* 307 Temporary Redirect

An example HTTP request & response might be:

Example HTTP Request:
```
GET /uri-res/N2L?urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a HTTP/1.1
Host: www.example.com
```

Example HTTP Response:
```
HTTP/1.1 307 Temporary Redirect
Location: /path/to/file.txt
```

## N2Ls

“N2L” is an abbreviation for “Name To Locations”.

The `/uri-res/N2Ls?<query>` resolver takes a **name**, typically expressed as a **URN** (in the `<query>`), and returns **locations**.

The **locations** is a list of 0, 1, or more URLs, returned in the HTTP response.

For example, a list of URLs could be returned in the HTTP response body as `text/uri-list` data.

For example:

Example HTTP Request:
```
GET /uri-res/N2Ls?urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a HTTP/1.1
Host: www.example.com
```

Example HTTP Response:
```
HTTP/1.1 200 OK
Content-Type: text/uri-list

# urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a
http://www.example.com/path/to/file.txt
http://something.test/mirror/thefile.txt
```

Other formats could be used to return the **locations** (as alternatives to `text/uri-list`), especially if the HTTP client specifies alternative formats using the HTTP `Accept` header.

For example:

Example HTTP Request:
```
GET /uri-res/N2Ls?urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a HTTP/1.1
Host: www.example.com
Accept: text/html
```

Example HTTP Response:
```
HTTP/1.1 200 OK
Content-Type: text/html

<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8" />
		<title>/uri-res/N2Ls?urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a</title>
	</head>
	<body>
		<h1>/uri-res/N2Ls?urn:sha256:c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a</h1>
		<ul>
			<li><a href="http://www.example.com/path/to/file.txt">http://www.example.com/path/to/file.txt</a></li>
			<li><a href="http://something.test/mirror/thefile.txt">http://something.test/mirror/thefile.txt</a></li>
		<ul>
	</body>
</html>
```

## See Also
* [IETF RFC-2169: A Trivial Convention for using HTTP in URN Resolution](https://tools.ietf.org/html/rfc2169) (June 1997)
* [HTTP Extensions for a Content-Addressable Web](http://lists.w3.org/Archives/Public/www-talk/2001NovDec/0090.html) (October 2001)
