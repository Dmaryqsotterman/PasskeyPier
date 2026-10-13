# Contributing

Thanks for looking. A few things that make a change easy to take:

1. Open an issue first for anything larger than a bug fix, so we agree on the shape.
2. Keep the change focused - one behaviour per pull request.
3. Run `go vet ./...`, `go build ./...` and `go test ./...` before opening the PR.
   For the web layer, `npm --prefix web run build`.
4. Add a test for the behaviour you changed. The ceremony and harbour packages
   both have table tests to copy from.
5. Match the surrounding style; the core is deliberately small and flat.
6. Run `gofmt -l .` before pushing; CI is strict about it.
