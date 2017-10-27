# Elysium Project — Progressive DB
Elysium's database repository for World of Warcraft (1.12), compatible with the [Elysium server core](https://github.com/elysium-project/server) (based on Mangos). This repository includes the full progression database for 1.2 → 1.12 versions, which, when applied, can simulate WoW as if it was at this state.

Here are some of the sources we can use to find item changes:

## Allakhazam (viewing old versions of the site using the wayback machine)
https://web.archive.org/web/20060522202752/http://wow.allakhazam.com:80/db/item.html?witem=1992
Just paste the id of the item at the end of the link and check the different dates.

## WoWWiki (check the history of the page)
http://wowwiki.wikia.com/wiki/Tanglewood_Staff

## The official patch notes.
https://github.com/elysium-project/database/blob/master/progression/Patchnotes%20%28ALPHA%20to%201.12.1%29.txt

## Client data converted to sql tables.
https://github.com/elysium-project/database/blob/master/progression/old_versions_data.7z
For items that use spells (on equip/use effect) we can use the dbc data to find out when the item effect was changed. Simply check the spells0-9 tables and see when the spell was updated.
We can also check if the diplayid used by the item exists in older clients, but that will only tell us if the item existed and had the same displayid, not when it was updated.

* Remember that patch values start from 0 for 1.2, and go to 10 for 1.12.

Keep your backup table up to date by applying migrations from the *[updates](https://github.com/elysium-project/database/tree/master/updates)* and [migrations](https://github.com/elysium-project/server/tree/development/sql/migrations) from the server repository. 

It is now extreamly easy for people to contribute now, and this will save us a lot of time in the long run.

## Tools
* [Item Template Editor (ITE)](https://github.com/elysium-project/database/tree/master/tools/item_template_editor): GUI to update items in the database. Generates SQL statements.
* [Item Template Commentator](https://github.com/elysium-project/database/tree/master/tools/item_template_commentator): Adds a comment, listing name and stats, above each altered item_template in a SQL file.
* [Commentator](https://github.com/elysium-project/database/tree/master/tools/Commentator): Converts all SQL comments to markdown. 

## License
This project is licensed under the GNU GPL 3.0 License - see the [LICENSE](./LICENSE) file for details!

## Links
* [Website](https://www.elysium-project.org)
