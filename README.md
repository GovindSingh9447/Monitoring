curl --header "Content-Type: application/json" --request PUT --data '{ "transient": { "action.destructive_requires_name":false } }' http://localhost:9200/_cluster/settings
