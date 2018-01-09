A collection of reference dashboards for control plane and tenant monitoring

Creating dashboards
-------------------

To prevent Grafana stripping out datasource names dashboards
should be downloaded via the API. This can be done via [curl](http://docs.grafana.org/tutorials/api_org_token_howto/#api-tutorial-how-to-create-api-tokens-and-dashboards-for-a-specific-organization),
or via a browser. It is recommended to use curl to maintain consistent formatting for diffs.

Download a dashboard via Curl
-----------------------------

By piping the output to json.tool it is easier to diff changes between dashboards.

Example command (you will need the grafana_admin password):

```
curl http://127.0.0.1:53000/api/dashboards/db/system-overview -u grafana_admin | python -m json.tool > system_overview.json
```

The dashboard id field must then be set to null, for example:

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
