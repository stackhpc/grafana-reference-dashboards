A collection of reference dashboards for control plane and tenant monitoring

Creating dashboards
-------------------

To prevent Grafana stripping out datasource names dashboards
should be downloaded via the API. This can be done via [curl](http://docs.grafana.org/tutorials/api_org_token_howto/#api-tutorial-how-to-create-api-tokens-and-dashboards-for-a-specific-organization),
or via a browser. In this case an example is given for a
browser.

In Grafana switch to the organisation in which the dashboard you
wish to save is located. Then in the same browser access the
dashboard via the API:

http://10.1.2.3:3000/api/dashboards/db/tenant-logs

This will return the dashboard as a JSON string. To allow the
dashboard to load successfully it is required to nullify the
dashboard id. For example:

```
<snip>
"dashboard":{
  "annotations":{"list":[]},
  "editable":true",
  "gnetId":null,
  "hideControls":false,
  "id":null,                               <-- Must be null
  "links":[],
  "rows": </snip>
```
