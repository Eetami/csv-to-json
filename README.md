# csv-to-json

Simple bash script for converting CSV to JSON.

The script read CSV from stdin and prints JSON to stdout.

## Example usage

Read from pipe

```console
$ echo "foo,bar
yolo,swag" | csv-to-json
[{"foo": "yolo","bar": "swag"}]
```

Read from file

```console
$ csv-to-json <foo-bar.csv
[{"foo": "yolo","bar": "swag"}]
```

Read from here document

```console
$ csv-to-json <<EOF
foo,bar
yolo,swag
EOF
[{"foo": "yolo","bar": "swag"}]
```

Read from here document and pipe to jq

```console
$ ./csv-to-json <<EOF | jq
> foo,bar
> yolo,swag
> EOF
[
  {
    "foo": "yolo",
    "bar": "swag"
  }
]
```
