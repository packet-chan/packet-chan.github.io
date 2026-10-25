# packet-chan developer website

Single publishing repository for https://packet-chan.github.io/.

| URL | Purpose |
| --- | --- |
| `/` | Public developer homepage |
| `/app-ads.txt` | AdMob authorized seller record; keep at domain root |
| `/privacy_policy/` | Existing Block Stack privacy-policy URL; preserve for released apps |

For future apps, use `/apps/<unique-app-slug>/` and keep their files in matching directories. Reserve the paths above; avoid publishing another project repository under the same path.

Only public static content belongs here. Never add signing keys, passwords, service-account files, production secrets, or private development builds. A hidden link, an obscure URL, or robots.txt does not provide access control. Services requiring authentication belong on a host that enforces authentication.

The privacy_policy repository history was merged into this repository under `privacy_policy/`. Maintain the policy here going forward. The old repository is retained only for historical reference; its separate Pages publishing is disabled after migration.
