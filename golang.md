# Golang

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**

- [doc](#doc)
- [Install packages](#install-packages)
- [Awesome go](#awesome-go)
- [Update packages](#update-packages)
- [Necessary dev tools](#necessary-dev-tools)
- [Programming](#programming)
- [goroutine/chanel](#goroutinechanel)
- [Performance](#performance)
- [Test](#test)
- [Data Structure](#data-structure)
- [Code generator](#code-generator)
- [IO](#io)
- [File format](#file-format)
- [Algorithm](#algorithm)
- [Marchine Learning](#marchine-learning)
- [Math](#math)
- [Statistics](#statistics)
- [NLP](#nlp)
- [Util](#util)
- [Code generator](#code-generator-1)
- [CLI](#cli)
- [JSON](#json)
- [Serialization](#serialization)
- [Text](#text)
- [Markdown](#markdown)
- [WEB](#web)
- [Cache](#cache)
- [DB](#db)
- [GUI](#gui)
- [Figure and Chart](#figure%C2%A0and-chart)
- [Image](#image)
- [Graphics](#graphics)
- [PDF](#pdf)
- [HPC](#hpc)
- [Distributed systems](#distributed-systems)
- [Flow / piple](#flow--piple)
- [Glue](#glue)
- [misc](#misc)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->


## doc

-  [A curated selection of blog posts on Go](https://github.com/enocom/gopher-reading-list)
-  [Ten Useful Techniques in Go](http://arslan.io/ten-useful-techniques-in-go)
-  [Effective Go in chinese](http://www.hellogcc.org/effective_go.html)
-  [(Draft) Traps, Gotchas, and Common Mistakes in Go (golang)](http://devs.cloudimmunity.com/gotchas-and-common-mistakes-in-go-golang/)
-  Rob Pike的Go语言PPT教程翻译[1](http://tonybai.com/2012/08/23/the-go-programming-language-tutorial-part1/),[2](http://tonybai.com/2012/08/27/the-go-programming-language-tutorial-part2/),[3](http://tonybai.com/2012/08/28/the-go-programming-language-tutorial-part3/)
-  [Translating Effective Python into Go: Know When to Use Channels for Generator-Like Functions](http://www.informit.com/articles/article.aspx?p=2359758)
- [go-best-practices-2016](https://peter.bourgon.org/go-best-practices-2016/)
- [年终盘点！2017年超有价值的Golang文章](http://colobu.com/2017/12/28/top-golang-articles-of-2017/)
- [go-under-the-hood](https://github.com/changkun/go-under-the-hood) [Go 语言原本](https://changkun.de/golang/)

- [Go语言高级编程(Advanced Go Programming)](https://chai2010.cn/advanced-go-programming-book/)

## Install packages

Use proxy, or use [Gopm](https://github.com/gpmgo/gopm).
```
http_proxy=127.0.0.1:8087 go get **
```

for socks5 proxy

```
sudo dnf install privoxy
sudo echo forward-socks5 / 127.0.0.1:1080 . >> /etc/privoxy/config
sudo service privoxy restart
http_proxy=127.0.0.1:8118 go get **
```

Godoc and vet moved to the go.tools subrepository since go1.2, so

```
# go get code.google.com/p/go.tools/cmd/...
```

More official [sub-repositories](http://golang.org/pkg/#subrepo)

- crypto — additional cryptography packages.
- net — additional networking packages.
- sys — packages for making system calls.
- text — packages for working with text.
- tools — godoc, vet, cover, and other tools.
- exp — experimental code (handle with care; may change without warning).

install them

```
https_proxy=https://127.0.0.1:8118 go get -v golang.org/x/tools/cmd/{godoc,goimports,gorename,vet,gomvpkg,cover}
```

other great tools

```
go get -v github.com/golang/lint/golint
go get -v github.com/sqs/goreturns
```

update xcode-go

```
proxychains go get -u github.com/acroca/go-symbols
proxychains go get -u github.com/davidrjenni/reftools/cmd/fillstruct
proxychains go get -u github.com/haya14busa/goplay/cmd/goplay
proxychains go get -u github.com/mdempsky/gocode
proxychains go get -u github.com/sqs/goreturns
proxychains go get -u github.com/uudashr/gopkgs/v2/cmd/gopkgs
proxychains go get -u github.com/zmb3/gogetdoc
proxychains go get -u golang.org/x/lint/golint
proxychains go get -u golang.org/x/tools/cmd/gorename
proxychains go get -u golang.org/x/tools/gopls
proxychains go get -u github.com/cweill/gotests/...
proxychains go get -u github.com/rogpeppe/godef
proxychains go get -u github.com/ramya-rao-a/go-outline
proxychains go get -u github.com/go-delve/delve/cmd/dlv

```

## Awesome go

- [go.libhunt.com](https://go.libhunt.com)


## Update packages

```
go get -u github.com/astaxie/beego
```

Or use [gofresh](https://github.com/divan/gofresh) (Keep your Go package dependencies fresh.)

## Necessary dev tools

- [gometalinter](https://github.com/alecthomas/gometalinter) - Concurrently run Go lint tools and normalise their output
- goimports, [see more](https://michaelwhatcott.com/gosublime-goimports/)


## Programming

- [Good Code vs Bad Code in Golang](https://teivah.io/blog/good-code-vs-bad-code-in-golang/)
- [go-patterns](https://github.com/tmrts/go-patterns) - A curated list of Go patterns and idioms http://tmrts.com/go-patterns
- [composable-go-services-using-libchan/](http://blog.codeship.com/composable-go-services-using-libchan/)
- [libchan](https://github.com/docker/libchan) - Like Go channels over the network,
- [Interfaces in Go Object Oriented Go](https://medium.com/@gianbiondi/interfaces-in-go-59c3dc9c2d98#.8sk9pzn9g)
- [Go Traps](http://go-traps.appspot.com/)
- [50 Shades of Go: Traps, Gotchas, and Common Mistakes for New Golang Devs](http://devs.cloudimmunity.com/gotchas-and-common-mistakes-in-go-golang/)
- [Who needs generics? Use ... instead!](https://appliedgo.net/generics/), [Summary of Go Generics Discussions](https://docs.google.com/document/d/1vrAy9gMpMoS3uaVphB32uVXX4pi-HnNjkMEgyAHX4N4/edit#heading=h.vuko0u3txoew)
- [Practical advice for Go library authors](https://go-talks.appspot.com/github.com/cep21/go-talks/practical-advice-for-go-library-authors.slide)
- [Why are slices sometimes altered when passed by value in Go?](https://www.calhoun.io/why-are-slices-sometimes-altered-when-passed-by-value-in-go/)
- [How to ship production-grade Go](https://www.oreilly.com/ideas/how-to-ship-production-grade-go)
- [There is no pass-by-reference in Go](https://dave.cheney.net/2017/04/29/there-is-no-pass-by-reference-in-go)
- [**The ultimate guide to writing a Go tool**](https://arslan.io/2017/09/14/the-ultimate-guide-to-writing-a-go-tool/)
- [**Allocation Efficiency in High-Performance Go Services**](https://segment.com/blog/allocation-efficiency-in-high-performance-go-services/)
- [*Memory Blocks in Go*](http://www.tapirgames.com/blog/golang-memory-management)
- [Writing a very fast cache service with millions of entries in Go](https://allegro.tech/2016/03/writing-fast-cache-service-in-go.html)
- [The empty struct{}](https://dave.cheney.net/2014/03/25/the-empty-struct)
- [译文 如何使用 Go 1.13 里的错误处理](https://gocn.vip/topics/9858)
- [GO编程模式系列](https://coolshell.cn/articles/21128.html)

packages

- [go-promise](https://github.com/fanliao/go-promise) - A library implement futrue and promise
- [bufferManager.go](https://github.com/songgao/bufferManager.go) - bufferManager demonstrates a technique to decrease pressure on GC in Go.

## goroutine/chanel

tutorials

- [Using contexts to avoid leaking goroutines](http://golang.rakyll.org/leakingctx/)
- [Mastering concurrency in Go](https://www.outlearn.com/learn/matryer/mastering-concurrency-in-go)
- [Go channels are bad and you should feel bad](http://www.jtolds.com/writing/2016/03/go-channels-are-bad-and-you-should-feel-bad/?utm_source=statuscode&utm_medium=medium)
- [Channels in Golang](http://www.tapirgames.com/blog/golang-channel)
- [**How To Close Channels in Golang Elegantly**](http://www.tapirgames.com/blog/golang-channel-closing)

packages

- [go-broadcast](https://github.com/dustin/go-broadcast) - A trivial channel pubsub I use in lots of projects. http://godoc.org/github.com/dustin/go-broadcast
- [tunny](https://github.com/Jeffail/tunny) - A goroutine pool for golang
- [abool](https://github.com/tevino/abool) - Atomic Boolean library for cleaner Golang code, optimized for performance yet simple to use.


## Performance

- [Go Performance Tales](http://jmoiron.net/blog/go-performance-tales/)
- [**So You Wanna Go Fast?**](http://bravenewgeek.com/so-you-wanna-go-fast/)
- [**writing-high-performance-go**](http://go-talks.appspot.com/github.com/davecheney/presentations/writing-high-performance-go.slide)
    The compiler implements a specific optimisation for this case
    
        var m map[string]string
        v, ok := m[string(bytes)]
    
    This will avoid the conversion of the byte slice to a string for the map lookup. This is very specific, it won't work if you do something like
    
        key := string(bytes)
        val, ok := m[key]

- [技术分享之《golang高性能实战》](http://xiaorui.cc/2018/04/09/%E6%8A%80%E6%9C%AF%E5%88%86%E4%BA%AB%E4%B9%8B%E3%80%8Agolang%E9%AB%98%E6%80%A7%E8%83%BD%E5%AE%9E%E6%88%98%E3%80%8B/)
- [gcvis](https://github.com/davecheney/gcvis) - Visualise Go program GC trace data in real time http://dave.cheney.net/2014/07/11/visualising-the-go-garbage-collector
- [go-torch](https://github.com/uber/go-torch) - Stochastic flame graph profiler for Go programs
- [Visualizing profiling in Go: A different way](http://www.florinpatan.ro/2016/05/visualizing-profiling-in-go-different.html)
- [如何监控 golang 程序的垃圾回收](https://holys.im/2016/07/01/monitor-golang-gc/)
- [Debugging performance issues in Go programs](https://software.intel.com/en-us/blogs/2014/05/10/debugging-performance-issues-in-go-programs)
- [golang手动管理内存](http://my.oschina.net/lubia/blog/175154)
- [go-filemutex](https://github.com/alexflint/go-filemutex) - Like sync.Mutex, but works across processes
- [Profiler labels in Go 1.9+](https://rakyll.org/profiler-labels/)
- [Go code refactoring : the 23x performance hunt](https://medium.com/@val_deleplace/go-code-refactoring-the-23x-performance-hunt-156746b522f7)
- [2018-12-26-在Go中恰到好处的内存对齐](https://github.com/EDDYCJY/blog/blob/master/golang/2018-12-26-在Go中恰到好处的内存对齐.md)
- [String interning in Go](https://artem.krylysov.com/blog/2018/12/12/string-interning-in-go/)


Packages:

Applications:

- [rush](https://github.com/shenwei356/rush) -- parallelly execute shell commands. A GNU parallel like tool in Go. It supports Linux/OS X/Windows!

## Test

- [**testify**](https://github.com/stretchr/testify) - A toolkit with common assertions and mocks that plays nicely with the standard library
- [gotests](https://github.com/cweill/gotests) - Generate better Go tests from your source code.

## Data Structure

- **[go-datastructures](https://github.com/Workiva/go-datastructures)** - Go-datastructures is a collection of useful, performant, and threadsafe Go datastructures.
- [**golang-set**](https://github.com/deckarep/golang-set) - A simple set type for the Go language.
- [set](https://github.com/fatih/set) - Set is a basic and simple, hash-based, Set data structure implementation in Go (Golang)
- [**set**](https://github.com/xtgo/set) - General, type-safe, non-allocating set-operations for any sort.Interface
- [pmap (ParallelMap)](https://github.com/shenwei356/pmap) - A lock-free parallel map in go
- [concurrent-map](https://github.com/streamrail/concurrent-map) - provides a high-performance solution to this by sharding the map with minimal time spent waiting for locks.
- [lane](https://github.com/oleiade/lane) - A golang queues, stacks and deques implementation library
- [btree](https://github.com/google/btree) - by google
- [btree](https://github.com/tidwall/btree) - tidwall's folk
- [bloom](https://github.com/willf/bloom) - Go package implementing Bloom filters
- [cfilter](https://github.com/irfansharif/cfilter) - Cuckoo Filter implementation in Go, better than Bloom Filters
- [bitset](https://github.com/willf/bitset) - Go package implementing bitsets
- [countminsketch](https://github.com/shenwei356/countminsketch) - An implementation of Count-Min Sketch in Golang
- **[BoomFilters](https://github.com/tylertreat/BoomFilters)** - Probabilistic data structures for processing continuous, unbounded streams. This includes Stable Bloom Filters, Scalable Bloom Filters, Counting Bloom Filters, Inverse Bloom Filters, Cuckoo Filters, several variants of traditional Bloom filters, HyperLogLog, Count-Min Sketch, and MinHash
- [cuckoofilter](https://github.com/seiflotfy/cuckoofilter) - Cuckoo Filter: Practically Better Than Bloom
- [goraph](https://github.com/gyuho/goraph) - Package goraph implements graph, tree data structures and algorithms.
- [go-radix](https://github.com/armon/go-radix) - Golang implementation of Radix trees, [go-immutable-radix](https://github.com/hashicorp/go-immutable-radix)
- [sortutil](https://github.com/cznic/sortutil) - Utilities supplemental to the Go standard "sort" package
- [golib/sort](https://github.com/tideland/golib#sort) - Parallel Quicksort.
- [go-minhash](https://github.com/dgryski/go-minhash) - BottomK minwise hashing for streaming set similarity
- [hyperloglog](https://github.com/clarkduvall/hyperloglog) - HyperLogLog and HyperLogLog++ implementation in Go/Golang. http://godoc.org/github.com/clarkduvall/hyperloglog
- [**hyperloglog**](https://github.com/axiomhq/hyperloglog) - HyperLogLog with lots of sugar (Sparse, LogLog-Beta bias correction and TailCut space reduction)
- [mafsa](https://github.com/smartystreets/mafsa) - Package mafsa implements Minimal Acyclic Finite State Automata in Go, essentially a high-speed, memory-efficient, Unicode-friendly set of strings. https://godoc.org/github.com/smartystreets/mafsa

Persistent

- [goque](https://github.com/beeker1121/goque) - Persistent stacks, queues, and priority queues for Go backed by LevelDB

## Code generator

- [gen](https://github.com/clipperhouse/gen) - Type-driven code generation for Go http://clipperhouse.github.io/gen/
- [gengen](https://github.com/joeshaw/gengen) - A Go source transformation tool for generics
- [generic](https://github.com/taylorchu/generic) - A code generation tool to enable generics in go
- [genny](https://github.com/cheekybits/genny) - Elegant generics for Go


## IO

- [xopen](https://github.com/brentp/xopen) - open files for buffered reading and writing in #golang
- [readahead](https://github.com/klauspost/readahead) - Asynchronous read-ahead for Go readers
- [pgzip](https://github.com/klauspost/pgzip) - Go parallel gzip (de)compression
- [compress](https://github.com/klauspost/compress) - Optimized compression packages
- [breader](https://github.com/shenwei356/breader) - breader (Buffered File Reader), asynchronous parsing and pre-processing while reading file. Safe cancellation is also supported.


## File format

- [xlsx](https://github.com/tealeg/xlsx) - Google Go (golang) library for reading and writing XLSX files.
- [multicorecsv](https://github.com/mzimmerman/multicorecsv) - A multicore csv reader library in Go. 3X
- [copmress](https://github.com/dsnet/compress) - Collection of compression related Go packages.
- [csvtk](https://github.com/shenwei356/csvtk) - Another cross-platform, efficient, practical and pretty CSV/TSV toolkit in Golang http://bioinf.shenwei.me/csvtk

## Algorithm

- [graph](https://github.com/gonum/graph) - Graph packages for the Go language
- [golearn](https://github.com/sjwhitworth/golearn) - Machine Learning for Go
- [gonn](https://github.com/fxsjy/gonn) -GoNN is an implementation of Neural Network in Go Language, which includes BPNN, RBF, PCN
- [CloudForest](https://github.com/ryanbressler/CloudForest) - Ensembles of decision trees in go/golang.
- [bayesian](https://github.com/jbrukh/bayesian) - Naive Bayesian Classification for Golang.
- [go-galib](https://github.com/thoj/go-galib) - Genetic Algorithms library written in Go / golang
- [algorithms](https://github.com/arnauddri/algorithms) - Algorithms & Data Structures in Go

## Marchine Learning

- [gorgonia](https://github.com/chewxy/gorgonia) - Gorgonia is a library that helps facilitate machine learning in Go.

## Math

- [geom](https://github.com/skelterjohn/geom) - 2d geometry for golang
- [gonum](https://github.com/gonum)
- [pip-go](https://github.com/JamesMilnerUK/pip-go) - Point in polygon implemented in Go

## Statistics

- [stats](https://github.com/montanaflynn/stats) - A statistics package with common functions that are missing from the Golang standard library.
- [stat](https://github.com/grd/stat) - https://github.com/grd/stat  t-test
- [stat](https://github.com/gonum/stat) - Statistics package for Go

## NLP

- [go-pinyin]( https://github.com/mozillazg/go-pinyin)

## Util

log

- [log4go ](http://code.google.com/p/log4go/)- Logging package similar to log4j for the Go programming language
- [log15](https://github.com/inconshreveable/log15) - Simple, powerful logging for Go

Others

- [gouuid](https://github.com/nu7hatch/gouuid) - Pure Go UUID implementation
- [basex](https://github.com/dineshappavoo/basex) - Create Youtube-Like IDs With Golang
- [quarnster/util](https://github.com/quarnster/util) - Various Go utility code
- [daemon](https://github.com/takama/daemon) - A daemon package for use with Go (golang) services with no dependencies
- [shutdown](https://github.com/klauspost/shutdown) - Shutdown management library for Go
- [Gox](https://github.com/mitchellh/gox) - Simple Go Cross Compilation。更新go版本后，记得gox -build-toolchain
- [goxc](https://github.com/laher/goxc) - a build tool for Go, with a focus on cross-compiling, packaging and deployment
- [clipboard](https://github.com/atotto/clipboard) - clipboard for golang
- [go.pipeline](https://github.com/songgao/go.pipeline) - go.pipeline is a utility library that imitates unix pipeline. It simplifies chaining unix commands (and other stuff) in Go.
- [go-qrcode](https://github.com/skip2/go-qrcode) - :sparkles: QR Code encoder (Go) http://go-qrcode.appspot.com
- [commonregex](https://github.com/mingrammer/commonregex) - A collection of common regular expressions for Go
- [cwalk](https://github.com/iafan/cwalk) - cwalk = Concurrent filepath.Walk replacement (Go)

Date

- [monday](https://github.com/mikespook/) - Monday is a minimalistic translator for month and day of week names in time.Date objects
- [Now](https://github.com/jinzhu/now) - Now is a time toolkit for golang

Debug

- [go-spew](https://github.com/davecgh/go-spew) - Go-spew implements a deep pretty printer for Go data structures to aid in debugging.
- [Debugging Goroutines: How to debug like a pro](https://vtimothy.com/posts/debugging-goroutines/)
- [Debugging in Go with Delve](https://eleni.blog/2020/12/19/debugging-in-go-with-delve/)

Release

- [staticfiles](https://github.com/bouk/staticfiles) - staticfiles compiles a directory of files into an embeddable .go
- [govvv](https://ahmetalpbalkan.com/blog/govvv/) – Versioning for Go binaries

## Code generator

- [go-poet](https://github.com/dpolansky/go-poet/) - A Go package for generating Go code

## CLI

- **[cobra](https://github.com/spf13/cobra)** - A Commander for modern Go CLI interactions
- [flag2](https://github.com/ProfOak/flag2) - A more traditional flag library for the go programming language
- [writ](https://github.com/bobziuchkovski/writ) - A flexible command and option parser for Go
- [go-arg](https://github.com/alexflint/go-arg) - Struct-based argument parsing in Go
- [cli](https://github.com/codegangsta/cli) - A small package for building command line apps in Go
- **[color](https://github.com/fatih/color)** - Color package for Go (golang) [http://godoc.org/github.com/fatih/color](http://godoc.org/github.com/fatih/color) . It has support for Windows too
- [emoji](https://github.com/kyokomi/emoji) - emoji terminal output for golang
- [go-sh](https://github.com/codeskyblue/go-sh) - like python-sh, for easy call shell with golang.
- [uitable ](https://github.com/gosuri/uitable) - A go library to improve readability in terminal apps using tabular data
- **[uiprogress](https://github.com/gosuri/uiprogress)** - A go library to render (multi) progress bars in terminal applications.
- [barely](https://github.com/reconquest/barely) - Simple and extensible status bar to pretty display of Go-lang program's progress
- [pb](https://github.com/cheggaaa/pb) - Console progress bar for Golang
- [viper](https://github.com/spf13/viper) -Go configuration with fangs
- [goconfig](https://github.com/Unknwon/goconfig) - goconfig is a easy-use comments-support configuration file(.ini) parser for the Go Programming Language
- [go-homedir](https://github.com/mitchellh/go-homedir) - Go library for detecting and expanding the user's home directory without cgo.
- [go-prettytable](https://github.com/tatsushid/go-prettytable) - A library for Golang to build a simple text table with a multibyte, doublewidth character support
- [教你写一个color日志库，不止有代码还有原理。](https://www.zybuluo.com/aliasliyu4/note/612147?hmsr=toutiao.io&utm_medium=toutiao.io&utm_source=toutiao.io)
- [tablewriter](https://github.com/olekukonko/tablewriter) - ASCII table in golang
- [Handling CTRL-C (interrupt signal) in Golang Programs](https://nathanleclaire.com/blog/2014/08/24/handling-ctrl-c-interrupt-signal-in-golang-programs/)
- [**multibar**](https://github.com/sethgrid/multibar) - Display multiple progress bars in Go (golang).
- [spinner](https://github.com/briandowns/spinner) - Go (golang) package for providing a terminal spinner/progress indicator with options.
- [**go-prompt**](https://github.com/c-bata/go-prompt) - Building a powerful interactive prompt in Go, inspired by python-prompt-toolkit.
- [promptui](https://github.com/manifoldco/promptui) - Interactive prompt for command-line applications
- [beeep](https://github.com/gen2brain/beeep) - Go cross-platform library for sending desktop notifications and beeps


## JSON

- [gjson](https://github.com/tidwall/gjson) - Get JSON values very quickly in Go
- [megajson](https://github.com/benbjohnson/megajson) - A JSON parser generator for high performance encoding and decoding in Go.
- [gojson](https://github.com/ChimeraCoder/gojson) - A simple command-line tool for manipulating JSON for use in developing Go cod
- [jsonpp](https://github.com/jmhodges/jsonpp) - A command line JSON pretty printer.

Needing code generation

- [ffjson](https://github.com/pquerna/ffjson): faster JSON for Go
- [easyjson](https://github.com/mailru/easyjson) - Fast JSON serializer for golang.

Using reflection


xxx

- [jsonparser](https://github.com/buger/jsonparser) - Alternative JSON parser for Go that does not require schema (so far fastest)
- [gojay](https://github.com/francoispqt/gojay) - fastest JSON encoder/decoder with powerful stream API for Golang
- [json-iterator/go](https://github.com/json-iterator/go) - A high-performance 100% compatible drop-in replacement of "encoding/json"
- [fastjson](https://github.com/valyala/fastjson) - Fast JSON parser and validator for Go. No custom structs, no code generation, no reflection

## Serialization

- [Practical Golang: Using Protobuffs](https://jacobmartins.com/2016/05/24/practical-golang-using-protobuffs/)

## Text

- [go-humanize](https://github.com/dustin/go-humanize) - Go Humans! (formatters for units to human friendly sizes) https://godoc.org/github.com/dustin/go-humanize
- [A modern text indexing library for go](https://github.com/blevesearch/bleve)
- [govalidator](https://github.com/asaskevich/govalidator) - Package of string validators and sanitizers for Go lang
- [iconv](https://github.com/qiniu/iconv) - Golang bindings to libiconv - Convert string to requested character encoding
- [diff](https://github.com/mb0/diff) - Go difference algorithm
- [bmatch](https://github.com/AndreasBriese/bmatch) is faster fixed pattern search for Go.
- [bleve](https://github.com/blevesearch/bleve) - A modern text indexing library for go

## Markdown

- [blackfriday ](https://github.com/russross/blackfriday)- a markdown processor for Go

## WEB

doc 

- [Go Web Examples](https://gowebexamples.github.io/)
- [Top 6 web frameworks for Go as of 2017](https://dev.to/speedwheel/top-6-web-frameworks-for-go-as-of-2017-34i)

packages

- [gorilla](https://github.com/gorilla) - Gorilla web toolkit
- [go.rice](https://github.com/GeertJohan/go.rice) is a Go package that makes working with resources such as html,js,css,images,templates, etc very easy.
- **[gin](https://gin-gonic.github.io/gin/)** - Gin is a HTTP web framework written in Go (Golang). It features a Martini-like API with much better performance, up to 40 times faster. If you need smashing performance, get yourself some Gin. [Building Go Web Applications and Microservices Using Gin](https://semaphoreci.com/community/tutorials/building-go-web-applications-and-microservices-using-gin)
- [beego](https://github.com/astaxie/beego) - beego is an open-source, high-performance web framework for the Go programming language. [http://beego.me](http://beego.me/)
- [**echo**](https://github.com/labstack/echo) - Echo is a fast :rocket: and unfancy micro web framework for Golang. http://echo.labstack.com
- [ace](https://github.com/yosssi/ace) - HTML template engine for Go [http://ace.yoss.si/](http://ace.yoss.si/)
- [osin](https://github.com/RangelReale/osin) - Golang OAuth2 server library
- [go-oauth](https://github.com/garyburd/go-oauth) - OAuth 1.0 client package for Go
- [go-http-auth](https://github.com/abbot/go-http-auth) - Basic and Digest HTTP Authentication for golang http
- [gomniauth](https://github.com/stretchr/gomniauth) - Authentication framework for Go applications.
- [hawk](https://github.com/hueniverse/hawk)  - HTTP Holk Authentication Schemz
- [gopencils](https://github.com/bndr/gopencils) - Easily consume REST APIs with Go (golang)
- [code.google.com/p/go.crypto/ssh](https://godoc.org/code.google.com/p/go.crypto/ssh) - Package ssh implements an SSH client and server. [example](http://kukuruku.co/hub/golang/ssh-commands-execution-on-hundreds-of-servers-via-go)
- [go-pkg-rss](https://github.com/jteeuwen/go-pkg-rss) - reads RSS and Atom feeds and provides a caching mechanism that adheres to the feed specs.
- [feeds](https://github.com/gorilla/feeds) - golang rss/atom generator library
- [postman](https://github.com/zachlatta/postman) - Command-line utility for batch-sending email. http://zachlatta.com/postman
- [gomail](https://github.com/go-gomail/gomail) - The best way to send emails in Go.
- [go-i18n](https://github.com/nicksnyder/go-i18n) - Translate your Go program into multiple languages with templates and CLDR plural support.
- [gorequest](https://github.com/parnurzeal/gorequest) - GoRequest -- Simplified HTTP client ( inspired by nodejs SuperAgent ) http://parnurzeal.github.io/gorequest/
- [melody](https://github.com/olahol/melody) - Minimalist websocket framework for Go

## Cache

- [bigcache](https://github.com/allegro/bigcache)

## DB

KV

- [goleveldb](https://github.com/syndtr/goleveldb) - LevelDB key/value database in Go.
- [bolt](https://github.com/boltdb/bolt) - A low-level key/value database for Go.
- [storm](https://github.com/asdine/storm) - Simple and powerful toolkit for BoltDB
- [etcd](https://github.com/coreos/etcd) - A highly-available key value store for shared configuration and service discovery
- [badger](https://github.com/dgraph-io/badger) - An embeddable, persistent, simple and fast key-value (KV) store, written natively in Go. Optimize for SSDs

In-memory

- [buntdb](https://github.com/tidwall/buntdb) - BuntDB is an embeddable, in-memory key/value database for Go with custom indexing and geospatial support
- [summitdb](https://github.com/tidwall/summitdb) - In-memory NoSQL database with ACID transactions, Raft consensus, and Redis API
- [go-memdb](https://github.com/hashicorp/go-memdb) - Golang in-memory database built on immutable radix trees
- [yakdb](https://github.com/needcaffeine/yakdb) - yakdb (yet another key-value database) is a highly-performant in-memory key-value store written in Go. http://vicvijayakumar.com/yakdb-a-nosql-database-in-go.html

doc

- [tiedot](https://github.com/HouzuoGuo/tiedot) - a document database engine that uses JSON as document notation

rich data structure

- [SSDB](https://github.com/ideawu/ssdb) - A fast NoSQL database for storing big list of data
- [ledisdb](https://github.com/siddontang/ledisdb) - a high performance NoSQL powered by Go
- [tidb](https://github.com/pingcap/tidb) - TiDB is a distributed SQL database compatible with MySQL protocol.

graph

- [dgraph](https://github.com/dgraph-io/dgraph) - Scalable, Distributed, Low Latency Graph Database
## ORM

- [gorm](https://github.com/jinzhu/gorm) - The fantastic ORM library for Golang, aims to be developer friendly
- [go-sqlite3](https://github.com/mattn/go-sqlite3) - sqlite3 driver for go that using database/sql [http://mattn.kaoriya.net/](http://mattn.kaoriya.net/)
- [beego orm](https://github.com/astaxie/beego/tree/master/orm) - A powerful orm framework for go
- [qbs](https://github.com/coocood/) - QBS stands for Query By Struct. A Go ORM

## GUI

- [go-qt5 ](https://github.com/salviati/go-qt5)- qt5 bindings for go

## Figure and Chart

- [plotinum](https://code.google.com/p/plotinum/) - A plotting library for the Go programming language.
- [chart](https://github.com/vdobler/chart) - Basic charts in go. This package focuses more on autoscaling, error bars, and logarithmic plots than on beautifull or marketing ready charts.
- [gosplat ](https://github.com/agonopol/gosplat)- Easily generate html/js graphs in go with dygraphs/gochart
- [svgo](https://github.com/ajstarks/svgo) - Go Language Library for SVG generation. [paper](http://www.svgopen.org/2011/papers/34-SVGo_a_Go_Library_for_SVG_generation/), [slide](https://speakerdeck.com/ajstarks/programming-pictures-with-svgo)
- [gonum/plot](https://github.com/gonum/plot/wiki/Example-plots), [example](https://github.com/gonum/plot/wiki/Example-plots)


## Image

- [gift](https://github.com/disintegration/gift) - Go Image Filtering Toolkit
- [bild](https://github.com/anthonynsimon/bild) - A collection of parallel image processing algorithms in pure Go

## Graphics

- [gg](https://github.com/fogleman/gg) - Go Graphics - 2D rendering in Go with a simple API. https://godoc.org/github.com/fogleman/gg

3D

-  [ln](https://github.com/fogleman/ln) - 3D line art engine.

## PDF

- [signintech/gopdf](https://github.com/signintech/gopdf) - A simple library for generating PDF written in Go lang [Chinese supported]
- [gofpdf](https://github.com/jung-kurt/gofpdf) - A PDF document generator with high level support for text, drawing and images [Chinese not supported]

## HPC

- [hpcgo](https://github.com/drio/hpcgo) - Helping submit jobs to HPC cluster
- [mpi](https://github.com/marcusthierfelder/mpi) - mpi-binding for golang
- [circuit](https://github.com/gocircuit/circuit)
- [go-workers](https://github.com/jrallison/go-workers) - Sidekiq compatible background workers in golang
- [glow](https://github.com/chrislusf/glow) - Glow is an easy-to-use distributed computation system written in Go, similar to Hadoop Map Reduce, Spark, Flink, Samza, etc. Currently just started and not feature rich yet, but should be reliable to run most common cases.

## Distributed systems

- [Go kit](https://github.com/go-kit/kit) is a distributed programming toolkit for building microservices in large organizations.
- [gam](https://github.com/rogeralsing/gam) - Go Actor Model framework - Ultra fast distributed actors for Golang
- [rpcx](https://github.com/smallnest/rpcx) - rpcx is a distributed RPC service framework based net/rpc like alibaba Dubbo and weibo Motan. Implemented by Go
- [mesh](https://github.com/weaveworks/mesh) - Mesh is a tool for building distributed applications.
- [Beehive](https://github.com/kandoo/beehive) Beehive is a distributed programming framework that comes with built-in transactions, replication, fault-tolerance, runtime instrumentation, and optimized placement.
- [How we use gRPC to build a client/server system in Go](https://medium.com/pantomath/how-we-use-grpc-to-build-a-client-server-system-in-go-dd20045fa1c2)

## Flow / piple

- [goflow](https://github.com/trustmaster/goflow) - Flow-based and dataflow programming library for Go programming language


## Glue

- [gopy](https://github.com/go-python/gopy) generates a CPython extension module from a go package.

[Go projects index](https://code.google.com/p/go-wiki/wiki/Projects)

See more on [awesome-go](https://github.com/avelino/awesome-go), [golang opensource projects](http://www.open-open.com/lib/view/open1396063913278.html#Command-line_Option_Parsers)

## misc

- [range over interface{} which stores a slice](https://stackoverflow.com/questions/14025833/range-over-interface-which-stores-a-slice/14026030#14026030)
- [calendarheatmap](https://github.com/nikolaydubina/calendarheatmap)
- [Dump any data as valid syntax in Go](https://github.com/Code-Hex/dd)
