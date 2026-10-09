This is a draft dataset in [the planning.data repository](https://digital-land.github.io/specification/dataset/local-plan-document-category/).

### Existing dataset

Typology: category

This dataset applies to:
- The topics a development policy can cover, such as housing, transport or design.
- Use this with development-policy to find policies on a topic. For example, all affordable housing policies.

| Field | Type | Cardinality | Required | Notes |
| ----- | ----- | ----- | ----- | ----- |
| `reference` | string | 1 | yes | e.g. `affordable-housing` |
| `name` | string | 1 | yes | e.g. "Affordable housing" |
| `notes` | text | 1 |  |  |
| `prefix` | string | 1 | yes |  |
| `entity` | integer | 1 | yes | Assigned by planning.data |
| `entry-date` | datetime | 1 | yes |  |
| `start-date` | datetime | 1 |  |  |
| `end-date` | datetime | 1 |  |  |

Current entries in the MHCLG dataset:
- `accessibility`
- `advertising`
- `affordable-housing`
- `aggregates`
- `air-quality`
- `allocated-sites`
- `allotments`
- `archaeology`
- `area-specific-policy`
- `arts`
- `aviation`
- `biodiversity`
- `broadband`
- `burial-spaces`
- `buses`
- `car-parks`
- `climate-change`
- `communications`
- `community-facilities`
- `community-infrastructure-levy`
- `compulsory-purchase-orders`
- `conservation-area`
- `construction`
- `contamination`
- `culture`
- `cycling`
- `density`
- `design`
- `designation`
- `development-management`
- `digital-infrastructure`
- `ecology`
- `economy`
- `education`
- `employment`
- `energy`
- `enforcement`
- `engagement`
- `equestrian-facilities`
- `existing-housing`
- `flooding`
- `freight`
- `green-belt`
- `gypsy-and-travellers`
- `health`
- `heritage`
- `highways`
- `housing`
- `housing-mix`
- `industry`
- `infrastructure`
- `jobs`
- `leisure`
- `lighting`
- `listed-building`
- `local-development-scheme`
- `mining`
- `monitoring`
- `nature`
- `neighbourhood-planning`
- `night-time-economy`
- `noise`
- `office`
- `open-space`
- `ownership`
- `parking`
- `play-space`
- `private-hire`
- `professional-and-financial-services`
- `public-transport`
- `rail`
- `regeneration`
- `rent`
- `residential-alterations`
- `retail`
- `retail-policy`
- `schools`
- `section-106`
- `servicing`
- `specialised-housing`
- `strategic-policy`
- `street-markets`
- `tourism`
- `town-centres`
- `tram`
- `transport`
- `trees`
- `use-class`
- `views`
- `walking`
- `waste`
- `water`
- `waterways`
- `world-heritage-sites`

Ended entries (have an `end-date`, so no longer in use):
- `other-commercial-development`
- `telecommunications`
- `coastal-change-management`
- `minerals-and-energy`
- `security`
- `area/location-specific-policy` (replaced by `area-specific-policy`)
- `conservation-natural-environment`
- `conservation-built-environment`
- `conservation-historic-environment`
- `flood-risk` (replaced by `flooding`)
- `waste-management`
- `water-supply`
- `wastewater`

## Scope for co-design

* Can these categories be used to categorise consultation questions as well as policies?
* Are any topics missing, or too broad or narrow to be useful?
* Would a specific local-plan-policy-category have any benefit?

### Referenced by
- `development-policy`, through its `development-policy-categories` field
