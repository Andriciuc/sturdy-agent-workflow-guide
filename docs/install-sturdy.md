# Install sturdy

This page describes how to install `sturdy` on Linux and check that it works.

## Before you start

Make sure that you have the following:

- A Linux system with `curl` installed
- A user account with `sudo` privileges

## Download and install the package

1. Download the latest package:

    ```bash
    curl -LO https://example.com/sturdy/sturdy-latest.tar.gz
    ```

2. Extract the archive:

    ```bash
    tar -xzf sturdy-latest.tar.gz
    ```

3. Move the binary to a directory in your `PATH`:

    ```bash
    sudo mv sturdy /usr/local/bin/
    ```

## Check the installation

Run the following command:

```bash
sturdy --version
```

The output is similar to the following:

```text
sturdy 1.0.0
```

!!! note

    If the command is not found, check that `/usr/local/bin` is in your `PATH`.
