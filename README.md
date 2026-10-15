# Taiwan Election-Day Events Watch — raw data (edition 1: 2026-11-28)
### 台灣投票日演出觀測 — 原始資料（第一期：115年地方公職人員選舉）

**[中文說明 → README.zh-TW.md](README.zh-TW.md)**

This repository is a **raw open-data release**. It contains the events listed for Taiwan's polling day on
**Saturday 28 November 2026** (local elections and a national referendum), the companies credited for those events, and
those companies' shareholders and directors as recorded in Taiwan's company registry, together with the dates, raw listings,
news reports and per-event detail for national polling days since 2016, and political-donation register extracts for
the credited companies' groups (no party labels). **It contains no analysis**: no classification of companies, no fact-checks, no comparisons and no
conclusions. Those appear only on the author's web page, <https://www.samyip.net/tw-election-day-events/>, which is not
part of this release.

Status: **pre-publication data release (0.3.0-draft)**. The data are part of ongoing research and will be cited in a
forthcoming paper. Values may be corrected in later versions; see `CHANGELOG.md`.

## Files (`data/`)

| File | Rows | Content | Primary sources |
|---|---|---|---|
| `events_20261128.csv` | 14 | Events on 2026-11-28: title, artists, venue, city, start time, source page | Ticketing platforms and official pages (one URL per event; `source_type` = official / social) |
| `event_credits_20261128.csv` | 37 | Every organiser, co-organiser, producer and sponsor credit **as printed**, with the matched legal entity and tax ID where established | The same pages |
| `entities_registry.csv` | 24 | Registry facts for the credited Taiwan companies and their parents: legal name, tax ID, type, listing, 股權狀況 (equity status: 僑外資 = foreign / overseas-Chinese investment; blank = not marked), capital, representative, address, dates | Ministry of Economic Affairs company registry (findbiz; one record from the GCIS open-data API) |
| `entity_holdings.csv` | 61 | Directors, supervisors, managers and their registered holdings, with the corporate holder they represent | Same registry pages |
| `polling_days.csv` | 9 | National polling days 2016–2026 | Central Election Commission dates |
| `past_polling_day_listings.csv` | 420 | Event titles listed on past polling days and on the four Saturdays either side | Venue calendars (Legacy, Taipei Music Center, Kaohsiung Music Center), ticketing catalogues, zh.wikipedia list of Taipei Arena concerts |
| `past_polling_day_news_reports.csv` | 95 | Dated show reports for those days | ETtoday entertainment news lists, retrieved via the Internet Archive Wayback Machine |
| `past_polling_day_events_detail.csv` | 90 | Per-event detail for past polling days (venue, stated organiser, source) | Wikipedia list, archived ticketing pages, 2026 census |
| `political_donations_company_records.csv` | 41 | Political-donation register rows for companies in the credited companies' groups (donor, recipient, election, date, amount, record ID). **No party labels are given.** | Control Yuan political-donation register (ardata.cy.gov.tw) |

## Notes on the data
- **Registry data** were captured from the public findbiz pages on 2026-10-15 and are reproduced as shown. They include the
  names of directors and supervisors, which the registry publishes. A blank `equity_status` means the registry page shows
  no 股權狀況 row; on the pages captured, the row appears only for foreign / overseas-Chinese (僑外資) or PRC (陸資)
  investment. None of the captured companies is marked 陸資.
- **Holdings**: when several directors represent the same corporate shareholder, the holding is repeated on each row and
  must be counted once. For 有限公司 (limited companies) the registry shows only directors, so holdings may not sum to 100%.
- **Credits**: `legal_entity_matched` is blank where the legal entity behind a printed name could not be established.
- **Donations**: rows are register extracts. Recipients' party affiliations are not given, because they could not be
  verified for every recipient at the time of donation.
- **Listings** are titles as listed. Duplicates across sources are kept, one row per (date, title, source).

## Citation
Yip, Kam-lung Sam (2026). *台灣投票日演出觀測 Taiwan Election-Day Events Watch — raw data, edition 1* (0.3.0-draft).
DOI: see the Zenodo record. Web page: <https://www.samyip.net/tw-election-day-events/>

## Author, funding, AI use
- **Author:** Kam-lung Sam Yip (葉錦龍), Visiting Researcher, Center for Asian Studies, Kanagawa University. ORCID
  [0009-0006-3813-636X](https://orcid.org/0009-0006-3813-636X).
- **Funding:** part of the output of the Kanagawa University Center for Asian Studies FY2026 Individual Research Incentive Grant
  (個別奨励研究助成), *The Development and Transformation of Japan's Content Business in East Asia: A Comparative Area Study of Hong Kong, Taiwan, and Mainland China* (「東アジアにおける日本コンテンツ事業の展開と変容――香港・台湾・中国大陸を対象とした比較地域研究」).
- **AI use:** compiled with the assistance of Anthropic's Claude models (via Claude Code) for data collection, structuring
  and consistency checks. The author verifies the data against the cited sources before each version is finalised.
- **Conflict of interest:** the author has worked since 2009 as a concert promoter for Japanese and Korean artists in East
  and Southeast Asia, took no part in any event listed here, and has had no business dealings with the credited
  organisers or co-organisers in the past five years.

## Licence
Compiled data: **CC BY 4.0** (`LICENSE`). Upstream sources keep their own terms; see `LICENSE-CONTENT.md`.
Corrections: open an issue, or use the form on the web page.
