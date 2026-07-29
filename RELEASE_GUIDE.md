# Publishing future versions

The canonical source files live in the local `text_browser` folder. Every
release should follow this sequence:

1. Update the source workbook or reader template.
2. Increase the semantic version in `VERSION`.
3. Run `python3 build_david_celeste_reader.py`.
4. Copy the rebuilt reader to this repository as both `index.html` and
   `david-celeste-imessage-player.html`.
5. Copy the current workbook, README, and all reader/research screenshots into
   this repository.
6. Commit and push the changes to `main`. GitHub Pages will update the online
   reader.
7. Rebuild `share/David-Celeste-Courtroom-Text-Reader.zip` and
   `share/SHA256SUMS.txt`.
8. Create and push a matching tag, such as `v1.1.0`, then publish the ZIP and
   checksum with `gh release create`. The authenticated GitHub token currently
   lacks the separate `workflow` scope, so release publishing is intentionally
   manual and does not require expanding account permissions.

Use patch versions for fixes, minor versions for new features or added source
material, and major versions for incompatible changes.

The in-reader update check reads the latest GitHub release tag. Keep the
`VERSION` file and release tag identical except for the tag's leading `v`.
