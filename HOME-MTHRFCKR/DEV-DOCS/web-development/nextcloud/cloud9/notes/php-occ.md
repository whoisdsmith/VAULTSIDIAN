---
tags:: notes
---
# Php OCC

elnulqmy@ctrlaltback.space [~/public_html/cloud9-ctrlaltback-space]# php occ list --format=txt
CLOUD9 24.0.1

Usage:
  command [options] [arguments]

Options:
  -h, --help            Display this help message
  -q, --quiet           Do not output any message
  -V, --version         Display this application version
      --ansi            Force ANSI output
      --no-ansi         Disable ANSI output
  -n, --no-interaction  Do not ask any interactive question
      --no-warnings     Skip global warnings, show command output only
  -v|vv|vvv, --verbose  Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

Available commands:
  aria2                                  Aria2 hooks
  check                                  check dependencies of the server environment
  help                                   Display help for a command
  list                                   List commands
  status                                 show some status information
  upgrade                                run upgrade routines after installation of a new release. The release has to be installed before.
 activity
  activity:send-mails                    Sends the activity notification mails
 analytics
  analytics:load                         execute a dataload
 app
  app:check-code                         check code to be compliant
  app:disable                            disable an app
  app:enable                             enable an app
  app:getpath                            Get an absolute path to the app directory
  app:install                            install an app
  app:list                               List all available apps
  app:remove                             remove an app
  app:update                             update an app or all apps
 audioplayer
  audioplayer:reset                      reset audio player library
  audioplayer:scan                       scan for new audio files; use -v for debugging
 background
  background:ajax                        Use ajax to run background jobs
  background:cron                        Use cron to run background jobs
  background:webcron                     Use webcron to run background jobs
 background-job
  background-job:execute                 Execute a single background job manually
 broadcast
  broadcast:test                         test the SSE broadcaster
 circles
  circles:check                          Checking your configuration
  circles:maintenance                    Clean stuff, keeps the app running
  circles:manage:config                  edit config/type of a Circle
  circles:manage:create                  create a new circle
  circles:manage:destroy                 destroy a circle by its ID
  circles:manage:details                 get details about a circle by its ID
  circles:manage:edit                    edit displayName or description of a Circle
  circles:manage:join                    emulate a user joining a Circle
  circles:manage:leave                   simulate a user joining a Circle
  circles:manage:list                    listing current circles
  circles:manage:setting                 edit setting for a Circle
  circles:members:add                    Add a member to a Circle
  circles:members:details                get details about a member by its ID
  circles:members:level                  Change the level of a member from a Circle
  circles:members:list                   listing Members from a Circle
  circles:members:remove                 remove a member from a circle
  circles:members:search                 Change the level of a member from a Circle
  circles:memberships                    index and display memberships for local and federated users
  circles:remote                         remote features
  circles:shares:files                   listing shares files
  circles:sync                           Sync Circles and Members
  circles:test                           testing some features
 config
  config:app:delete                      Delete an app config value
  config:app:get                         Get an app config value
  config:app:set                         Set an app config value
  config:import                          Import a list of configs
  config:list                            List all configs
  config:system:delete                   Delete a system config value
  config:system:get                      Get a system config value
  config:system:set                      Set a system config value
 dav
  dav:create-addressbook                 Create a dav addressbook
  dav:create-calendar                    Create a dav calendar
  dav:delete-calendar                    Delete a dav calendar
  dav:list-calendars                     List all calendars of a user
  dav:move-calendar                      Move a calendar from an user to another
  dav:remove-invalid-shares              Remove invalid dav shares
  dav:retention:clean-up                 
  dav:send-event-reminders               Sends event reminders
  dav:sync-birthday-calendar             Synchronizes the birthday calendar
  dav:sync-system-addressbook            Synchronizes users to the system addressbook
 db
  db:add-missing-columns                 Add missing optional columns to the database tables
  db:add-missing-indices                 Add missing indices to the database tables
  db:add-missing-primary-keys            Add missing primary keys to the database tables
  db:convert-filecache-bigint            Convert the ID columns of the filecache to BigInt
  db:convert-mysql-charset               Convert charset of MySQL/MariaDB to use utf8mb4
  db:convert-type                        Convert the Nextcloud database to the newly configured one
 duplicates
  duplicates:clear                       Clear all duplicates and information for discovery
  duplicates:find-all                    Find all duplicates files
  duplicates:list                        List all duplicates files
 encryption
  encryption:change-key-storage-root     Change key storage root
  encryption:decrypt-all                 Disable server-side encryption and decrypt all files
  encryption:disable                     Disable encryption
  encryption:enable                      Enable encryption
  encryption:encrypt-all                 Encrypt all files for all users
  encryption:list-modules                List all available encryption modules
  encryption:migrate-key-storage-format  Migrate the format of the keystorage to a newer format
  encryption:set-default-module          Set the encryption default module
  encryption:show-key-storage-root       Show current key storage root
  encryption:status                      Lists the current status of encryption
 federation
  federation:sync-addressbooks           Synchronizes addressbooks of all federated clouds
 files
  files:cleanup                          cleanup filecache
  files:recommendations:recommend        
  files:repair-tree                      Try and repair malformed filesystem tree structures
  files:scan                             rescan filesystem
  files:scan-app-data                    rescan the AppData folder
  files:transfer-ownership               All files and folders are moved to another user - outgoing shares and incoming user file shares (optionally) are moved as well.
 group
  group:add                              Add a group
  group:adduser                          add a user to a group
  group:delete                           Remove a group
  group:info                             Show information about a group
  group:list                             list configured groups
  group:removeuser                       remove a user from a group
 integrity
  integrity:check-app                    Check integrity of an app using a signature.
  integrity:check-core                   Check integrity of core code using a signature.
  integrity:sign-app                     Signs an app using a private key.
  integrity:sign-core                    Sign core using a private key.
 l10n
  l10n:createjs                          Create javascript translation files for a given app
 log
  log:file                               manipulate logging backend
  log:manage                             manage logging configuration
  log:tail                               Tail the nextcloud logfile
  log:watch                              Watch the nextcloud logfile
 mail
  mail:account:create                    creates IMAP account
  mail:account:delete                    Delete an IMAP account
  mail:account:diagnose                  Diagnose a user's IMAP connection
  mail:account:export                    Exports a user's IMAP account(s)
  mail:account:export-threads            Exports a user's account threads
  mail:account:sync                      Synchronize an IMAP account
  mail:account:train                     Train the classifier of new messages
  mail:clean-up                          clean up all orphaned data
  mail:repair:tags                       Create default tags for account. If no account ID given, all tag entries will be repaired
  mail:tags:migration-jobs               Creates a background job entry in the cron table for every user to migrate important labels to IMAP
  mail:thread                            Build threads from the exported data of an account
 maintenance
  maintenance:data-fingerprint           update the systems data-fingerprint after a backup is restored
  maintenance:mimetype:update-db         Update database mimetypes and update filecache
  maintenance:mimetype:update-js         Update mimetypelist.js
  maintenance:mode                       set maintenance mode
  maintenance:repair                     repair this installation
  maintenance:theme:update               Apply custom theme changes
  maintenance:update:htaccess            Updates the .htaccess file
 music
  music:cleanup                          clean up orphaned DB entries (this happens also periodically on the background)
  music:playlist-export                  export user playlist(s) to file(s)
  music:playlist-import                  import user playlist(s) from file(s)
  music:podcast-add                      add a podcast channel from an RSS feed
  music:podcast-reset                    remove all podcast channels of one or more users
  music:podcast-update                   update podcast channels of one or more users from their sources
  music:reset-cache                      drop data cached by the music app for performance reasons
  music:reset-database                   drop metadata indexed by the music app (artists, albums, tracks, playlists)
  music:scan                             scan and index any unindexed audio files
 notification
  notification:generate                  Generate a notification for the given user
  notification:test-push                 Generate a notification for the given user
 notify_push
  notify_push:log                        Temporarily set the log level of the push server
  notify_push:metrics                    Get the metrics from the push server
  notify_push:reset                      Cancel all active connections to the push server
  notify_push:self-test                  Run self test for configured push server
  notify_push:setup                      Configure push server
 preview
  preview:generate-all                   Generate previews
  preview:pre-generate                   Pre generate previews
  preview:repair                         distributes the existing previews into subfolders
  preview:reset-rendered-texts           Deletes all generated avatars and previews of text and md files
 root_cache_cleaner
  root_cache_cleaner:clean               Clean duplicate items from the root filecache
 security
  security:bruteforce:reset              resets bruteforce attemps for given IP address
  security:certificates                  list trusted certificates
  security:certificates:import           import trusted certificate in PEM format
  security:certificates:remove           remove trusted certificate
 serverinfo
  serverinfo:update-storage-statistics   Triggers an update of the counts related to storages used in serverinfo
 sharing
  sharing:cleanup-remote-storages        Cleanup shared storage entries that have no matching entry in the shares_external table
  sharing:expiration-notification        Notify share initiators when a share will expire the next day.
 tag
  tag:add                                Add new tag
  tag:delete                             delete a tag
  tag:edit                               edit tag attributes
  tag:list                               list tags
 talk
  talk:active-calls                      Allows you to check if calls are currently in process
  talk:command:add                       Add a new command
  talk:command:add-samples               Adds some sample commands: /wiki, …
  talk:command:delete                    Remove an existing command
  talk:command:list                      List all available commands
  talk:command:update                    Add a new command
  talk:room:add                          Adds users to a room
  talk:room:create                       Create a new room
  talk:room:delete                       Deletes a room
  talk:room:demote                       Demotes participants of a room to regular users
  talk:room:promote                      Promotes participants of a room to moderators
  talk:room:remove                       Remove users from a room
  talk:room:update                       Updates a room
  talk:signaling:add                     Add an external signaling server.
  talk:signaling:delete                  Remove an existing signaling server.
  talk:signaling:list                    List external signaling servers.
  talk:stun:add                          Add a new STUN server.
  talk:stun:delete                       Remove an existing STUN server.
  talk:stun:list                         List STUN servers.
  talk:turn:add                          Add a TURN server.
  talk:turn:delete                       Remove an existing TURN server.
  talk:turn:list                         List TURN servers.
  talk:user:remove                       Remove a user from all their rooms
 text
  text:reset                             Reset a text document
 theming
  theming:config                         Set theming app config values
 trashbin
  trashbin:cleanup                       Remove deleted files
  trashbin:expire                        Expires the users trashbin
  trashbin:restore                       Restore all deleted files
  trashbin:size                          Configure the target trashbin size
 twofactorauth
  twofactorauth:cleanup                  Clean up the two-factor user-provider association of an uninstalled/removed provider
  twofactorauth:disable                  Disable two-factor authentication for a user
  twofactorauth:enable                   Enable two-factor authentication for a user
  twofactorauth:enforce                  Enabled/disable enforced two-factor authentication
  twofactorauth:state                    Get the two-factor authentication (2FA) state of a user
 update
  update:check                           Check for server and app updates
 usage-report
  usage-report:generate                  Prints a CSV entry with some usage information of the user:
userId,date,assignedQuota,usedQuota,numFiles,numShares,numUploads,numDownloads
"admin","2017-09-18T09:00:01+00:00",5368709120,786432000,1024,23,1400,5678
 user
  user:add                               adds a user
  user:add-app-password                  Add app password for the named user
  user:delete                            deletes the specified user
  user:disable                           disables the specified user
  user:enable                            enables the specified user
  user:export                            Export a user.
  user:import                            Import a user.
  user:info                              show user info
  user:lastseen                          shows when the user was logged in last time
  user:list                              list configured users
  user:report                            shows how many users have access
  user:resetpassword                     Resets the password of the named user
  user:setting                           Read and modify user settings
 versions
  versions:cleanup                       Delete versions
  versions:expire                        Expires the users file versions
 workflows
  workflows:list                         Lists configured workflows