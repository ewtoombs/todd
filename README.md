# todd
''Shove the output of a command down an HTTP connection.''

## Example: copy an entire folder over HTTP.

On the sending side:
```
> todd 1024 tar c some_folder
```
This starts a simple HTTP server on port 1024. Then, on the receiving side:
```
> curl remote.host:1024 | tar x
```
As soon as curl connects to the remote server, the remote server starts the
command `tar c some_folder` and sends the output to curl.
