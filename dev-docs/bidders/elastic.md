---
layout: bidder
title: ElasticBid
description: ElasticBid Prebid.js Bidder Adapter
biddercode: elastic
tcfeu_supported: true
dsa_supported: true
gpp_sids: tcfeu, usnat, usstate_all, usp
usp_supported: true
coppa_supported: true
schain_supported: true
floors_supported: true
media_types: banner, video
userIds: all
prebid_member: false
safeframes_ok: true
deals_supported: true
pbjs: true
pbs: false
pbs_app_supported: false
fpd_supported: true
ortb_blocking_supported: partial
gvl_id: 789
multiformat_supported: will-bid-on-one
privacy_sandbox: paapi, topics
sidebarType: 1
---

### Registration

For using the ElasticBid adapter, no prior setup is required. Contact the ElasticBid team at [support@elasticbid.com](mailto:support@elasticbid.com) for additional details or support.

### Bid Params

{: .table .table-bordered .table-striped }
| Name         | Scope              | Description                                         | Example                    | Type             |
|--------------|--------------------|-----------------------------------------------------|----------------------------|------------------|
| `placementId`| required           | Unique identifier for the ad placement             | `12345`                    | `string`         |

### Media Types

#### Banner

The ElasticBid adapter supports banner ads and accepts the following parameters:

- **Sizes**: Define the dimensions of the ad units.

Example configuration:
```javascript
var adUnits = [
  {
    code: 'test-banner-div',
    mediaTypes: {
      banner: {
        sizes: [[300, 250], [728, 90]],
      },
    },
    bids: [
      {
        bidder: 'elastic',
        params: {
          placementId: '12345', // Replace with valid test placement ID
        },
      },
    ],
  },
];
```
#### Video

The ElasticBid adapter supports video ads (instream only) and requires the following parameters:

{: .table .table-bordered .table-striped }
| Name            | Scope              | Description                                              | Example                  | Type          |
|-----------------|--------------------|----------------------------------------------------------|--------------------------|---------------|
| `context`       | required           | Must be `instream`                                       | `'instream'`             | `string`      |
| `playerSize`    | required           | Dimensions of the video player                          | `[640, 480]`             | `array`       |
| `mimes`         | required           | Supported video MIME types                              | `['video/mp4']`          | `array`       |
| `protocols`     | required           | Supported video protocols                               | `[2, 3, 5, 6]`           | `array`       |
| `playbackmethod`| optional           | Playback methods supported by the video player         | `[1, 2]`                 | `array`       |
| `omidpn`        | optional           | Open Measurement Initiative Partner Name               | `ElasticBid`             | `string`      |
| `omidpv`        | optional           | Open Measurement Initiative Partner Version            | `1.2.3`                  | `string`      |
| `linearity`     | required           | Indicates whether the ad is linear or non-linear       | `1`                      | `integer`     |
| `minduration`   | optional           | Minimum video ad duration in seconds                   | `5`                      | `integer`     |
| `maxduration`   | optional           | Maximum video ad duration in seconds                   | `30`                     | `integer`     |
| `startdelay`    | optional           | Indicates the start delay in seconds for ad placement  | `0`                      | `integer`     |
| `placement`     | optional           | Placement type of the video ad                         | `1` (Pre-roll)           | `integer`     |
| `plcmt`         | optional           | Plcmt type of the video ad                             | `1` (Pre-roll)           | `integer`     |
| `skip`          | optional           | Indicates if the ad can be skipped (1 for yes, 0 for no)| `1`                      | `integer`     |
| `skipafter`     | optional           | Seconds before skip is enabled (only applicable if skippable) | `5`               | `integer`     |
| `api`           | optional           | Supported API frameworks                                | `[2]`                    | `array`       |

Example configuration:
```javascript
var adUnits = [
  {
    code: 'test-video-div',
    mediaTypes: {
      video: {
        context: 'instream',
        playerSize: [[640, 480]],
        mimes: ['video/mp4'],
        protocols: [2, 3, 5, 6],
        playbackmethod: [1, 2],
        skip: 1,
        skipafter: 5,
        api: [2],
      },
    },
    bids: [
      {
        bidder: 'elastic',
        params: {
          placementId: '67890', // Replace with valid test placement ID
        },
      },
    ],
  },
];
```
### Notes

1. The ElasticBid adapter is compatible with GDPR, CCPA, and GPP compliance requirements.
2. Floors are supported for all media types, and floor prices can be dynamically retrieved via the `getFloor` method.
3. The ElasticBid adapter supports Open Measurement Initiative (OMID) parameters for enhanced ad verification.
4. Contact [support@elasticbid.com](mailto:support@elasticbid.com) for integration support, test credentials, and additional guidelines.
5. Ensure proper configuration of bid parameters to maximize bid request accuracy and demand match.

