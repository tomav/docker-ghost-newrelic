# docker-ghost-newrelic

This image is an extension of official Ghost image, adding built-in support for NewRelic agent.

Usage remains the same, and you can use `NEW_RELIC_*` [environment variables](https://docs.newrelic.com/docs/agents/nodejs-agent/installation-configuration/nodejs-agent-configuration#environment) to configure your agent.

### docker-compose example

```
production:
  image: tvial/docker-ghost-newrelic
  volumes:
  - .:/var/lib/ghost
  ports:
  - "2368:2368"
  environment:
    - NODE_ENV=production
    - NEW_RELIC_LICENSE_KEY=abcdefghijklmnopqrstuvwxyz
    - NEW_RELIC_APP_NAME=My Blog (Production)
    - NEW_RELIC_LOG=/tmp/newrelic_agent.log
```