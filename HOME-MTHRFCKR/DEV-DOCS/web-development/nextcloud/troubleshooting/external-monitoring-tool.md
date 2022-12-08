# External monitoring tool

You can connect an external monitoring tool by using this end point:

```https://cloud9.ctrlaltback.space/ocs/v2.php/apps/serverinfo/api/v1/info```

Appending "?format=json" at the end of the URL gives you the result in JSON.

To use an access token, please generate one then set it using the following command:
occ config:app:set serverinfo token --value yourtoken
Then pass the token with the "NC-Token" header when querying the above URL.