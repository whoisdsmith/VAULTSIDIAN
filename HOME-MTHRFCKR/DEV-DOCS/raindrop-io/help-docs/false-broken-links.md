# False Broken Links

---

## Local resources

---

If you have bookmarks for resources that only accessible from your local network, they will be marked as broken.
This happen because our automated scripts can't connect to such domains and by default we mark them as broken.

To change this behaviour:

1. Visit [settings](https://app.raindrop.io/settings/app)
2. Select [Basic mode](#basic-mode) from `Broken links` dropdown
3. Wait for few hours

---

## Fix broken link

---

If URL is incorrect such bookmark will be marked as broken. Just fix URL and wait for few hours, broken state will be updated automatically.

---

## Modes

---

To prevent false positives you can [configure](https://app.raindrop.io/settings/app) how strictly we should check your bookmarks.

We have few different modes to choose from:

---

### Basic mode

- Mark as "broken" only when origin server send 404 (not found) or 410 (gone) HTTP status

### Default mode

- Origin server send 404 (not found) or 410 (gone) status
- Or domain name is unresolved / not exists

### Strict mode

- Same as "Default", plus:
- Origin response is timed out (more than 13 sec)
- Server is down or send error (408, 500, 521, 523, 524 HTTP status)
- A lot of redirects

---
