This script is a client of StatsRIPE, which comes from `[RIPE Atlas docs | RIPEstat Data API | Docs](https://stat.ripe.net/docs/02.data-api/)`

The origin code is comes from BGPRanking([BGP-Ranking/statsripe.py at master · D4-project/BGP-Ranking · GitHub](https://github.com/D4-project/BGP-Ranking/blob/master/bgpranking/libs/statsripe.py)), I add some features into it, such as 

```python
    # response = ripe.country_asns(country, query_time=datetime.today().date(), details=1)
    # response = ripe.ris_prefixes(4538, query_time=datetime.today().date())
    # response = ripe.network_info("8.8.8.8")
    # response = ripe.Reverse_DNS_IP("8.8.8.8")
    # response = ripe.AS_info(1)
    response = ripe.Search("AS12876")
    # response = ripe.Atlas_Probes("AS4538")
    # response = ripe.prefix_overview("109.0.0.0/11")
    print(response["data"])
   
```
example for `Search AS12876` showed below.
```json
{
    'categories': [{
        'category': 'ASNs',
        'suggestions': [{
            'label': 'AS12876',
            'value': 'AS12876',
            'description': 'Online SAS, FR'
        }]
    }, {
        'category': 'Related Resources',
        'suggestions': [{
            'value': '212.83.128.0/19',
            'label': '212.83.128.0/19',
            'description': 'Recently announced by AS12876'
        }, {
            'value': '51.158.128.0/17',
            'label': '51.158.128.0/17',
            'description': 'Recently announced by AS12876'
        }, {
            'value': '2001:bc8:1800::/38',
            'label': '2001:bc8:1800::/38',
            'description': 'Recently announced by AS12876'
        }, {
            'label': 'AS7447',
            'value': 'AS7447',
            'description': 'ONLINEINTERACTIVE, US  -- Note: Possibly related to as12876'
        }, {
            'label': 'AS11115',
            'value': 'AS11115',
            'description': 'ONLINE-TECH-LLC, US  -- Note: Possibly related to as12876'
        }, {
            'label': 'AS13857',
            'value': 'AS13857',
            'description': 'ONLINEMAC, US  -- Note: Possibly related to as12876'
        }]
    }],
    'query_term': 'as12876',
    'limit': 6,
    'query_time': '2022-04-15T09:00:00'
}
```
