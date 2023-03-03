# Adblocker Domain/URL List collection

* Collection of blacklist/whitelist containing Domain names/URLs for DNS-adblockers such as pihole

## Setup
+ DNS-wide adblocker like AdGuard or pihole

## Documentation
### Synopsis/Syntax
- Relevant list URLs
    - Adlist Sources
        ```
        https://raw.githubusercontent.com/Thanatisia/domain-lists/lists/adlists/[list-name]
        ```
    - Whitelists
        ```
        https://raw.githubusercontent.com/Thanatisia/domain-lists/lists/whitelists/[list-name]
        ```
    - Blacklists
        ```
        https://raw.githubusercontent.com/Thanatisia/domain-lists/lists/blacklists/[list-name]
        ```

### Usage
- Pi-hole
    - Importing Lists
        - Importing Adlists
            - Manually
                - via WebGUI
                    + Copy the filename's url according to the template syntax shown in [Synopsis/Syntax](#synopsis/syntax) 
                    - Go to tab 'Adlists'
                        - Paste all sources into the Address bar
                            + Please seperate each domain/url with a space-delimiter
                        + Press Add
                        + Edit and add your comments and group assignments
        - Importing Blacklist
            - Manually
                - via WebGUI
                    - Go to tab 'Adlists'
                        + Enter the filename's url according to the template syntax shown in [Synopsis/Syntax](#synopsis/syntax) 
                        + Set your target user/groups
        - Importing Whitelist
            - Automatically
                - Unfortunately, due to limitations, the importing of adlist as files from the WebGUI is only for Blacklists, thus
                    + You will need to use the pihole CLI
                    + This will create a '/etc/pihole/whitelist.txt' file for you by downloading whitelist.txt and copying it to '/etc/pihole' folder
                ```console
                pihole -w [whitelist-filename]
                ```
            - Manually
                - via Adlist
                    - Download the whitelist file
                        ```console
                        curl -L -O [whitelist-file-url]
                        ```
                    + Copy all the contents of the whitelist to clipboard
                    - Add whitelist contents to database
                        + Go to Web admin GUI
                            + Go to tab 'Domains'
                            + Paste the contents directly into the 'domain' textbox
                            + Press 'Add to Whitelist'
                            + Update comments and group assignment to users for the domain
    - Update block/whitelist gravity
        - Update Gravity from WebGUI
            + Go to tab 'Tools'
            + Update Gravity
        - Update Gravity using CLI
            ```console
            pihole -g
            ```

## Wiki

### Pages
+ [CONTRIBUTING](#CONTRIBUTING.md)

## Resources
+ [StevenBlack hosts](https://raw.githubusercontent.com/StevenBlack/hosts/master/hosts)
+ [firebog adlists](https://firebog.net)

## References
+ [pihole discourse - How do I add a whitelist.txt](https://discourse.pi-hole.net/t/how-do-i-add-a-whitelist-txt/26495)
+ [pihole discourse - How to import many domains into PiHole Whitelist](https://discourse.pi-hole.net/t/how-to-import-many-domains-into-pihole-whitelist/6958)

## Remarks
