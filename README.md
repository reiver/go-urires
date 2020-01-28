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
```

URCs express **characteristics** — meta-data — about a URL, or URN.

## Resolution Service

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

## See Also
* [IETF RFC-2169: A Trivial Convention for using HTTP in URN Resolution](https://tools.ietf.org/html/rfc2169) (June 1997)
* [HTTP Extensions for a Content-Addressable Web](http://lists.w3.org/Archives/Public/www-talk/2001NovDec/0090.html) (October 2001)
