---
layout: bidder
title: SpinX
description: SpinX Adaptor
biddercode: spinx
pbjs: true
pbs: false
media_types: banner, native, video
gvl_id: 1308
tcfeu_supported: true
gpp_sids: tcfeu, usp
usp_supported: true
coppa_supported: true
pbs_app_supported: false
schain_supported: true
userIds: all
fpd_supported: true
prebid_member: false
ortb_blocking_supported: true
multiformat_supported: will-bid-on-one
floors_supported: true
aliasCode: adkernel
sidebarType: 1
---

### Note

The SpinX bidding adapter requires setup and approval before implementation. Please reach out to <support@spinx.biz> for more details.

### Bid Params

{: .table .table-bordered .table-striped }
| Name     | Scope    | Description           | Example                   | Type     |
|----------|----------|-----------------------|---------------------------|----------|
| `host`   | required | RTB host | `'cpm.arteabee.com'` | `string` |
| `zoneId` | required | Zone Id           | 30164                 | `integer` |
