# Release checklist

> Precondition: You will need https://github.com/sunng87/cargo-release for this

1. Make sure you are on latest master
2. Create a new branch: `git checkout -b release`
3. Navigate to the crate you want to release
4. Check the changes since the last release: `git diff CRATE-VERSION` f.e. `git diff testcontainers-0.4.0`
5. Determine the degree of changes according to the [Release Guide](./RELEASING.md)
6. Issue `cargo release --dry-run <DEGREE>`, f.e. `cargo release --dry-run minor`
7. Verify that the correct release process would happen
8. Run `cargo release <DEGREE>` without the `--dry-run` flag
9. Repeat (1)-(8) for all crates that need to be released
10. Submit a PR with the bumped versions
11. (optional) If you just released a new crate, do: `cargo owner --add github:coblox:cargo-owners`
