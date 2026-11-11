# azure-databricks-automation-pat-01

#There are two types of access tokens which can be used. There is the personal access token, and there are also Azure Active Directory tokens


curl -X GET "$DATABRICKS_HOST/api/2.0/clusters/list" \
  -H "Authorization: Bearer $DATABRICKS_TOKEN" | jq .

curl -X GET "$DATABRICKS_HOST/api/2.0/clusters/create" \
  -H "Authorization: Bearer $DATABRICKS_TOKEN" | jq .

curl -X GET "$DATABRICKS_HOST/api/2.0/policies/clusters/list" \
  -H "Authorization: Bearer $DATABRICKS_TOKEN" | jq .


 

curl -X POST "$DATABRICKS_HOST/api/2.1/jobs/run-now" \
  -H "Authorization: Bearer $DATABRICKS_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "job_id": 45678,
    "notebook_params": {
      "dry_run": "true",
      "start_date": "2026-08-27"
    }
  }'  






https://learn.microsoft.com/en-gb/azure/databricks/dev-tools/rest-api
