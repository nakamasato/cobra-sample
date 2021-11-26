# cobra sample

A sample Golang application with [cobra](https://github.com/spf13/cobra), which is used by many of Kubernetes operators and other applications.


## Getting Started

1. Install `cobra/cmd` to use `cobra` cli.
    ```bash
    go install github.com/spf13/cobra/cobra
    ```
1. Make your own directory.
    ```bash
    mkdir cobra-sample
    cd cobra-sample
    ```
1. Initialize go module.
    ```bash
    go mod init github.com/nakamasato/cobra-sample
    ```
1. Init cobra application with `cobra` cli.
    ```bash
    cobra init sample --pkg-name github.com/nakamasato/cobra-sample/sample
    Your Cobra application is ready at
    /Users/masato-naka/repos/nakamasato/cobra-sample/sample
    ```

    This command generates the following files:
    ```bash
    tree
    .
    ├── go.mod
    ├── go.sum
    └── sample
        ├── LICENSE
        ├── cmd
        │   └── root.go
        └── main.go
    ```

1. Update `sample/cmd/root.go`
    ```go
    Run: func(cmd *cobra.Command, args []string) {
		fmt.Println("Hello world!")
	},
    ```
1. Change directory to `sample`
    ```bash
    cd sample
    ```
1. Run.
    ```bash
    go run main.go
    Hello world!
    ```

For more details, please read https://github.com/spf13/cobra
