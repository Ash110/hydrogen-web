# FAQ

## Is there a way to run the app as a desktop app?

You can install Hydrogen as a PWA using Chrome/Chromium on any platform or Edge on Windows. Gnome Web/Ephiphany also allows to "Install site as web application". There is no Electron build of Hydrogen, and there will likely be none in the near future, as Electron complicates the release process considerably. Once Hydrogen is more mature and feature complete, we might reconsider and use [Tauri](https://tauri.studio) if there are compelling use cases not possible with PWAs. For now though, we want to keep development and releasing fast and nimble ;)

## Is feature X supported?

If you can't find an easy way to locate the feature you are looking for, then the anwser is usually "no, not yet" :) But here are some things people have asked about in the past:

### How does newline work? Shift+Enter has no effect.

That's not yet a feature, as hydrogen just uses a single line text box for message input for now.

### Hmm does Hydrogen not support leaving rooms? I left some rooms via Element and they moved to "Historical" but nothing happened on this end.

Indeed :) [Joining](https://github.com/vector-im/hydrogen-web/issues/28) and [leaving](https://github.com/vector-im/hydrogen-web/issues/147) isn't implemented yet, just haven't gotten around to it.

## How can I verify my session from Element?

You can only verify by comparing keys manually currently. In Element, go to your own profile in the right panel, click on the Hydrogen device and select Manually Verify by Text. The session key displayed should be the same as in the Hydrogen settings. You can't yet mark your Element session as trusted from Hydrogen.

## I want to host my own Hydrogen, how do I do that?

There are no published builds at this point. You need to checkout the version you want to build, or master if you want to run bleeding edge, and run `yarn init` and then `yarn build` in a console (and install nodejs > 14 and yarn if you haven't yet). Now you should find all the files needed to host Hydrogen in the `target/` folder, just copy them all over to your server. As always, don't host your client on the same [origin](https://web.dev/same-origin-policy/#what's-considered-same-origin) as your homeserver.

## I want to embed Hydrogen in my website, how should I do that?

There are no npm modules yet published for Hydrogen. The easiest is probably to setup your website project, do yarn/npm init if you haven't yet, then add the hydrogen repo as a git http dependency, and import the files/classes you want to use from Hydrogen. Feel free to ask which classes you need as the documentation is lacking somewhat still. Note that at this early, pre 1.0 stage of the project, there is no promise of API stability yet.
