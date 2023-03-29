# Gather note

@JoshConley and @AndrewSouthpaw forked from the original repo. The original script uses API keys, which [are now deprecated](https://developers.hubspot.com/docs/api/migrate-an-api-key-integration-to-a-private-app), so we had to tweak the code a bit.

## Usage

In the `portal_property_syncer.py`, near the bottom you'll need to add `accessToken` info for both `portal1Portal` and `portal2Portal`:

For `portal1Portal.accessToken`, run this command to grab the key:

```
$ doppler -p gather-town -c prod_http secrets get PROD_SERVER_HUBSPOT_API_KEY --raw --plain
```

For `portal2Portal.accessToken`, run this command to grab the key:

```
$ doppler -p gather-town -c dev_http secrets get DEV_SERVER_HUBSPOT_API_KEY --raw --plain
```

From the repo root, run:

```
$ pip3 install -r requirements.txt
$ python3 portal_property_syncer.py
```

# HubSpot Portal Syncer

Collection of simple tools that allow syncing several HubSpot portal together.

Developed in [Mayple](https://www.mayple.com).

## Portal Property Syncer

Sync the properties of contacts, companies, deals and tickets from one portal to another.
At the end of execution, it lets you know what manual operations you are required to do.
NOTE: right now, this only creates new properties in the target portal, it does update existing properties to be like the source.
Set the appropriate API keys and portal IDs to the portals you wish to sync, update the pairs and run it. Fairly simple.

## Author

**Alon Diamant (advance512)**

* [github/advance512](https://github.com/advance512)
* [Homepage](http://www.alondiamant.com)
