# docker-compose

Ready-to-run local development stacks. Each folder starts a datastore together with a web UI for it.

| Folder | Services | Ports |
|---|---|---|
| `elastic-search` | Elasticsearch 7.14 + Kibana | 9200, 9300, Kibana on 5601 |
| `mongo` | MongoDB 4.4 + mongo-express | 27017, UI on 127.0.0.1:8081 |
| `mysql` | MySQL + phpMyAdmin | 3306, UI on 8080 |
| `redis` | Redis + Redis Commander | 6379, UI on 8082 |
| `neo4j` | Neo4j (`start.sh`, plain `docker run`) | 7474 (browser), 7687 (bolt) |

## Usage

```bash
cd mongo            # or elastic-search, mysql, redis
docker compose up -d
docker compose down # stop
```

For Neo4j:

```bash
sh neo4j/start.sh
```

> **Local development only.** These stacks use default credentials (`root` / `admin`), have security disabled, and keep data in throwaway host folders under `/tmp`. Don't expose them on a public network.
