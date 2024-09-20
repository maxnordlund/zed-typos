# Typos Language Server

[Typos Language Server](https://github.com/tekumara/typos-lsp) support for Zed editor.

Typos is a spell checking tool using a list of commonly known typos, allowing it to have fewer false-positives than dictionary-based tools like [CSpell](https://github.com/streetsidesoftware/cspell).
This is a great alternative for CI/CD integration, but I would suggest using both.

## Installation

You can install this extension directly through Zed's extension marketplace.

## Configuration

The Typos extension can be configured through a `.typos.toml` configuration file, which reference can be found [here](https://github.com/crate-ci/typos/blob/master/docs/reference.md).

Additionally, you can configure it in your Zed's settings with the following:

```json
{
    "lsp": {
        "typos": {
            "initialization_options": {
                // Path to your typos config file, .typos.toml by default.
                "config": ".typos.toml",
                // Path to your typos-lsp executable, takes $PATH into account.
                "path": "typos-lsp",
                // Diagnostic severity within Zed. "Error" by default, can be:
                // "Error", "Hint", "Information", "Warning"
                "diagnosticSeverity": "Error",
                // Minimum logging level for the LSP, displayed in Zed's logs. "info" by default, can be:
                // "debug", "error", "info", "off", "trace", "warn"
                "logLevel": "info",
                // Traces the communication between ZED and the language server. Recommended for debugging only. "off" by default, can be:
                // "messages", "off", "verbose"
                "trace.server": "off"
            }
        }
    }
}
```

**WARNING**: When modifying your Typos configuration either in `typos.toml` or `Cargo.toml` you will need to reload the workspace to take them into account.
You do not need to reload when editing Zed's `settings.json`.
