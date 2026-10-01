# Space Photos Assets

This repository contains the metadata assets (no media blobs) used by [Space Photos](https://space.ykvm.com/) as of 2026-10-01. The files mirror NASA’s APOD v1 responses, except for the `service_version` field (which has been removed).

## Important Notes
* The `service_version` property is absent in all files. Its value is always `v1` (string) so if you need it in your app, just declare a constant on your object after parsing the JSON.
* The following assets have been updated manually to add missing `url`s:
  * `2008-12-31`
  * `2009-06-29`
  * `2009-08-10`
  * `2010-01-20`
  * `2010-01-24`
  * `2010-05-10`
  * `2010-05-26`
  * `2010-06-08`
  * `2010-07-25`
  * `2010-08-25`
  * `2010-12-15`
  * `2011-01-23`
  * `2011-02-01`
  * `2011-02-22`
  * `2011-03-07`
  * `2014-02-10`
  * `2024-10-23`
  * `2025-03-24`
  * `2025-05-18`
  * `2025-05-19`
  * `2025-07-28`
  * `2025-08-11`
  * `2025-08-26`
* Many assets have been updated to use characters like `“` / `”`, `‘` / `’`, `—` (em dash), etc. where appropriate.
* Media URLs hosted at `apod.nasa.gov` will probably not work.

## Usage as a Static API
It should be possible to fetch individual photos directly from GitHub using links like `https://raw.githubusercontent.com/yakovmanshin/spacephotos-assets/refs/heads/main/assets/photos/2018-03-17.json`. You may want to use a fork, in case I delete this repo at some point.

## Media URLs
Media URLs at `apod.nasa.gov` will most likely not function, but it’s possible to construct URLs in the new format dynamically (though it’s effectively a guess).

Example (from [the asset above](https://raw.githubusercontent.com/yakovmanshin/spacephotos-assets/refs/heads/main/assets/photos/2018-03-17.json)):
1. Use the `hdurl` whenever available (e.g., `https://apod.nasa.gov/apod/image/1803/crab_lg.jpg`);
1. Replace `https://apod.nasa.gov/apod/image/` with `https://assets.science.nasa.gov/content/dam/science/cds/apod/apod/` (for the large image) or with `https://assets.science.nasa.gov/dynamicimage/assets/science/cds/apod/apod/` (for the dynamically resized one);
1. Expand the four-digit number into a year + month: `1803` becomes `2018/march`;
1. Keep the file name.

Result:
* Original image (`hdurl`): https://apod.nasa.gov/apod/image/1803/crab_lg.jpg
* Large image: https://assets.science.nasa.gov/content/dam/science/cds/apod/apod/2018/march/crab_lg.jpg
* Regular image (resized): https://assets.science.nasa.gov/dynamicimage/assets/science/cds/apod/apod/2018/march/crab_lg.jpg?w=1280&h=800 (notice that I request 1280 × 800 but the response is 1232 × 800)
* The `url` value from the asset (`https://apod.nasa.gov/apod/image/1803/crab_lg1024.jpg`) is effectively not used
