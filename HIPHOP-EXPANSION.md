# Hip-Hop expansion

Snapshot: 19 November 2026. **7952 unique MusicBrainz artist IDs**, adding **7761** to the original 191. The existing `HipHop Artists.json` URL is unchanged.

## Focused listening

The main list combines the original CSV, positive MusicBrainz genre-tag matches, and reviewed named candidates. Two optional subsets are published in `focused/`: **79 Early and Golden Age artists** and **5 Youngstown Ohio artists**. Both are subsets of the main list. The early selection is curated from named candidates, not inferred from a person's birth date or a band's formation date. It includes pioneers and familiar reference points alongside obscure artists; it is not a claim that every selected act is obscure.

Early research used Soul Jazz's [Boombox 2](https://soundsoftheuniverse.com/product/ejyybbqmn), the [Yo! Boombox track listing](https://www.hhv.de/en-GB/records/item/soul-jazz-records-presents-yo-boombox-hip-hop-electro-disco-rap-1979-83-1004136), the [Smithsonian anthology](https://folkways.si.edu/smithsonian-anthology-of-hip-hop-and-rap-intl), and additional sources recorded per candidate. Representative deep cuts include Lonnie Love, MC Rock Lovely, Margo’s Kool Out Crew, Eye Beta Rock, Funky Constellation, Just Four, and the Carver Area High School Seniors. Historical sources informed the candidate selection; they do not each contain every candidate listed.

## Youngstown connections

| Artist | Connection | Evidence |
|---|---|---|
| Rufus Blaq | native | [Source](https://www.worldradiohistory.com/Archive-All-Music/Gavin-Report/90/98/Gavin-Report-1998-03-27.pdf) |
| MC Homeless | grew up locally | [Source](https://tripleeyeindustries.com/artists/mc-homeless/) |
| 2d6 | artist-listed home base | [Source](https://2d6music.bandcamp.com/) |
| Kenny Ali | local MC | [Source](https://vindyarchives.com/news/2008/sep/06/rapper-ali-has-high-hopes-for-new-cd/) |
| Pryslezz | native | [Source](https://vindyarchives.com/news/2008/jun/05/youngstown-native-climbs-hip-hop-charts/) |

A city connection is established separately from the MusicBrainz identity. Performing a concert in Youngstown alone does not establish local origin. 2d6's MusicBrainz profile links directly to the cited Bandcamp page; Rufus Blaq's catalog includes Credentials; Kenny Ali's catalog credits Return of the MC, corroborated by [Kool G Rap's official Bandcamp](https://theofficialkoolgrap.bandcamp.com/album/genius-of-rap). MC Homeless and Pryslezz were already in the original list. Pryslezz’s catalog includes Leaning Sideways, also credited on [Jason Derulo’s official music page](https://www.jasonderulo.com/music/); his earlier Sideways collaboration is documented by [DJBooth](https://djbooth.net/songs/pryslezz-ft-jason-derulo-and-nox-sideways/).

Unresolved local research candidates: **Crookit, KeilyN, Baker, Lethal FX, DJ Ludo, Unc Doe, FreeLance, Ya Boi TC, fredcrewneck, Lucky Penny, Senial, Dice Dimension, Mista Shyce, 2Fly, Da Kreek, DidDat, Droege, Throwback**. These names were not assigned speculative IDs. The research report records exact outcomes and returned candidate IDs. In particular, the available US rapper Throwback links to Kansas City profiles rather than Jonathon Tepper; Lucky Penny's returned rap catalog was not tied to the documented Youngstown releases; KeilyN has an exact-name record with guest credits on SoulKlap’s Klapback EP, but that catalog record could not be independently tied to the Youngstown artist. These are lookup/identity limitations, not claims that the artists do not exist.

## Collection method and coverage

The [tag vocabulary](reports/hiphop-search-tags.json) targets old-school/golden-age rap, boom bap, underground, jazz rap, conscious, alternative, hardcore and political hip-hop. It intentionally includes modern and international artists in those traditions. Each automated addition has at least one positive matching community tag on its MusicBrainz artist record. No score-only or fabricated-ID matches are used. Tags are community metadata, not independent proof that every release fits a genre.

Queries are partitioned by MusicBrainz ID prefix, splitting partitions larger than 500 results to keep offsets below 500. The [page log](reports/hiphop-search-status.json) records 7892 retrieved records, 7892 reported results among recorded leaf partitions, and 0 failed page/partition requests. 7797 unique records passed the positive-tag filter. Search data can change during collection. Even a fully retrieved tag query is not a complete history of hip-hop: untagged, uncataloged, alias-only or poorly documented acts can be missing.

Named research reviewed 107 candidates: 85 resolved source names and 22 unresolved names, with aliases deduplicated by ID. Four early candidates require further work: Terry Lewis and Wild Flower, Silver Star, Grandmaster Flowers and Disco King Mario. The returned Silver Star ID describes a British DJ rather than the early US act; it was not used for that identity. Named matches use catalog names/aliases, disambiguation, relevant releases and linked profiles where available. Not every broad tag-selected artist has been manually researched.

## Using the lists

Paste a raw JSON URL into Lidarr's Custom List URL field. The format is an array of `{"MusicBrainzId":"artist UUID"}` objects. These lists select artists, not individual tracks or only early releases; monitoring settings govern which releases Lidarr imports. The focused lists are useful if the full list is broader than your intended library.

All 191 original IDs are preserved; UUID format, uniqueness, subset membership, report counts and JSON shape are checked. Public raw files are fetched and compared after publication. No live Lidarr import was tested; metadata-service coverage can differ from MusicBrainz. Other genre lists are unchanged.
