# SpiderFoot Docs

---

## Running SpiderFoot

To run SpiderFoot, simply execute `sf.py` from the directory you extracted/pulled SpiderFoot into. Ensure you’re using Python 3; on some Linux distributions `python` is Python 2.7, so best to be explicit and use `python3`:

```
~/spiderfoot$ python3 sf.py
Attempting to verify database and update if necessary...
You must specify a target when running in scan mode. Try --help for guidance.
```

This is telling you that you’re missing command-line arguments, because SpiderFoot doesn’t know whether you want to run it in scan mode, or in Web UI mode.

Use **Web UI mode** when you want to have SpiderFoot run with its built-in web server, enabling you to run scans, browse data and manage configuration via a web browser. Web UI mode also enables you to drive SpiderFoot using `sfcli.py` in a client/server model.

Use **scan mode** when you just want to have SpiderFoot fire off a scan and parse the results as output. No web server is started in this mode.

### Web UI Mode

To start SpiderFoot in Web UI mode, you need to tell it what IP and port to listen to. The below example binds SpiderFoot to localhost (127.0.0.1) on port 5001:

```
~/spiderfoot$ python3 sf.py -l 127.0.0.1:5001
```

Once executed, a web-server will be started, which will listen on 127.0.0.1:5001. You can then use the web-browser of your choice by browsing to https://127.0.0.1:5001. Or, since version 2.10 you can use the CLI, which by default will connect to the server locally, on 127.0.0.1:5001, or you can provide a URL of your server explicitly:

```
~/spiderfoot$ python3 sfcli.py -s https://127.0.0.1:5001
```

If you wish to make SpiderFoot accessible from another system, for example running it on a server and controlling it remotely using `sfcli.py`, then you can specify an external IP for SpiderFoot to bind to, or use 0.0.0.0 so that it binds to all addresses, including 127.0.0.1:

```
~/spiderfoot$ python3 sf.py -l 0.0.0.0:5001
```

Then to use the CLI from a remote system where the `sfcli.py` file has been copied to, you would run:

```
$ python3 sfcli.py -u https://<remote ip>:5001
```

Run `python3 ./sfcli.py --help` to better understand how to use the client CLI.

If port 5001 is used by another application on your system, you can change the port:

```
~/spiderfoot$ python3 sf.py -l 127.0.0.1:9999
```

Once started, you will see something similar to this, which means you are ready to go. If you instead see an error message about missing modules, please go back and ensure you’ve installed all the pre-requisites.

```
~/spiderfoot$ python3 ./sf.py -l 0.0.0.0:5001
Attempting to verify database and update if necessary...
Starting web server at https://0.0.0.0:5001 ...


*************************************************************
 Use SpiderFoot by starting your web browser of choice and
 browse to https://<IP of this host>:5001
*************************************************************


[08/Jul/2019:14:40:53] ENGINE Listening for SIGHUP.
[08/Jul/2019:14:40:53] ENGINE Listening for SIGTERM.
[08/Jul/2019:14:40:53] ENGINE Listening for SIGUSR1.
[08/Jul/2019:14:40:53] ENGINE Bus STARTING
[08/Jul/2019:14:40:53] ENGINE Serving on https://0.0.0.0:5001
[08/Jul/2019:14:40:53] ENGINE Bus STARTED
```

**Caution!**

