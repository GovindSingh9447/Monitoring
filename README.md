curl -XGET localhost:9200/_cat/indices
Delete logs by datewise.

curl -XDELETE localhost:9200/*13-03-2023
If wildcard issue comes when deletion elasticsearch indices on any project. Use above curl request.
curl --header "Content-Type: application/json" --request PUT --data '{ "transient": { "action.destructive_requires_name":false } }' http://localhost:9200/_cluster/settings
