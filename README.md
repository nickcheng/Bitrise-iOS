Bitrise Client
---

# Features
- [x] Trigger Builds for a specific app
- [x] Apps List `GET /me/apps` (update on enterForeground)
- [x] Builds List `GET /apps/${APP-SLUG}` `GET /apps/${APP-SLUG}/builds`
  + [x] Show builds without paging
  + [x] Abort Button `POST /apps/${APP-SLUG}/builds/${BUILD-SLUG}/abort`
  + [ ] Poll interval 8sec for "new builds available message" for new builds
      - [ ] Tap message to show new builds
      - [ ] PullToRefresh to fetch new builds
  + [ ] Pagination
- [x] Show last app page on launch
- [ ] Trigger Build for each app
  + [ ] Cache workflowIDs
- [ ] Build Logs `GET /apps/${APP-SLUG}/builds/${BUILD-SLUG}/log`

# How to Build
## App Configuration

Set correct value in `configs/secret.xcconfig`.
This is ignored by git. (listed in .gitignore)

#### Required

- `TRIGGER_BUILD_APP_SLUG`
- `TRIGGER_BUILD_API_TOKEN`

#### Optional

- `TRIGGER_BUILD_WORKFLOW_IDS` ... whitespace separated

## Setup Carthage
Install the latest version of Carthage.
```
brew install carthage
```

Run following to build dependency frameworks.
```
carthage bootstrap --platform iOS --no-use-binaries
```

## Generate xcodeproj

Please install the latest XcodeGen on your own.
```
mint install yonaskolb/XcodeGen
```

Generate xcodeproj by running command below.
```
xcodegen
```

# License
MIT
