# Electronic artist expansion

Published snapshot: 19 November 2026. 7952 unique MusicBrainz artist IDs; 7624 additions to the original 328. The existing raw URL is unchanged.

## Scope and evidence

MusicBrainz artist search returned 8000 records across 16 UUID-prefix partitions. 7851 unique records had at least one positive community tag from the [search vocabulary](reports/electronic-search-tags.json), excluding special Various Artists/no-artist entities. All original IDs are retained. Each added ID is taken directly from a returned MusicBrainz artist record; no IDs were fabricated or inferred from artist names. [Evidence report](reports/electronic-expansion.csv) lists names, IDs, matching tags, original-list membership and identity disambiguation.

Coverage includes early electroacoustic and musique concrète, synth music, house, techno, trance, bass music, industrial, chiptune, regional dance styles, plunderphonics and mashups. This is intentionally broad: experimental, pop, rock and other crossover artists can qualify. A positive community tag is evidence of association, not proof that an artist works exclusively in electronic music. Records have not each received manual biographical review. Remixes are not selected individually: a Lidarr artist list imports artists, and your monitoring settings determine releases.

## Exact collection limitations

The union searches reported 44029 results across the 16 partitions, but only the first 500 records from each partition were retrieved (8000 total). Offset 500 failed after four attempts in 15 recorded partitions; the final partition has no recorded completion beyond offset 400. See the [page-level search log](reports/electronic-search-status.json). The unretrieved results are not resolved or published by this expansion, and the reported search total includes records that may fail the positive-tag filter. This snapshot is not a complete catalog of electronic music history or of the chosen search results. Untagged artists, missing MusicBrainz artists, and alternate aliases may be absent.

The original unresolved electronic CSV terms, Ninja Tune (a label) and Vaporwave (a genre), remain excluded as artist identities. Vaporwave is included as a discovery tag. No invented artist IDs were assigned to either term.

## Youngstown connections

Existing verified entries include Gil Mantera’s Party Dream, Dan Curtin, Lady Miss Kier and Crankdat. Gil Mantera’s Party Dream describes itself as a Youngstown electronic synthpop band on its [official site](https://partydream.com/). Connections should distinguish local formation, birthplace and regional association; they do not mean every act formed in Youngstown.

Further leads from the research include [MUNNYCAT](https://www.munnycat.com/) (originally Youngstown, now Los Angeles) and [Unshore](https://unshore.bandcamp.com/) (Youngstown experimental/lo-fi producer). No additional MusicBrainz identity was resolved for these leads during this publication. The local scene research and early-pioneer/mashup manual checks remain incomplete.

## Validation

JSON shape, UUID syntax, uniqueness, and preservation of all original 328 IDs are checked locally. Raw publication is fetched and compared after pushing. No live Lidarr instance was tested. MusicBrainz catalog presence does not guarantee support in Lidarr’s metadata service.
