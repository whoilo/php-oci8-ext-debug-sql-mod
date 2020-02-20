# OCI8 Extension SQL debug mod

This mod allows you to gather all the queries and send each via udp to your favourite stats collector

Add to php.ini:

```
oci8.debug_sql_enable=1
oci8.debug_sql_udp_host=127.0.0.1
oci8.debug_sql_udp_port=7778
```
where `127.0.0.1` is default host and `7778` is default port. You can change it at your own

### How to build and install

[See here](https://www.php.net/manual/en/oci8.installation.php)

### Debug string format
```
event_date_time|hash_value|sql_id|query_text|bind_vars_with_values|execution_time_in_ms|script_filename_with_lineno|sapi_name
```
`hash_value` and `sql_id` are intended to search query in library cache

Mod sends this string via udp on each `oci_execute` call

