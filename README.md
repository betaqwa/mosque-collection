# Mosque Collection — Malaysia

A structured dataset of masjid and surau across Malaysia, compiled from JAKIM directory data and geocoded using a multi-provider pipeline (Google Maps, Foursquare, LocationIQ, maps.co).

## Files

| File | Records | Description |
|---|---|---|
| `masjid.json` | 12,545 | Masjid (Friday-prayer mosques) across all 14 states and federal territories |
| `surau.json` | 27,533 | Surau (smaller prayer halls) across all 14 states and federal territories |

**Total: 40,078 places of worship**

## Data Fields

| Field | Type | Description |
|---|---|---|
| `name` | string | Name of the masjid or surau |
| `type` | string | `masjid` or `surau` |
| `address` | string\|null | Street address |
| `city` | string\|null | City or town (title case) |
| `postcode` | string\|null | 5-digit Malaysian postcode |
| `state` | string | Malaysian state or federal territory |
| `country` | string | `MY` |
| `latitude` | number | WGS84 latitude |
| `longitude` | number | WGS84 longitude |
| `zone` | string\|null | JAKIM prayer time zone |
| `phone` | string\|null | Contact number |
| `jemaah_capacity` | number\|null | Congregation capacity |
| `has_friday_prayer` | boolean | Whether Friday prayer (Jumaat) is held |
| `is_verified` | boolean | Whether the listing has been verified |
| `is_claimed` | boolean | Whether the masjid/surau has claimed its profile |
| `geocode_status` | string | `ok` for all rows in this dataset |

## Coverage

All 40,078 records have been geocoded (`geocode_status: ok`) with valid `latitude` and `longitude` coordinates. Postcode and city coverage:

- **Postcode**: ~93.7% filled (2,373 null — rural/remote locations with no structured postcode)
- **City**: ~99.9% filled (4 null)
- **Address**: ~99.98% filled (9 null — geocoded by POI name only, no address string available)

## States Covered

Johor, Kedah, Kelantan, Melaka, Negeri Sembilan, Pahang, Perak, Perlis, Pulau Pinang, Sabah, Sarawak, Selangor, Terengganu, W.P. Kuala Lumpur, W.P. Labuan, W.P. Putrajaya

## Geocode Pipeline

Data was geocoded using a 5-tier fallback pipeline:

1. Full name + address query
2. Address-only (cleaned)
3. Strip first address segment
4. Postcode-only
5. Name + state (for locations with no usable address)

Providers used in order of preference: Google Maps, Foursquare Places, LocationIQ, maps.co.

Postcode completion was further enhanced by cross-referencing against a Malaysia postcode reference dataset.

## Source

Original directory data sourced from JAKIM (Jabatan Kemajuan Islam Malaysia). Geocoding and data cleaning by [Betaqwa](https://github.com/betaqwa).

## License

Data is provided for reference and research purposes. Original JAKIM directory data remains the property of the Malaysian government.
