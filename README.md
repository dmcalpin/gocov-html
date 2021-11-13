# Gocov HTML export

This is a simple helper tool for generating HTML output from
[axw/gocov](https://github.com/axw/gocov/)

Here is a screenshot:

![HTML coverage report screenshot](https://github.com/matm/gocov-html/blob/master/gocovh-html.png)

## Installation

Just type the following to install the program and its dependencies:
```
$ go get github.com/axw/gocov/gocov
$ go get github.com/matm/gocov-html
```

## Usage

`gocov-html` can read a JSON file or read from standard input:
```
$ gocov test strings | gocov-html > strings.html
ok      strings 0.700s  coverage: 98.1% of statements
```

The generated HTML content comes along with a default embedded CSS. Use the `-s` 
flag to use a custom stylesheet:
```
$ gocov test net/http | gocov-html -s mystyle.css > http.html
```

To properly report subpackage totals in the overview section, include a `-prefix` flag. This is usually your repository name.
```
$ gocov test ./... | gocov-html -prefix=github.com/username/repo/ > mypackage.html
```

For large reports, you may wish to forego printing the code itself. Use the `-summary=true` flag to omit function code in the report.
```
$ gocov test net/http | gocov-html -summary=true > http.html
```
