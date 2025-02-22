---
title: Admin API
category: api
permalink: /api/admin
---

Use this if you want to administer your account.

With this API you can do a few things, for example add websites to your dashboard. This API is only available on request because we want to know what the use case for the API will be. Just drop us a line via [our contact page](https://simpleanalytics.com/contact).

### List websites

> `GET` [https://simpleanalytics.com/api/websites](https://simpleanalytics.com/api/websites)

The only Admin API endpoint that is available for all plans.

```bash
curl "https://simpleanalytics.com/api/websites" \
     -H 'Content-Type: application/json' \
     -H 'Api-Key: sa_api_key_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx' \
     -H 'User-Id: sa_user_id_00000000-0000-0000-0000-000000000000'
```

Your user ID and API key are shown in [your account settings](https://simpleanalytics.com/account).

### Add a website

> `POST` [https://simpleanalytics.com/api/websites/add](https://simpleanalytics.com/api/websites/add)

<blockquote class="red">
  <p>For this endpoint you need a Business plan. You will be upgraded automatically when using this endpoint.</p>
</blockquote>

You can specify a time zone via `timezone` and set the website to public or private via the `public` boolean. [See wikipedia](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) for a list of valid time zones. If you don't specify a time zone we will set it to UTC.

```bash
curl -X "POST" "http://localhost:3000/api/websites/add" \
     -H 'Content-Type: application/json' \
     -H 'Api-Key: sa_api_key_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx' \
     -H 'User-Id: sa_user_id_00000000-0000-0000-0000-000000000000' \
     -d $'{
  "public": false,
  "hostname": "example.com",
  "timezone": "Europe/Amsterdam"
}'
```

### Custom endpoints

For bigger customers we make custom endpoints. If you are in the need of a custom endpoint, [let us know](https://simpleanalytics.com/contact).
