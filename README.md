# tree-rs

### Project Description: A Modern `tree` in Rust

This project is a modern reimagining of the classic `tree` command, built in Rust for performance, safety, and correctness. It retains the core functionality beloved by users while overhauling the command-line interface to follow contemporary best practices.

The redesigned CLI prioritizes **clarity, consistency, and ergonomics** through several key principles:

*   **Intuitive Arguments:** It favors descriptive, long-form arguments (e.g., `--dirs-only`, `--full-path`) and reserves standard short flags (`-h` for help) for their expected functions.
*   **Consolidated Options:** Functionality is grouped logically under single, powerful flags. For example, sorting is managed with `--sort <key>` and output formats with `--output <format>`, reducing the number of top-level flags to remember.
*   **Ecosystem Harmony:** The design aligns with conventions established by other modern CLI tools like `eza`, `ripgrep`, and `bat`, making it feel familiar and predictable to users.

The goal is to create a `tree` command that is not only a powerful utility for scripting but is also a pleasure for users to discover and use interactively.

### `tree-rs` Command Arguments

### Basic Usage
- [ ] **`tree`**: Display the tree of the current directory.
- [ ] **`tree [path]`**: Display the tree of a specific path.
- [ ] **`tree [path1] [path2] ...`**: Display the tree for multiple paths.


### Filtering & Traversal Control
- [ ] **`-a, --all`**: List all files, including hidden "dotfiles".
- [ ] **`-L, --max-depth <level>`**: Descend only `<level>` directories deep. *(Note: -L is kept for legacy, though -M would avoid collision with `ls`'s --follow-symlinks)*.
- [ ] **`-d, --dirs-only`**: List directories only.
- [ ] **`--follow-symlinks`**: Follow symbolic links to directories as if they were real directories. *(Note: The ambiguous `-l` is removed to avoid conflict with `ls -l`)*.
- [ ] **`-x, --one-filesystem`**: Stay on the current filesystem only.
- [ ] **`-P, --pattern <glob>`**: Include only files and directories matching the wildcard `<glob>`.
- [ ] **`-I, --ignore <glob>`**: Exclude files and directories matching the wildcard `<glob>`.
- [ ] **`-i, --ignore-case`**: Makes pattern matching case-insensitive.
- [ ] **`--match-dirs`**: In pattern matching, apply the pattern to directory names to control traversal.
- [ ] **`--prune`**: Prune empty directories from the output.
- [ ] **`--limit-entries <num>`**: Do not descend into directories containing more than `<num>` entries.
- [ ] **`--from-file <file>`**: Read paths to process from a specified `<file>`.



### File Information Display
- [ ] **`-p, --permissions`**: Print file type and permissions.
- [ ] **`-u, --user`**: Print the username or UID.
- [ ] **`-g, --group`**: Print the group name or GID.
- [ ] **`-s, --size`**: Print the size of each file in bytes.
- [ ] **`--human`**: In combination with `--size`, print sizes in human-readable format (K, M, G). *(Note: `-h` is now reserved for `--help`)*.
- [ ] **`--si`**: Use SI units (powers of 1000) for human-readable sizes.
- [ ] **`--date`**: Print the last modification date. *(Replaces the ambiguous -D)*.
- [ ] **`--time-format <format>`**: Format the date/time output using `strftime` syntax.
- [ ] **`--inode`**: Print the inode number for each file.
- [ ] **`--dev`**: Print the device ID for each file.


### Sorting Options
- [ ] **`--sort <key>`**: Specify the sort key. Keys include:
    - `name` (default): Alphabetical sort.
    - `version`: Natural sort of numbers within text.
    - `time`: Sort by modification time.
    - `ctime`: Sort by status change time.
    - `none`: Do not sort; list in directory order.
- [ ] **`-r, --reverse`**: Reverse the sort order.
- [ ] **`--dirs-first`**: List directories before files at the same level.


### Output Formatting & Graphics
- [ ] **`-f, --full-path`**: Print the full path prefix for each file.
- [ ] **`--no-indent`**: Do not print the indentation lines.
- [ ] **`--color <when>`**: Control colorization. `<when>` can be:
    - `always`: Always use color (like original `-C`).
    - `auto` (default): Use color only when output is to a terminal.
    - `never`: Disable color (like original `-n`).
- [ ] **`--charset <type>`**: Set the character set for drawing lines. `<type>` can be:
    - `utf` (default): Use standard graphics characters.
    - `ascii`: Use plain ASCII characters (like original `-A`).
    - `ibm-pc`: Use CP437 line-drawing characters (like original `-S`).
- [ ] **`--raw`**: Print non-printable characters as-is. *(Replaces -N)*.
- [ ] **`--hide-non-printable`**: Replace non-printable characters with `?` (like original `-q`).
- [ ] **`--quote-names`**: Quote filenames in double quotes (like original `-Q`).
- [ ] **`--no-report`**: Omit the final file/directory count report.


### Machine-Readable Output Formats
- [ ] **`--output <format>`**: Generate output in a machine-readable format. `<format>` can be:
    - `xml` (like original `-X`)
    - `json` (like original `-J`)
    - `html` (like original `-H`)
- [ ] **`-o, --output-file <filename>`**: Send output to a specific file instead of stdout.
- [ ] **`--html-base <href>`**: Set the base H1 and title for HTML output.
- [ ] **`--html-title <title>`**: Set the title and H1 header for HTML output.
- [ ] **`--html-no-links`**: Disable hyperlinks in HTML output.


### Miscellaneous
- [ ] **`-h, --help`**: Print the help summary and exit.
- [ ] **`-V, --version`**: Print the program version and exit.
