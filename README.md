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
