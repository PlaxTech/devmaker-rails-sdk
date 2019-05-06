# DevmakerRailsSdk
Bunch of helper code for your DevMaker Rails project

# Todo
- Move the push notification class (and its `fcm` gem dependency) to a new gem (does not need to be an engine)
  - add the whole user device database and mutations
- Move the GQL specific stuff to a single gem

## Usage

## Installation
Add this line to your application's Gemfile:
```ruby
gem "devmaker_rails_sdk", git: "https://gitlab.com/devmaker-mobile-apps/rails/devmaker-rails-sdk.git"
```

You need to have access to this private gitlab repo from your gitlab account.

So you give bundler an user and password. This is the command:
```bash
bundle config gitlab.com GitLabUsername:GITLAB_PASSWORD
```

And then execute:
```bash
$ bundle
```

## Whats is included?

- Class to send push notification to firebas (using the FCM gem)
- [`DevmakerRailsSdk::GraphqlControllerMixin`](app/controllers/devmaker_rails_sdk/graphql_controller_mixin.rb) is a controller mixin to handle GraphQL requests
- A bunch of common GraphQL Types and Mixins usefull in many project... (see [app/graphql](app/graphql)

## Deploy an app using this private gem:
On heroku, use the `@devmaker-ci-cd` gitlab user to access, you need to set it as an ENV var:
```bash
heroku config:set BUNDLE_GITLAB__COM=devmaker-ci-cd:THE_SUPER_SECRET_PASSWORD
```