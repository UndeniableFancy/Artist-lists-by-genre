# Artist lists by genre

Four Lidarr Custom Lists generated from the supplied CSV artist lists. Both jazz lists are combined: the 267 original names are all included among the 1,067 expanded names, as checked before deduplication. Unresolved artists are excluded from the JSON and listed explicitly in the omission report.

## Raw list URLs and coverage

| List | Source names | Matched names | Published IDs | Unresolved |
|---|---:|---:|---:|---:|
| [Rock artists](https://raw.githubusercontent.com/UndeniableFancy/Artist-lists-by-genre/main/Rock%20artists.json) | 449 | 447 | 447 | 2 |
| [HipHop Artists](https://raw.githubusercontent.com/UndeniableFancy/Artist-lists-by-genre/main/HipHop%20Artists.json) | 191 | 191 | 191 | 0 |
| [Jazz Artists](https://raw.githubusercontent.com/UndeniableFancy/Artist-lists-by-genre/main/Jazz%20Artists.json) | 1067 | 1053 | 1042 | 14 |
| [Electronics Artists](https://raw.githubusercontent.com/UndeniableFancy/Artist-lists-by-genre/main/Electronics%20Artists.json) | 333 | 331 | 328 | 2 |

## Use in Lidarr

Open Settings → Import Lists and add a Custom List. Paste a raw JSON link from the table into List URL, select your desired profiles, root folder, and monitoring options, then test and save. Use the matching title as the list name.

The files are top-level arrays of `{"MusicBrainzId":"artist UUID"}` objects, matching [Lidarr CustomAPIResource](https://github.com/Lidarr/Lidarr/blob/develop/src/NzbDrone.Core/ImportLists/Custom/CustomAPIResource.cs) and [CustomImportProxy](https://github.com/Lidarr/Lidarr/blob/develop/src/NzbDrone.Core/ImportLists/Custom/CustomImportProxy.cs).

## Provenance and limitations

The supplied CSVs contained no verified IDs. IDs were retrieved from MusicBrainz artist searches; none were invented. Matching uses normalized names and aliases, genre tags, disambiguation descriptions, location clues, and recorded manual review decisions. Normalization ignores case, punctuation, and accents. The [MusicBrainz search API](https://musicbrainz.org/doc/MusicBrainz_API/Search/ArtistSearch) supports names and aliases.

The match report distinguishes automated name matches from context-based and manually reviewed matches. A sole search result is not an exhaustive proof of identity: batched search responses may be truncated and community data may be incomplete. These are evidence-backed best-effort matches, not a claim that every artist has been independently researched by hand. Uncertain cases and lookup failures are excluded and documented.

Jazz Air is the US free-jazz trio; electronic Air is the French electronic band. Jazz Carl Perkins is the pianist; rock Carl Perkins is the rockabilly performer. Lists are deduplicated by MusicBrainz ID, so multiple source aliases can resolve to one published entry. Genre membership otherwise follows the CSVs.

Validation checks the JSON schema, UUID syntax, uniqueness, and report counts. Published raw files are fetched and compared with the generated files. No live Lidarr instance was available for end-to-end import testing; a valid MusicBrainz ID does not guarantee that Lidarr’s metadata service currently supports the artist or all releases.

## Reports

- [Matched artists](reports/matched-artists.csv): source name, catalog name, ID, evidence URL, and match method.
- [Unresolved artists](reports/unresolved-artists.csv): exact omissions, reasons, and candidate identities.
- [Coverage](coverage.json): machine-readable list totals.