By default, SpiderFoot does not authenticate users connecting to its user-interface or serve over HTTPS, so avoid running it on a server/workstation that can be accessed from untrusted devices, as they will be able to control SpiderFoot remotely and initiate scans from your devices. As of SpiderFoot 2.7, to use authentication and HTTPS, see the [Security](https://www.spiderfoot.net/documentation//#security) section below.

### Scan Mode

New in SpiderFoot 3.0 is the ability to run SpiderFoot entirely via the command-line (without starting a web server) to run a scan. You can see all the available command-line arguments by using the `--help` flag:

```
~/spiderfoot$ python3 ./sf.py --help
usage: sf.py [-h] [-d] [-l IP:port] [-m mod1,mod2,...] [-M] [-s TARGET]
             [-t type1,type2,...] [-T] [-o tab|csv|json] [-n] [-r] [-S LENGTH]
             [-D DELIMITER] [-f] [-F FILTER] [-x] [-q]

SpiderFoot 3.0: Open Source Intelligence Automation.

optional arguments:
  -h, --help          show this help message and exit
  -d, --debug         Enable debug output.
  -l IP:port          IP and port to listen on.
  -m mod1,mod2,...    Modules to enable.
  -M, --modules       List available modules.
  -s TARGET           Target for the scan.
  -t type1,type2,...  Event types to collect.
  -T, --types         List available event types.
  -o tab|csv|json     Output format. Tab is default.
  -n                  Strip newlines from data.
  -r                  Include the source data field in tab/csv output.
  -S LENGTH           Maximum data length to display. By default, all data is
                      shown.
  -D DELIMITER        Delimiter to use for CSV output. Default is ,.
  -f                  Filter out other event types that weren't requested with
                      -t.
  -F FILTER           Filter out a set of event types.
  -x                  STRICT MODE. Will only enable modules that can directly
                      consume your target, and if -t was specified only those
                      events will be consumed by modules. This overrides -t
                      and -m options.
  -q                  Disable logging.
```

The command-line arguments are fairly self explanatory, however a few require some explaining. First, some simple examples…

The below example is running a scan against binarypool.com as a target, enabling a very simple module, `sfp_dnsresolve` which performs simple DNS resolutions of any identified IP addresses and hostnames.

```
~/spiderfoot$ python3 ./sf.py -m sfp_dnsresolve -s binarypool.com
Attempting to verify database and update if necessary...
[*] Modules enabled (3): sfp_dnsresolve,sfp__stor_db,sfp__stor_stdout
[*] Scan [FA0D8528] initiated.
[*] Downloading configuration data from: https://publicsuffix.org/list/effective_tld_names.dat
[*] Identifying aliases for specified target(s)
[*] Aliases identified: [{'value': '104.236.67.238', 'type': 'IP_ADDRESS'}, {'value': 'binarypool.com', 'type': 'INTERNET_NAME'}, {'value': b'binarypool.com', 'type': 'INTERNET_NAME'}]
[*] sfp_dnsresolve module loaded.
[*] sfp__stor_db module loaded.
[*] sfp__stor_stdout module loaded.
SpiderFoot UI                 Internet Name                                binarypool.com
sfp_dnsresolve                IP Address                                   104.236.67.238
sfp_dnsresolve                Domain Name (Parent)                         com
[*] Scan [FA0D8528] completed.
[*] Scan completed with status FINISHED
```

We can see that it is a little noisy, so we can add the `-q` flag to reduce output to just the data from the scan:

```
~/spiderfoot$ python3 ./sf.py -m sfp_dnsresolve -s binarypool.com -q
Attempting to verify database and update if necessary...
SpiderFoot UI                 Internet Name                                binarypool.com
sfp_dnsresolve                IP Address                                   104.236.67.238
sfp_dnsresolve                Domain Name                                  binarypool.com
SpiderFoot UI                 Domain Name                                  binarypool.com
```

It’s also not necessary to specify any module, and just run all modules for your scan:

```
~/spiderfoot$ python3 ./sf.py -s binarypool.com -q
Attempting to verify database and update if necessary...
WARNING: You didn't specify any modules or types, so all will be enabled.
SpiderFoot UI                 Internet Name                                binarypool.com
sfp_hunter                    Email Address                                steve@binarypool.com
sfp_emailrep                  Raw Data from RIRs/APIs                      {'references': 5, 'email': 'steve@binarypool.com', 'suspicious': False, 'reputation': 'high', 'details': {'valid_mx': True, 'data_breach': True, 'suspicious_tld': False, 'spf_strict': False, 'days_since_domain_creation': 5315, 'last_seen': '10/16/2019', 'credentials_leaked_recent': False, 'malicious_activity': False, 'spoofable': True, 'dmarc_enforced': False, 'profiles': ['pastebin', 'twitter'], 'free_provider': False, 'disposable': False, 'deliverable': True, 'spam': False, 'domain_reputation': 'high', 'credentials_leaked': True, 'accept_all': True, 'new_domain': False, 'domain_exists': True, 'first_seen': '05/05/2012', 'malicious_activity_recent': False, 'blacklisted': False}}
sfp_email                     Email Address                                steve@binarypool.com
sfp_emailrep                  Hacked Email Address                         steve@binarypool.com [Unknown]
...
```

So far this has all been fairly simple. But if we want to do something a little more advanced, such as getting every possible e-mail address on a domain name (`-t EMAILADDR`), using only modules that take our target directly as input (referred to as “strict mode”, `-x`), and only get e-mail address but not any other data (`-f`), we can do the following:

```
~/spiderfoot$ python3 ./sf.py -s spiderfoot.net -t EMAILADDR -f -x -q
Attempting to verify database and update if necessary...
sfp_hunter                    Email Address                                support@spiderfoot.net
~/spiderfoot$
```

[Up to table of contents](https://www.spiderfoot.net/documentation//#toc)

### Security

Since version 2.7, SpiderFoot introduced authentication as well as TLS/SSL support. These are automatic based on the presence of specific files.

#### Authentication

SpiderFoot will require basic digest authentication if a file named `passwd` exists in `$HOME/.spiderfoot/passwd`. The format of the file is simple–just create an entry per account, in the format of:

```
username:password
```

For example:

```
admin:supersecretpassword
```

Once the file is created, restart SpiderFoot.

#### TLS/SSL

SpiderFoot will serve HTTPS (and only that) if it detects the existence of a public certificate and key file in SpiderFoot’s root directory. This means whatever port you set SpiderFoot to listen on is the port TLS/SSL will be used. It is not possible for SpiderFoot to serve both HTTP and HTTPS simultaneously on different ports. If you need to do that, an nginx proxy in front of SpiderFoot would be a better solution.

Simply place two files in the SpiderFoot directory– `spiderfoot.crt` (RSA public key in PEM format) and `spiderfoot.key` (RSA private key in PEM format). Restart SpiderFoot and you will now be serving HTTPS only.

A [helper script](https://github.com/smicallef/spiderfoot/blob/master/generate-certificate) has been provided for Linux users to generate self-signed certificate using OpenSSL, or you can follow the instructions [in this StackOverflow article](https://stackoverflow.com/questions/10175812/how-to-create-a-self-signed-certificate-with-openssl).

[Up to table of contents](https://www.spiderfoot.net/documentation//#toc)

### API Keys

Many SpiderFoot modules require API keys to function to their fullest extent (or at all), so you will need to go to each service and obtain an API key where you feel that having such a key would add value to your scans. Instructions for how to obtain each API key can be found within the Settings for the respective module:

![](https://www.spiderfoot.net/wp-content/uploads/2020/10/config-1024x451.png)

[Up to table of contents](https://www.spiderfoot.net/documentation//#toc)

### Configuring SpiderFoot

One of the main principles behind SpiderFoot is to be highly configurable. Every setting is available in the user interface within the Settings section and should be adequately explained there. Just a few key points to note:

- API keys can be imported and exported between SpiderFoot and SpiderFoot HX using the “Import API Keys” and “Export API Keys” functions. The format is also a simple CSV so can also be manipulated outside of SpiderFoot to be loaded in, if you prefer.
- When Debugging is enabled, a lot of logs are generated and can sometimes result in error messages about database locking. This appears to be harmless towards the scan but can mean that logs get dropped.
- It is worth going through the modules you intend to rely upon heavily to ensure they are configured appropriately for your needs, most importantly the DNS-related modules as they tend to have a knock-on impact to many other modules.

[Up to table of contents](https://www.spiderfoot.net/documentation//#toc)

### Using SpiderFoot

#### Running a Scan

When you run SpiderFoot in Web UI mode for the first time, there is no historical data, so you should be presented with a screen like the following:

![](https://134.209.41.85/wp-content/uploads/2019/07/spiderfoot-newscan.png)

To initiate a scan, click on the ‘New Scan’ button in the top menu bar. You will then need to define a name for your scan (these are non-unique) and a target (also non-unique):

![](https://134.209.41.85/wp-content/uploads/2019/07/spiderfoot-newscan3.png)

You can then define how you would like to run the scan–either by use case (the tab selected by default), by data required or by module.

Module-based scanning is for more advanced users who are familiar with the behavior and data provided by different modules, and want more control over the scan:

![](https://134.209.41.85/wp-content/uploads/2019/07/spiderfoot-modules.png)

Beware though, there is no dependency checking when scanning by module, only for scanning by required data. This means that if you select a module that depends on event types only provided by other modules, but those modules are not selected, you will get no results.

#### Scan Results

From the moment you click ‘Run Scan’, you will be taken to a screen for monitoring your scan in near real time:

![](https://134.209.41.85/wp-content/uploads/2019/07/spiderfoot-running-1024x589.png)

That screen is made up of a graph showing a break down of the data obtained so far plus log messages generated by SpiderFoot and its modules.

The bars of the graph are clickable, taking you to the result table for that particular data type.

#### Browsing Results

By clicking on the ‘Browse’ button for a scan, you can browse the data by type:

![](https://134.209.41.85/wp-content/uploads/2019/07/spiderfoot-browse.png)

This data is exportable and searchable. Click the Search box to get a pop-up explaining how to perform searches.

By clicking on one of the data types, you will be presented with the actual data:

![](https://134.209.41.85/wp-content/uploads/2019/07/spiderfoot-browse2.png)

The fields displayed are explained as follows:

- Checkbox field: Use this to set/unset fields as false positive. Once at least one is checked, click the orange False Positive button above to set/unset the record.
- Data Element: The data the module was able to obtain about your target.
- Source Data Element: The data the module received as the basis for its data colletion. In the example above, the sfp\_portscan\_tcp module received an event about an open port, and used that to obtain the banner on that port.
- Source Module: The module that identified this data.
- Identified: When the data was identified by the module.

You can click the black icons to modify how this data is represented. For instance you can get a unique data representation by clicking the Unique Data View icon:

![](https://134.209.41.85/wp-content/uploads/2019/07/spiderfoot-unique.png)

#### Setting False Positives

Version 2.6.0 introduced the ability to set data records as false positive. As indicated in the previous section, use the checkbox and the orange button to set/unset records as false positive.

Once you have set records as false positive, you will see an indicator next to those records, and have the ability to filter them from view, as shown below:

![](https://134.209.41.85/wp-content/uploads/2019/07/spiderfoot-falsepos2-1024x274.png)

**NOTE**: Records can only be set to false positive once a scan has finished running. This is because setting a record to false positive also results in all child data elements being set to false positive. This obviously cannot be done if the scan is still running and can thus lead to an inconsistent state in the back-end. The UI will prevent you from doing so.

The result of a record being set to false positive, aside from the indicator in the data table view and exports, is that such data will not be shown in the node graphs.

#### Searching Results

Results can be searched either at the whole scan level, or within individual data types. The scope of the search is determined by the screen you are on at the time.

![](https://134.209.41.85/wp-content/uploads/2019/07/spiderfoot-search-1024x429.png)

As indicated by the pop-up box when selecting the search field, you can search as follows:

- Exact value: Non-wildcard searching for a specific value. For example, search for 404 within the HTTP Status Code section to see all pages that were not found.
- Pattern matching: Search for simple wildcards to find patterns. For example, search for \*:22 within the Open TCP Port section to see all instances of port 22 open.
- Regular expression searches: Encapsulate your string in ‘/’ to search by regular expression. For example, search for ‘/\\d+.\\d+.\\d+.\\d+/’ to find anything looking like an IP address in your scan results.

#### Managing Scans

When you have some historical scan data accumulated, you can use the list available on the ‘Scans’ section to manage them:

![](https://134.209.41.85/wp-content/uploads/2019/07/spiderfoot-scanlist2.png)

You can filter the scans shown by altering the Filter drop-down selection. Except for the green refresh icon, all icons on the right will all apply to whichever scans you have checked the checkboxes for.

#### Tor Integration

Refer to [this post](https://www.spiderfoot.net/spiderfoot-and-tor/) for more information.

[Up to table of contents](https://www.spiderfoot.net/documentation//#toc)

### Modules

#### Overview

SpiderFoot has all data collection modularised. When a module discovers a piece of data, that data is transmitted to all other modules that are ‘interested’ in that data type for processing. Those modules will then act on that piece of data to identify new data, and in turn generate new events for other modules which may be interested, and so on.

For example, `sfp_dnsresolve` may identify an IP address associated with your target, notifying all interested modules. One of those interested modules would be the `sfp_ripe` module, which will take that IP address and identify the netblock it is a part of, the BGP ASN and so on.

This might be best illustrated by looking at module code. For example, the `sfp_names` module looks for TARGET\_WEB\_CONTENT and EMAILADDR events for identifying human names:

```
    # What events is this module interested in for input
    # * = be notified about all events.
    def watchedEvents(self):
        return ["TARGET_WEB_CONTENT", "EMAILADDR"]

    # What events this module produces
    # This is to support the end user in selecting modules based on events
    # produced.
    def producedEvents(self):
        return ["HUMAN_NAME"]
```

Meanwhile, as each event is generated to a module, it is also recorded in the SpiderFoot database for reporting and viewing in the UI.

#### Module List

To see a list of all SpiderFoot modules, run `sf.py -M`:

```
~/spiderfoot$ python3 ./sf.py -M
Attempting to verify database and update if necessary...
Modules available:
sfp_abusech                Check if a host/domain, IP or netblock is malicious according to abuse.ch.
sfp_abuseipdb              Check if a netblock or IP is malicious according to AbuseIPDB.com.
sfp_accounts               Look for possible associated accounts on nearly 200 websites like Ebay, Slashdot, reddit, etc.
sfp_adblock                Check if linked pages would be blocked by AdBlock Plus.
sfp_ahmia                  Search Tor 'Ahmia' search engine for mentions of the target domain.
sfp_alienvault             Obtain information from AlienVault Open Threat Exchange (OTX)
sfp_alienvaultiprep        Check if an IP or netblock is malicious according to the AlienVault IP Reputation database.
sfp_apility                Search Apility API for IP address and domain reputation.
sfp_archiveorg             Identifies historic versions of interesting files/pages from the Wayback Machine.
sfp_arin                   Queries ARIN registry for contact information.
...
```

#### Data Elements

As mentioned above, SpiderFoot works on an “event-driven” module, whereby each module generates events about *data elements* which other modules listen to and consume.

The data elements are one of the following types:

- *entities* like IP addresses, Internet names (hostnames, sub-domains, domains),
- *sub-entities* like port numbers, URLs and software installed,
- *descriptors* of those entities (malicious, physical location information,…) or
- *data* which is mostly unstructured data (web page content, port banners, raw DNS records,…)

To see a full list of all the types available, run `sf.py -T`:

```
~/spiderfoot$ python3 ./sf.py -T
Attempting to verify database and update if necessary...
Types available:
ACCOUNT_EXTERNAL_OWNED                         Account on External Site
ACCOUNT_EXTERNAL_OWNED_COMPROMISED             Hacked Account on External Site
ACCOUNT_EXTERNAL_USER_SHARED_COMPROMISED       Hacked User Account on External Site
AFFILIATE_COMPANY_NAME                         Affiliate - Company Name
AFFILIATE_DESCRIPTION_ABSTRACT                 Affiliate Description - Abstract
AFFILIATE_DESCRIPTION_CATEGORY                 Affiliate Description - Category
AFFILIATE_DOMAIN                               Affiliate - Domain Name
AFFILIATE_DOMAIN_NAME                          Affiliate - Domain Name
AFFILIATE_DOMAIN_UNRESOLVED                    Affiliate - Domain Name - Unresolved
AFFILIATE_DOMAIN_WHOIS                         Affiliate - Domain Whois
AFFILIATE_EMAILADDR                            Affiliate - Email Address
...
```

#### Writing a Module

To write a SpiderFoot module, start by looking at the `sfp_template.py` file which is a skeleton module that does nothing. Use the following steps as your guide:

1. Create a copy of `sfp_template.py` to whatever your module will be named. Try and make this something descriptive, i.e. not something like `sfp_mymodule.py`but instead something like `sfp_imageanalyser.py` if you were creating a module to analyse image content.
2. Replace XXX in the new module with the name of your module and update the descriptive information in the header and comment within the module.
3. The comment for the class (check in `sfp_template.py`) is used by SpiderFoot in the UI to correctly categorise modules, so make it something meaningful. Look at other modules for examples.
4. Set the events in `watchedEvents()` and `producedEvents()` accordingly, based on the data element table in the previous section. If you are producing a new data element not pre-existing in SpiderFoot, you must create this in the database:
    - `` ~/spiderfoot$ sqlite3 spiderfoot.db sqlite> INSERT INTO tbl_event_types (event, event_descr, event_raw) VALUES ('NEW_DATA_ELEMENT_TYPE_NAME_HERE', 'Description of your New Data Element Here', 0, 'DESCRIPTOR or DATA or ENTITY or SUBENTITY');` ``
5. Put the logic for the module in `handleEvent()`. Each call to `handleEvent()` is provided a `SpiderFootEvent` object. The most important values within this object are:
    - `eventType`: The data element ID (`IP_ADDRESS`, `WEBSERVER_BANNER`, etc.)
    - `data`: The actual data, e.g. the IP address or web server banner, etc.
    - `module`: The name of the module that produced the event (`sfp_dnsresolve`, etc.)
6. When it is time to generate your event, create an instance of `SpiderFootEvent`:
    - `e = SpiderFootEvent("IP_ADDRESS", ipaddr, self.__name__, event)`
    - Note: the `event` passed as the last variable is the event that your module received. This is what builds a relationship between data elements in the SpiderFoot database.
7. Notify all modules that may be interested in the event:
    - `self.notifyListeners(e)`

[Up to table of contents](https://www.spiderfoot.net/documentation//#toc)

### Database

All SpiderFoot data is stored in a SQLite database (`spiderfoot.db` in your SpiderFoot installation folder) which can be used outside of SpiderFoot for analysis of your data.

The schema is quite simple and can be viewed in the [GitHub repo](https://github.com/smicallef/spiderfoot/blob/master/sfdb.py#L37).

The below queries might provide some further clues:

```
# Total number of scans in the SpiderFoot database
sqlite> select count(*) from tbl_scan_instance;
10
```

```
# Obtain the ID for a particular scan
sqlite> select guid from tbl_scan_instance where seed_target = 'binarypool.com';
b459e339523b8d06235bd06087ae6c6017aaf4ed68dccea0b65a1999a17e460a
```

```
# Number of results per data type
sqlite> select count(*), type from tbl_scan_results where scan_instance_id = 'b459e339523b8d06235bd06087ae6c6017aaf4ed68dccea0b65a1999a17e460a' group by type;
5|AFFILIATE_INTERNET_NAME
2|AFFILIATE_IPADDR
1|CO_HOSTED_SITE
1|DOMAIN_NAME
1|DOMAIN_REGISTRAR
1|DOMAIN_WHOIS
1|GEOINFO
28|HTTP_CODE
48|HUMAN_NAME
49|INTERNET_NAME
2|IP_ADDRESS
49|LINKED_URL_EXTERNAL
144|LINKED_URL_INTERNAL
2|PROVIDER_DNS
1|PROVIDER_MAIL
4|RAW_DNS_RECORDS
1|RAW_FILE_META_DATA
1|ROOT
14|SEARCH_ENGINE_WEB_CONTENT
1|SOFTWARE_USED
16|TARGET_WEB_CONTENT
2|TCP_PORT_OPEN
1|TCP_PORT_OPEN_BANNER
1|URL_FORM
10|URL_JAVASCRIPT
6|URL_STATIC
21|URL_WEB_FRAMEWORK
28|WEBSERVER_BANNER
28|WEBSERVER_HTTPHEADERS
```
