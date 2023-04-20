# How to create sample-cli with cobra

1. Make your own directory.
    ```bash
    mkdir cobra-sample
    cd cobra-sample
    ```
1. Initialize go module.
    ```bash
    go mod init github.com/nakamasato/cobra-sample
    ```
1. Install `cobra-cli` cli.
    ```bash
    go install github.com/spf13/cobra-cli@latest
    ```
1. Init cobra application with `cobra` cli.
    ```bash
    cobra-cli init sample-cli --author nakamasato
    Your Cobra application is ready at
    /Users/masato-naka/repos/nakamasato/cobra-sample/sample-cli
    ```

    This command generates the following files:
    ```bash
    tree
    .
    ├── go.mod
    ├── go.sum
    └── sample-cli
        ├── LICENSE
        ├── cmd
        │   └── root.go
        └── main.go
    ```

    Somehow, need to update import in `sample-cli/main.go`:

    ```diff
    - import "github.com/nakamasato/cobra-sample/cmd"
    + import "github.com/nakamasato/cobra-sample/sample-cli/cmd"
    ```

1. Update `sample/cmd/root.go`
    ```go
    Run: func(cmd *cobra.Command, args []string) {
		fmt.Println("Hello world!")
	},
    ```

1. Run.
    ```bash
    go run sample/main.go
    Hello world!
    ```

For more details, please read

1. https://github.com/spf13/cobra
1. https://github.com/spf13/cobra-cli/blob/main/README.md
