# World Airports Database

Global airports database with ICAO/IATA codes, coordinates, city, country, elevation, and timezone. 7,900+ airports.

## What is this?

This repository provides a **ready-to-use database** of world airports database with **7,914 records**. Available as SQLite database and SQL dumps — ideal for developers, data analysts, and fintech applications.

## Downloads

| Format | Description | Link |
|---|---|---|
| **SQLite** | Single database file, ready to query | [Releases](../../releases) |
| **SQL** | SQL dump, import into MySQL/PostgreSQL/etc. | [Releases](../../releases) |
| **Excel / CSV / PDF** | Formatted spreadsheets | [listbase.org](https://listbase.org/en/transport/) |

## Database Schema

```sql
CREATE TABLE airports (
  icao TEXT,
  iata TEXT,
  name TEXT NOT NULL,
  city TEXT,
  state TEXT,
  country TEXT NOT NULL,
  elevation INTEGER,
  lat REAL,
  lon REAL,
  tz TEXT
);
CREATE INDEX idx_airports_iata ON airports (iata);
CREATE INDEX idx_airports_icao ON airports (icao);
CREATE INDEX idx_airports_country ON airports (country);
```

## Stats

- **7,914** records
- **1** datasets
- Updated: **2026-07-27**

## Preview

| icao | iata | name | city | state | country | elevation | lat | lon | tz |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 06N7 | NYS | New York Skyports Seaplane Base | New York | New York | US |  | 40.73399083 | -73.97291638 | America/New_York |
| 19AK | ICY | Icy Bay Airport | Icy Bay | Alaska | US | 50 | 59.96900177 | -141.662002563 | America/Anchorage |
| 2AK6 | HGZ | Hog River Airport | Hogatza | Alaska | US | 534 | 66.2161026 | -155.6690063 | America/Anchorage |
| 38WA | BYW | Blakely Island Airport | Blakely Island | Washington | US | 66 | 48.5789985657 | -122.825996399 | America/Los_Angeles |
| 3IS8 | BDF | Rinkenberger Restricted Landing Area | Bradford | Illinois | US | 808 | 41.2308998108 | -89.6156997681 | America/Chicago |
| 65LA | BCS | Southern Seaplane Airport | Belle Chasse | Louisiana | US |  | 29.8661003113 | -90.0222015381 | America/Chicago |
| 7NC2 | DUF | Pine Island Airport | Corolla | North Carolina | US | 16 | 36.2535018921 | -75.7884979248 | America/New_York |
| 82CL | FOB | Fort Bragg Airport | Fort Bragg | California | US | 71 | 39.4743003845 | -123.79599762 | America/Los_Angeles |
| AGAF | AFT | Afutara Aerodrome | Bila | Malaita | SB | 23 | -9.1913888889 | 160.948611111 | Pacific/Guadalcanal |
| AGAR | RNA | Ulawa Airport | Arona |  | SB | 40 | -9.8605435826 | 161.979546547 | Pacific/Guadalcanal |
| AGAT | ATD | Uru Harbour Airport | Atoifi |  | SB |  | -8.8733301163 | 161.0110015869 | Pacific/Guadalcanal |
| AGBA | VEV | Barakoma Airport | Barakoma |  | SB |  | -7.912779808 | 156.7059936523 | Pacific/Guadalcanal |
| AGBT | BPF | Batuna Aerodrome | Batuna Mission Station | Western Province | SB | 24 | -8.5620277778 | 158.119305556 | Pacific/Guadalcanal |
| AGEV | GEF | Geva Airport | Liangia |  | SB |  | -7.5758299828 | 156.5970001221 | Pacific/Guadalcanal |
| AGGA | AKS | Auki Airport | Auki |  | SB | 5 | -8.7025699616 | 160.682006836 | Pacific/Guadalcanal |
| ... | ... | ... | ... | ... | ... | ... | ... | ... | ... |

*Showing 15 of 7,914 records*

## Release Files

| File | Records | Description |
|---|---|---|
| `world-airports.db` | 7,914 | SQLite database (all data) |
| `world-airports.sql` | 1-7,914 | SQL dump |


## Usage

### SQLite
```bash
sqlite3 world-airports.db "SELECT iata, name, city, country FROM airports WHERE country = 'TH' ORDER BY name;"
```

### Import SQL (MySQL)
```bash
mysql -u root -p your_database < world-airports.sql
```

### Import SQL (PostgreSQL)
```bash
psql -U postgres -d your_database -f world-airports.sql
```

## Use Cases

- **Flight search apps** — Look up airports by IATA/ICAO code or city name
- **Distance calculation** — Use lat/lon coordinates to compute distances between airports
- **Travel planning** — Find airports near a destination with timezone info
- **Logistics &amp; cargo** — Map airport locations for freight routing
- **Data enrichment** — Enrich flight data with airport names, cities, and countries

## FAQ

### What is an IATA code?
An IATA code is a 3-letter airport identifier assigned by the International Air Transport Association (e.g., LAX, NRT, BKK). It is used in airline tickets, baggage tags, and flight booking systems.

### What is an ICAO code?
An ICAO code is a 4-letter airport identifier assigned by the International Civil Aviation Organization (e.g., KLAX, RJTT, VTBS). It is used in air traffic control and flight plans.

### How often is this data updated?
The database is updated monthly. Check the [Releases](../../releases) page for the latest version.

### Can I use this data commercially?
Yes. This data is released under the [MIT License](LICENSE) — free to use for any purpose, including commercial applications.

### How do I find airports in a specific country?
```sql
SELECT iata, name, city FROM airports WHERE country = 'JP' ORDER BY name;
```

### How do I search for an airport by name?
```sql
SELECT * FROM airports WHERE name LIKE '%Heathrow%';
```


## Countries (1)

| Country | Code | Records | Details |
|---|---|---|---|
| United States of America | US | 1,777 | [View](countries/US/) |
| Australia | AU | 528 | [View](countries/AU/) |
| Canada | CA | 405 | [View](countries/CA/) |
| Brazil | BR | 331 | [View](countries/BR/) |
| China | CN | 238 | [View](countries/CN/) |
| Russian Federation | RU | 196 | [View](countries/RU/) |
| Indonesia | ID | 174 | [View](countries/ID/) |
| France | FR | 164 | [View](countries/FR/) |
| India | IN | 147 | [View](countries/IN/) |
| United Kingdom of Great Britain and Northern Ireland | GB | 114 | [View](countries/GB/) |
| Germany | DE | 111 | [View](countries/DE/) |
| Colombia | CO | 100 | [View](countries/CO/) |
| Argentina | AR | 99 | [View](countries/AR/) |
| Japan | JP | 97 | [View](countries/JP/) |
| Papua New Guinea | PG | 92 | [View](countries/PG/) |
| Mexico | MX | 88 | [View](countries/MX/) |
| South Africa | ZA | 82 | [View](countries/ZA/) |
| Iran, Islamic Republic of | IR | 76 | [View](countries/IR/) |
| Italy | IT | 67 | [View](countries/IT/) |
| Türkiye | TR | 66 | [View](countries/TR/) |
| Philippines | PH | 63 | [View](countries/PH/) |
| Congo, Democratic Republic of the | CD | 61 | [View](countries/CD/) |
| Norway | NO | 57 | [View](countries/NO/) |
| New Zealand | NZ | 57 | [View](countries/NZ/) |
| Madagascar | MG | 56 | [View](countries/MG/) |
| Pakistan | PK | 56 | [View](countries/PK/) |
| Venezuela, Bolivarian Republic of | VE | 56 | [View](countries/VE/) |
| Malaysia | MY | 56 | [View](countries/MY/) |
| Spain | ES | 55 | [View](countries/ES/) |
| Sweden | SE | 53 | [View](countries/SE/) |
| Chile | CL | 50 | [View](countries/CL/) |
| Peru | PE | 48 | [View](countries/PE/) |
| French Polynesia | PF | 47 | [View](countries/PF/) |
| Greece | GR | 45 | [View](countries/GR/) |
| Thailand | TH | 45 | [View](countries/TH/) |
| Myanmar | MM | 44 | [View](countries/MM/) |
| Algeria | DZ | 42 | [View](countries/DZ/) |
| Nepal | NP | 42 | [View](countries/NP/) |
| Ethiopia | ET | 40 | [View](countries/ET/) |
| Bolivia, Plurinational State of | BO | 40 | [View](countries/BO/) |
| Iceland | IS | 38 | [View](countries/IS/) |
| Saudi Arabia | SA | 36 | [View](countries/SA/) |
| Angola | AO | 35 | [View](countries/AO/) |
| Finland | FI | 34 | [View](countries/FI/) |
| Ukraine | UA | 34 | [View](countries/UA/) |
| Bahamas | BS | 33 | [View](countries/BS/) |
| Cuba | CU | 32 | [View](countries/CU/) |
| Solomon Islands | SB | 31 | [View](countries/SB/) |
| Kenya | KE | 31 | [View](countries/KE/) |
| Costa Rica | CR | 30 | [View](countries/CR/) |
| Vanuatu | VU | 30 | [View](countries/VU/) |
| Tanzania, United Republic of | TZ | 28 | [View](countries/TZ/) |
| Ecuador | EC | 28 | [View](countries/EC/) |
| Burkina Faso | BF | 27 | [View](countries/BF/) |
| Poland | PL | 26 | [View](countries/PL/) |
| Gabon | GA | 26 | [View](countries/GA/) |
| Egypt | EG | 26 | [View](countries/EG/) |
| Korea, Republic of | KR | 26 | [View](countries/KR/) |
| Viet Nam | VN | 26 | [View](countries/VN/) |
| Portugal | PT | 25 | [View](countries/PT/) |
| Kazakhstan | KZ | 25 | [View](countries/KZ/) |
| Honduras | HN | 24 | [View](countries/HN/) |
| Afghanistan | AF | 24 | [View](countries/AF/) |
| Namibia | NA | 23 | [View](countries/NA/) |
| Morocco | MA | 23 | [View](countries/MA/) |
| Côte d&#39;Ivoire | CI | 22 | [View](countries/CI/) |
| Nigeria | NG | 22 | [View](countries/NG/) |
| Congo | CG | 22 | [View](countries/CG/) |
| Sudan | SD | 22 | [View](countries/SD/) |
| Fiji | FJ | 22 | [View](countries/FJ/) |
| Guyana | GY | 22 | [View](countries/GY/) |
| Central African Republic | CF | 21 | [View](countries/CF/) |
| Zambia | ZM | 21 | [View](countries/ZM/) |
| Cameroon | CM | 20 | [View](countries/CM/) |
| Guatemala | GT | 20 | [View](countries/GT/) |
| Kiribati | KI | 20 | [View](countries/KI/) |
| Taiwan, Province of China | TW | 20 | [View](countries/TW/) |
| Ireland | IE | 19 | [View](countries/IE/) |
| Mozambique | MZ | 19 | [View](countries/MZ/) |
| Mauritania | MR | 18 | [View](countries/MR/) |
| Romania | RO | 18 | [View](countries/RO/) |
| Mongolia | MN | 18 | [View](countries/MN/) |
| Denmark | DK | 17 | [View](countries/DK/) |
| Lesotho | LS | 17 | [View](countries/LS/) |
| Somalia | SO | 17 | [View](countries/SO/) |
| Maldives | MV | 17 | [View](countries/MV/) |
| Switzerland | CH | 16 | [View](countries/CH/) |
| Suriname | SR | 16 | [View](countries/SR/) |
| Botswana | BW | 15 | [View](countries/BW/) |
| Chad | TD | 15 | [View](countries/TD/) |
| Panama | PA | 15 | [View](countries/PA/) |
| New Caledonia | NC | 15 | [View](countries/NC/) |
| Oman | OM | 15 | [View](countries/OM/) |
| Yemen | YE | 15 | [View](countries/YE/) |
| Uzbekistan | UZ | 15 | [View](countries/UZ/) |
| Greenland | GL | 14 | [View](countries/GL/) |
| Senegal | SN | 14 | [View](countries/SN/) |
| Libya | LY | 14 | [View](countries/LY/) |
| Israel | IL | 14 | [View](countries/IL/) |
| Lao People&#39;s Democratic Republic | LA | 14 | [View](countries/LA/) |
| Netherlands, Kingdom of the | NL | 13 | [View](countries/NL/) |
| Sri Lanka | LK | 13 | [View](countries/LK/) |
| Bangladesh | BD | 13 | [View](countries/BD/) |
| Malawi | MW | 12 | [View](countries/MW/) |
| Mali | ML | 12 | [View](countries/ML/) |
| Bulgaria | BG | 12 | [View](countries/BG/) |
| Czechia | CZ | 12 | [View](countries/CZ/) |
| Uruguay | UY | 12 | [View](countries/UY/) |
| Tunisia | TN | 11 | [View](countries/TN/) |
| Zimbabwe | ZW | 11 | [View](countries/ZW/) |
| Guinea | GN | 11 | [View](countries/GN/) |
| Uganda | UG | 11 | [View](countries/UG/) |
| Dominican Republic | DO | 11 | [View](countries/DO/) |
| United Arab Emirates | AE | 11 | [View](countries/AE/) |
| Iraq | IQ | 11 | [View](countries/IQ/) |
| Paraguay | PY | 11 | [View](countries/PY/) |
| Cambodia | KH | 11 | [View](countries/KH/) |
| Cabo Verde | CV | 10 | [View](countries/CV/) |
| Nicaragua | NI | 10 | [View](countries/NI/) |
| Puerto Rico | PR | 10 | [View](countries/PR/) |
| Belgium | BE | 9 | [View](countries/BE/) |
| Liberia | LR | 9 | [View](countries/LR/) |
| Croatia | HR | 9 | [View](countries/HR/) |
| Sierra Leone | SL | 8 | [View](countries/SL/) |
| Hungary | HU | 8 | [View](countries/HU/) |
| Slovakia | SK | 8 | [View](countries/SK/) |
| Cook Islands | CK | 8 | [View](countries/CK/) |
| Azerbaijan | AZ | 8 | [View](countries/AZ/) |
| Lithuania | LT | 7 | [View](countries/LT/) |
| Austria | AT | 7 | [View](countries/AT/) |
| Serbia | RS | 7 | [View](countries/RS/) |
| Turks and Caicos Islands | TC | 7 | [View](countries/TC/) |
| French Guiana | GF | 7 | [View](countries/GF/) |
| Belarus | BY | 7 | [View](countries/BY/) |
| Turkmenistan | TM | 7 | [View](countries/TM/) |
| Timor-Leste | TL | 7 | [View](countries/TL/) |
| Benin | BJ | 6 | [View](countries/BJ/) |
| Niger | NE | 6 | [View](countries/NE/) |
| Seychelles | SC | 6 | [View](countries/SC/) |
| Jamaica | JM | 6 | [View](countries/JM/) |
| Haiti | HT | 6 | [View](countries/HT/) |
| Tonga | TO | 6 | [View](countries/TO/) |
| Syrian Arab Republic | SY | 6 | [View](countries/SY/) |
| Guadeloupe | GP | 6 | [View](countries/GP/) |
| Ghana | GH | 5 | [View](countries/GH/) |
| Estonia | EE | 5 | [View](countries/EE/) |
| Djibouti | DJ | 5 | [View](countries/DJ/) |
| Rwanda | RW | 5 | [View](countries/RW/) |
| Marshall Islands | MH | 5 | [View](countries/MH/) |
| Saint Vincent and the Grenadines | VC | 5 | [View](countries/VC/) |
| Latvia | LV | 4 | [View](countries/LV/) |
| Comoros | KM | 4 | [View](countries/KM/) |
| Eritrea | ER | 4 | [View](countries/ER/) |
| South Sudan | SS | 4 | [View](countries/SS/) |
| Cyprus | CY | 4 | [View](countries/CY/) |
| Bosnia and Herzegovina | BA | 4 | [View](countries/BA/) |
| Samoa | WS | 4 | [View](countries/WS/) |
| Jordan | JO | 4 | [View](countries/JO/) |
| Micronesia, Federated States of | FM | 4 | [View](countries/FM/) |
| Georgia | GE | 4 | [View](countries/GE/) |
| Tajikistan | TJ | 4 | [View](countries/TJ/) |
| Singapore | SG | 4 | [View](countries/SG/) |
| Korea, Democratic People&#39;s Republic of | KP | 4 | [View](countries/KP/) |
| Western Sahara | EH | 3 | [View](countries/EH/) |
| Burundi | BI | 3 | [View](countries/BI/) |
| Slovenia | SI | 3 | [View](countries/SI/) |
| Montenegro | ME | 3 | [View](countries/ME/) |
| Cayman Islands | KY | 3 | [View](countries/KY/) |
| American Samoa | AS | 3 | [View](countries/AS/) |
| Qatar | QA | 3 | [View](countries/QA/) |
| Northern Mariana Islands | MP | 3 | [View](countries/MP/) |
| Bonaire, Sint Eustatius and Saba | BQ | 3 | [View](countries/BQ/) |
| Virgin Islands (British) | VG | 3 | [View](countries/VG/) |
| Kyrgyzstan | KG | 3 | [View](countries/KG/) |
| Bhutan | BT | 3 | [View](countries/BT/) |
| Togo | TG | 2 | [View](countries/TG/) |
| Guernsey | GG | 2 | [View](countries/GG/) |
| Falkland Islands (Malvinas) | FK | 2 | [View](countries/FK/) |
| Eswatini | SZ | 2 | [View](countries/SZ/) |
| Equatorial Guinea | GQ | 2 | [View](countries/GQ/) |
| Saint Helena, Ascension and Tristan da Cunha | SH | 2 | [View](countries/SH/) |
| Mauritius | MU | 2 | [View](countries/MU/) |
| Réunion | RE | 2 | [View](countries/RE/) |
| Sao Tome and Principe | ST | 2 | [View](countries/ST/) |
| Guinea-Bissau | GW | 2 | [View](countries/GW/) |
| Albania | AL | 2 | [View](countries/AL/) |
| Saint Pierre and Miquelon | PM | 2 | [View](countries/PM/) |
| Moldova, Republic of | MD | 2 | [View](countries/MD/) |
| North Macedonia | MK | 2 | [View](countries/MK/) |
| El Salvador | SV | 2 | [View](countries/SV/) |
| Belize | BZ | 2 | [View](countries/BZ/) |
| Wallis and Futuna | WF | 2 | [View](countries/WF/) |
| Kuwait | KW | 2 | [View](countries/KW/) |
| Lebanon | LB | 2 | [View](countries/LB/) |
| Guam | GU | 2 | [View](countries/GU/) |
| United States Minor Outlying Islands | UM | 2 | [View](countries/UM/) |
| Antigua and Barbuda | AG | 2 | [View](countries/AG/) |
| Dominica | DM | 2 | [View](countries/DM/) |
| Grenada | GD | 2 | [View](countries/GD/) |
| Virgin Islands (U.S.) | VI | 2 | [View](countries/VI/) |
| Saint Kitts and Nevis | KN | 2 | [View](countries/KN/) |
| Saint Lucia | LC | 2 | [View](countries/LC/) |
| Trinidad and Tobago | TT | 2 | [View](countries/TT/) |
| Armenia | AM | 2 | [View](countries/AM/) |
| Nauru | NR | 1 | [View](countries/NR/) |
| KS | KS | 1 | [View](countries/KS/) |
| Jersey | JE | 1 | [View](countries/JE/) |
| Isle of Man | IM | 1 | [View](countries/IM/) |
| Faroe Islands | FO | 1 | [View](countries/FO/) |
| Luxembourg | LU | 1 | [View](countries/LU/) |
| British Indian Ocean Territory | IO | 1 | [View](countries/IO/) |
| Mayotte | YT | 1 | [View](countries/YT/) |
| Gambia | GM | 1 | [View](countries/GM/) |
| Malta | MT | 1 | [View](countries/MT/) |
| Gibraltar | GI | 1 | [View](countries/GI/) |
| Tuvalu | TV | 1 | [View](countries/TV/) |
| Niue | NU | 1 | [View](countries/NU/) |
| Bahrain | BH | 1 | [View](countries/BH/) |
| Palau | PW | 1 | [View](countries/PW/) |
| Antarctica | AQ | 1 | [View](countries/AQ/) |
| Barbados | BB | 1 | [View](countries/BB/) |
| Martinique | MQ | 1 | [View](countries/MQ/) |
| Saint Martin (French part) | MF | 1 | [View](countries/MF/) |
| Saint Barthélemy | BL | 1 | [View](countries/BL/) |
| Aruba | AW | 1 | [View](countries/AW/) |
| Curaçao | CW | 1 | [View](countries/CW/) |
| Sint Maarten (Dutch part) | SX | 1 | [View](countries/SX/) |
| Anguilla | AI | 1 | [View](countries/AI/) |
| Montserrat | MS | 1 | [View](countries/MS/) |
| Bermuda | BM | 1 | [View](countries/BM/) |
| Hong Kong | HK | 1 | [View](countries/HK/) |
| Macao | MO | 1 | [View](countries/MO/) |
| Brunei Darussalam | BN | 1 | [View](countries/BN/) |
| Cocos (Keeling) Islands | CC | 1 | [View](countries/CC/) |
| Christmas Island | CX | 1 | [View](countries/CX/) |
| Norfolk Island | NF | 1 | [View](countries/NF/) |


## Browse Online

Explore and download individual datasets at **[listbase.org](https://listbase.org/en/transport/)**.

## License

[MIT](LICENSE) — Free to use for any purpose.

## Source

OurAirports, OpenFlights, and public aviation registries

---

Made with data from [ListBase.org](https://listbase.org/en/transport/) — Free Reference Tables & Lists
