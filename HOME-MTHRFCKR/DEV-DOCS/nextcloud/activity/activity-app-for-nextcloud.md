# nextcloud/activity: Activity app for Nextcloud

The activity app for Nextcloud

Provides an activity feed showing your file changes and other interesting things going on in your Nextcloud.

## 🏗 Development setup

  1. ☁ Clone this app into the `apps` folder of your Nextcloud: `git clone https://github.com/nextcloud/activity.git`
  2. ✅ Enable the app through the app management of your Nextcloud
  3. 🎉 Partytime!

## QA metrics on master branch:

![Build Status](https://camo.githubusercontent.com/b345a3164f0be949059cd6a572e804aaab8f1c36ff1a289d3670192b67c47c99/68747470733a2f2f7472617669732d63692e6f72672f6e657874636c6f75642f61637469766974792e7376673f6272616e63683d6d6173746572) ![Scrutinizer Code Quality](https://camo.githubusercontent.com/8eb3967c94e51fc1f53575486571c0a92852b8bbc8d6cb2cfaeadcdf791b8680/68747470733a2f2f7363727574696e697a65722d63692e636f6d2f672f6e657874636c6f75642f61637469766974792f6261646765732f7175616c6974792d73636f72652e706e673f623d6d6173746572) ![Code Coverage](https://camo.githubusercontent.com/834096c7348c8830a4a5b3409836c1db2436debbff18b08f674037a46a9d91c0/68747470733a2f2f7363727574696e697a65722d63692e636f6d2f672f6e657874636c6f75642f61637469766974792f6261646765732f636f7665726167652e706e673f623d6d6173746572)

## API for other apps to interact with activities

In Nextcloud 11 the old extension API was replaced by 3 new interfaces, to better split the functionality up. Documentation for each of those can be found in the `docs/` folder:

  * [Create](/nextcloud/activity/blob/master/docs/create.md) \- an activity and store it in the app
  * [Provider](/nextcloud/activity/blob/master/docs/provider.md) \- translate and render activities
  * [Setting](/nextcloud/activity/blob/master/docs/setting.md) \- allow users to control what they want to see in their stream or mail
  * [Filter](/nextcloud/activity/blob/master/docs/filter.md) \- allow to reduce the stream in the web UI by app or setting


___

#article 