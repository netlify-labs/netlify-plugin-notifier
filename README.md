# Netlify notifier plugin

Send messages during different build lifecycle events

## Install

```
npm install @netlify/plugin-notifier
```

## Usage:

`notices` is an array of notices to send.

```yml
# in netlify.yml
plugins:
  - package: '@netlify/plugin-notifier'
    config:
      notices:
        - event: onPostBuild
          type: email
          to: david@netlify.com
          subject: Your site is ready!
          message: Yay!
        - event: onPostBuild
          type: sms
          to: 222-222-2222
          message: 'Your build is published!'
        - event: onError
          type: webhook
          endpoint: https://my-webhook-endpoint.com/api
          message: Your site build failed sorry charlie
```
